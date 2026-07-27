# FLO (flo-ev)

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

No public, documented APIs. FLO publishes no developer portal, no API reference and no machine-readable contract. See `review.yml` for the full probe log and the mandate/standard/access findings.

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
