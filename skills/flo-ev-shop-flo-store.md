---
name: Shop the FLO store with MCP
description: Search FLO's EV charging hardware and accessories catalogue, look up a product and its variants, and build a cart through the live Shopify storefront MCP server on store.flo.com.
api: mcp/flo-ev-mcp.yml
surface: https://store.flo.com/api/mcp
operations: [search_catalog, get_product_details, get_cart, update_cart, search_shop_policies_and_faqs]
generated: '2026-07-27'
method: generated
grounding: mcp/flo-ev-store-mcp-tools.json (verbatim tools/list response, fetched 2026-07-27)
---

# Shop the FLO store with MCP

FLO publishes no developer API for its charging network. It does run a live, anonymously
callable MCP server on its Shopify-hosted hardware store. Everything below is grounded in the
verbatim `tools/list` response captured in `mcp/flo-ev-store-mcp-tools.json` — only these five
tools exist, and their input schemas are the ones in that file.

## Connect

- Endpoint: `POST https://store.flo.com/api/mcp`
- Headers: `Content-Type: application/json`, `Accept: application/json, text/event-stream`
- Protocol version: `2025-06-18` (server reports `storefront-renderer` 0.1.0)
- `initialize` and `tools/list` require no credentials. `prompts/list` and `resources/list`
  both return empty arrays — this server exposes tools only.

## Authentication

Catalogue reads work anonymously. Anything tied to a signed-in customer needs a Shopify
Customer Account token:

1. Read `https://store.flo.com/.well-known/oauth-protected-resource` — it names
   `https://shopify.com/authentication/85271511350` as the authorization server and bearer
   token in the `Authorization` header.
2. Run the authorization-code flow against that issuer (`/oauth/authorize`, `/oauth/token`)
   with the scope `customer-account-mcp-api:full`.

See `authentication/flo-ev-authentication.yml` and `scopes/flo-ev-scopes.yml`.

## Steps

1. **Find products** — call `search_catalog`. Pass a natural-language query, filter criteria,
   or both, inside the `catalog` argument; `meta` carries request metadata. At least one of
   query or filters must be provided. Results are paginated: carry `pagination.cursor` from the
   response into the next call only when the user asks for more. The response conforms to the
   UCP catalog search capability `dev.ucp.shopping.catalog.search`.
2. **Confirm the exact item** — call `get_product_details` with the `product_id` from step 1.
   Add `options` to pin a specific variant (FLO hardware varies by connector, cable length and
   mounting), and `country` / `language` to get the right price and copy — the FLO store runs
   regional and French/English storefronts (`store.us.flo.com`, `store.en.flo.com`,
   `store.fr.flo.com`).
3. **Answer policy questions before checkout** — call `search_shop_policies_and_faqs` with a
   `query` (required) for shipping, returns, warranty or installation questions. Do not
   paraphrase FLO warranty or installation terms from memory; quote what this tool returns.
4. **Build the cart** — call `update_cart`. Omit `cart_id` to create a new cart, or pass an
   existing one. Line items go in `add_items` / `update_items`, removals in `remove_line_ids`.
   Buyer details go in `buyer_identity`; addresses in `delivery_addresses_to_add` or
   `delivery_addresses_to_replace`, then pick `selected_delivery_options`. `discount_codes`,
   `gift_card_codes` and `note` are optional.
5. **Read back and hand off** — call `get_cart` with the required `cart_id` to get line items,
   shipping options, discount info and the checkout URL. Give the checkout URL to the user;
   never attempt to complete payment on their behalf.

## Rules

- Only these five tools exist on this server. There is no FLO tool for charging sessions,
  station telemetry, roaming or demand response — those surfaces are partner-mediated and have
  no API. If asked, say so rather than guessing an endpoint.
- The MCP path is `/api/mcp`. `https://store.flo.com/mcp` returns `503 SERVICE_UNAVAILABLE`.
- Error envelopes are platform-native, not RFC 9457. Shopify returns
  `{"errors":[{"message":...,"extensions":{"code":...}}]}`. See `errors/flo-ev-problem-types.yml`.
- No idempotency key is documented for this surface. Treat `update_cart` as non-idempotent:
  read the cart back with `get_cart` after a failed or ambiguous write instead of retrying blind.
- No rate limit is published. Back off on any 429 or 503.
- Prices and availability are regional — always pass `country`/`language` when the user's market
  is known.
