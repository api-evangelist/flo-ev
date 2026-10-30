# FLO

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

FLO is a Quebec City headquartered electric vehicle charging company, founded in 2009 as AddEnergie (addenergie.com now redirects to flo.com), that designs and manufactures its own Level 2 and DC fast charging hardware and operates one of the largest public charging networks in North America. FLO sits on the demand side of the electricity value chain rather than inside the regulated utility layer: it is a charge point operator and e-mobility service provider, not a distributor, transmitter or retailer, so Canada's energy-data obligations do not reach it. Ontario's Green Button regulation binds Ontario electricity and natural gas utilities, and Australia's Consumer Data Right for energy is a different jurisdiction entirely; neither applies to FLO, and FLO publishes no consumer energy data API of any kind. Its API posture is closed and partner-mediated. flo.com has no developer subdomain and no published API reference: developer.flo.com, developers.flo.com, api.flo.com, docs.flo.com and data.flo.com all fail to resolve, and /developers, /api, /openapi.json, /swagger.json and /api-docs all return 404. FLO does name real interoperability standards on its own pages - OCPP 1.6J on the station-to-network side, OCPI for roaming with partner networks, and OpenADR 2.0 alongside "FLO's flexible API" for utility demand response and smart grid integration - but each of those is reached through a commercial agreement rather than a signup form. Customer charging and session data is reachable only by the account holder through the account.flo.com login, and FLO publishes no open market, grid or station-location data feed under its own name. A second enrichment round in July 2026 did find live machine-readable surfaces on flo.com hosts, but all of them are platform-provided rather than FLO-authored: a Shopify storefront MCP server with five tools at store.flo.com/api/mcp plus public products.json and collections.json feeds, RFC 8414/9728 and OIDC discovery documents on store.flo.com, Salesforce Experience Cloud OIDC discovery on network.flo.com, and a Vanta trust center at trust.flo.com carrying FLO's SOC 2 Type 2. FLO also runs real but entirely private API infrastructure - auth.flo.com is an AWS API Gateway that answers every path with 403 Missing Authentication Token, alongside csnms.flo.com and an EMS host - so the charging network itself remains closed.

**Areas:** Energy · Canada · EV Charging · Electricity · Grid · Demand Response · Interoperability · OCPP · OCPI · OpenADR · Charge Point Operator · Quebec

## FLO on APIs.io

Everything profiled for FLO is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/flo-ev/](https://apis.io/providers/flo-ev/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [FLO Store (Shopify Storefront MCP)](https://apis.io/apis/flo-ev/flo-store-shopify-storefront-mcp/) — The only live, anonymously callable machine-readable surface in FLO's estate. FLO's hardware and accessories store runs on Shopify, and that platform serves…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [flo-store](https://apis.io/servers/flo-ev/flo-store/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [FLO — lint configurations rules](https://apis.io/rules/flo-ev/flo-ev-lint-configurations-spectral-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Flo Ev Authentication](https://apis.io/security/flo-ev/flo-ev-authentication/)
- [Flo Ev Domain Security](https://apis.io/security/flo-ev/flo-ev-domain-security/)
- [Flo Ev Trust Center](https://apis.io/security/flo-ev/flo-ev-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Flo Ev Scopes](https://apis.io/scopes/flo-ev/flo-ev-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.flo.com/)
- [Documentation](https://www.flo.com/business/product-documentation/)
- [Support](https://www.flo.com/support/)
- [Blog](https://www.flo.com/ev-charging-insights/)
- [Compliance](https://trust.flo.com/)
- [Terms of service](https://www.flo.com/terms-conditions/)
- [Privacy policy](https://www.flo.com/privacy-policy/)

## API Evangelist rating

**Kin Score 27.9** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 0.0 |
| Contract governance | 33.3 |
| Operational transparency | 0.0 |
| Developer ergonomics | 30.4 |
| Access clarity | 35.5 |

**Agent readiness 20.3** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | platform (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 34.4** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/flo-ev/](https://apis.io/providers/flo-ev/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for FLO: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/flo-ev/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
