# FLO (flo-ev)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

FLO is a Quebec City headquartered electric vehicle charging company, founded in 2009 as AddEnergie (addenergie.com now redirects to flo.com), that designs and manufactures its own Level 2 and DC fast charging hardware and operates one of the largest public charging networks in North America. FLO sits on the demand side of the electricity value chain rather than inside the regulated utility layer: it is a charge point operator and e-mobility service provider, not a distributor, transmitter or retailer, so Canada's energy-data obligations do not reach it. Ontario's Green Button regulation binds Ontario electricity and natural gas utilities, and Australia's Consumer Data Right for energy is a different jurisdiction entirely; neither applies to FLO, and FLO publishes no consumer energy data API of any kind. Its API posture is closed and partner-mediated. flo.com has no developer subdomain and no published API reference: developer.flo.com, developers.flo.com, api.flo.com, docs.flo.com and data.flo.com all fail to resolve, and /developers, /api, /openapi.json, /swagger.json and /api-docs all return 404. FLO does name real interoperability standards on its own pages — OCPP 1.6J on the station-to-network side, OCPI for roaming with partner networks, and OpenADR 2.0 alongside "FLO's flexible API" for utility demand response and smart grid integration — but each of those is reached through a commercial agreement rather than a signup form. Customer charging and session data is reachable only by the account holder through the account.flo.com login, and FLO publishes no open market, grid or station-location data feed under its own name.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/flo-ev/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/flo-ev/refs/heads/main/apis.yml)

## Tags

- Energy
- Canada
- EV Charging
- Electricity
- Grid
- Demand Response
- Interoperability
- OCPP
- OCPI
- OpenADR
- Charge Point Operator
- Quebec

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

No public, documented **first-party** API. FLO publishes no developer portal and no API reference, and no OpenAPI, AsyncAPI or GraphQL document exists on any flo.com host. See `review.yml` for the original probe log and the mandate/standard/access findings.

A second enrichment round (2026-07-27) hunted harder and did find live machine-readable surfaces on flo.com hosts — all **platform-provided**, none FLO-authored:

- **[FLO Store MCP server](https://store.flo.com/api/mcp)** — a live Shopify storefront MCP server (protocol `2025-06-18`, serverInfo `storefront-renderer` 0.1.0). `tools/list` answers anonymously with five tools: `search_catalog`, `get_product_details`, `get_cart`, `update_cart`, `search_shop_policies_and_faqs`. Verbatim schemas in `mcp/flo-ev-store-mcp-tools.json`.
- **Public JSON feeds** — `https://store.flo.com/products.json` and `/collections.json` (HTTP 200).
- **Discovery documents** — Shopify OIDC + RFC 8414 + RFC 9728 on `store.flo.com`; Salesforce Experience Cloud OIDC on `network.flo.com` (full endpoint set + JWKS + 36 platform scopes).
- **[Trust center](https://trust.flo.com/)** — Vanta-hosted; FLO holds **SOC 2 Type 2** (BARR Advisory, announced 2024-10-22).

FLO also runs real but entirely private API infrastructure: `auth.flo.com` is an AWS API Gateway that answers every path with `403 {"message":"Missing Authentication Token"}`, alongside `csnms.flo.com` (station network management) and `mqtt-production.ems.flo.com` (energy management). Every developer-facing name a third party would try — `api.`, `developer.`, `developers.`, `docs.`, `data.`, `ocpi.`, `status.` — does not resolve. The charging network itself stays closed and partner-mediated.

## Artifacts

- `mcp/` — MCP server manifest + verbatim `tools/list` capture
- `well-known/` — /.well-known/ probe index across five hosts + raw discovery documents
- `authentication/`, `scopes/` — identity profile and every OAuth scope advertised on a flo.com host (all platform-defined; FLO defines none)
- `conformance/` — OCPP 1.6J, OCPI, OpenADR 2.0, Plug and Charge, OIDC/OAuth/MCP, plus the explicit negatives
- `errors/` — the error envelopes FLO's live hosts actually return
- `lifecycle/` — versioning, deprecation, SLA and status-page findings (no status page exists)
- `security/` — TLS/HSTS/DNS posture, certificate-transparency subdomain census, trust center
- `skills/` — agent skill for the storefront MCP server
- `llms/` — generated llms.txt (FLO publishes none)

## Energy Data Posture

- **Mandate regime:** none — FLO is a charge point operator, not a regulated utility. Ontario's Green Button regulation binds Ontario electricity and gas utilities; the Australian CDR for energy is another jurisdiction. Neither reaches FLO.
- **Mandate status:** not-applicable — verified by absence across the full flo.com sitemap (103 pages); no compliance page, register entry, Green Button endpoint or ESPI surface exists.
- **Data standard:** OCPP 1.6J (station-to-network), OCPI (roaming), OpenADR 2.0 (utility demand response). No consumer energy data standard reference found.
- **Consumer data API:** No. Session, usage and billing data is reachable only by the account holder at [account.flo.com](https://account.flo.com/) or the station owner in the Owner's Portal.
- **Open market data:** No. No open grid, market, emissions or station-location feed is published.
- **Access gate:** partner-only. There is no signup form and no application form for API access — integration is a negotiated commercial arrangement (the EnergyHub OpenADR integration is the public example).
- **Auth model:** No API auth scheme is documented because no API is documented. Published auth surfaces are human: the account.flo.com web login, plus in-station driver auth via the FLO app, RFID, credit card, or GM Plug and Charge autocharge.

## Common Properties

- [Website](https://www.flo.com/)
- [Blog](https://www.flo.com/ev-charging-insights/) — [RSS](https://www.flo.com/feed/)
- [Press Room](https://www.flo.com/news-press/)
- [Media Room](https://www.flo.com/media-room/)
- [Support](https://www.flo.com/support/)
- [Product Documentation](https://www.flo.com/business/product-documentation/) — hardware spec sheets and guides only
- [FLO Account (login)](https://account.flo.com/) — customer login, not a developer portal
- [Partner Networks](https://www.flo.com/company/partner-networks/)
- [EV Charging Roaming (OCPI explainer)](https://www.flo.com/insights/ev-charging-roaming/)
- [FLO for Utilities (OpenADR 2.0)](https://www.flo.com/business/utilities/)
- [Privacy Policy](https://www.flo.com/privacy-policy/)
- [Terms of Service](https://www.flo.com/terms-conditions/)
- [LinkedIn](https://www.linkedin.com/company/floevcharging/)
- [Twitter](https://twitter.com/FLOevcharging)
- [Patents](https://www.flo.com/patents/)

## Maintainers

- Kin Lane — kin@apievangelist.com
