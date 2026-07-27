# Evie Networks (evie-networks)

Evie Networks is an Australian electric-vehicle charging infrastructure company, founded in 2017 and backed by the St Baker Energy Innovation Fund, that owns and operates one of the country's largest DC fast and ultrafast public charging networks across 300+ locations in every state and territory. It sits downstream of the electricity retail market as a charge point operator (CPO) and e-mobility service provider, buying energy and reselling it as charging sessions to drivers and fleets, and it also builds and operates charging assets for site hosts, councils, dealerships and commercial property owners. Its API posture is closed: as of 2026-07-27 there is no developer portal, no published API documentation, no OpenAPI or other machine-readable contract, and no named support for the EV charging interoperability standards (OCPP, OCPI, ISO 15118). Evie is not a designated data holder under Australia's Consumer Data Right energy regime — the CDR Register's public energy data-holder brand summary lists 84 brands and Evie is not among them — so the statutory data mandate that produced identical APIs across Australian banks and energy retailers does not reach the EV charging layer at all. A live production API host exists at api.goevie.com.au serving the Evie Charging mobile app, but it is undocumented, unadvertised and returns a Google Cloud Endpoints 404 to anonymous callers. Neither consumer charging-session data nor network/market data is published through any documented public interface; charger location data reaches developers only through third-party aggregators.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/evie-networks/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/evie-networks/refs/heads/main/apis.yml)

## Tags

- Energy
- Australia
- EV Charging
- Electricity
- Utilities
- E-Mobility
- Charging Infrastructure
- Fleet
- Transport Electrification

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

No documented public APIs.

Evie Networks publishes no developer portal, no API reference, and no machine-readable contract. Probing on 2026-07-27 found `developer.`, `developers.`, `api.`, `docs.` and `data.` subdomains unresolved on both `evie.com.au` and `evienetworks.com`, and `/developers`, `/api`, `/docs`, `/data`, `/openapi.json`, `/swagger.json`, `/api-docs` and `/.well-known/openid-configuration` all returning 404. The full 58-page sitemap contains no developer, API, data or open-data page.

A live production API gateway does exist at `https://api.goevie.com.au` — it answers anonymously with the Google Cloud Endpoints body `{"message":"The current request is not defined by this API.","code":404}` — but it is the private backend for the Evie Charging mobile app, is referenced nowhere on the public site, and has no documentation, terms or onboarding. It is recorded in `review.yml` and deliberately not listed as a public API.

## Mandate posture

- **Mandate regime:** none
- **Mandate status:** not-applicable
- **Data standard:** no standard reference found

Australia's Consumer Data Right was extended to energy and is live, with electricity retailers as primary data holders and AEMO as secondary data holder under the ACCC and the Data Standards Body — the same statutory machinery that produced the byte-for-byte identical banking APIs. That regime binds retailers and AEMO. It does not reach charge point operators. A query to the CDR Register's public endpoint `https://api.cdr.gov.au/cdr-register/v1/energy/data-holders/brands/summary` (HTTP 200, 2026-07-27) returned 84 designated energy data-holder brands, each with a conformant `publicBaseUri`; Evie Networks is not among them.

## Consumer data vs market data

- **Consumer data API:** no — charging-session, billing and subscription data is available only inside a customer's own app account, with no third-party access path, no consent flow and no accreditation route.
- **Open market data:** no — no network, utilisation, availability, pricing or emissions feed is published. The charger map at `/find-a-charger/` is the WP Store Locator WordPress plugin over Google Maps, not an Evie data API.

Evie is closed on both axes. The only anonymously callable JSON the company operates is the default WordPress REST API on the marketing site (`/wp-json/`, HTTP 200, 813 routes), which incidentally exposes charging-site records via `wp/v2/wpsl_stores`. That is CMS plumbing, not a product, and is not listed as an Evie API.

## Access

- **Access gate:** none-published
- **Auth model:** not published — no API keys, no OAuth2/OIDC discovery (`/.well-known/openid-configuration` 404 on both `evie.com.au` and `api.goevie.com.au`), no mTLS onboarding, no CDR accreditation pathway.

There is no action a developer can take to obtain API access. The commercial routes on the site — become a site host, fleet charge cards, council and dealership programmes — are sales enquiry forms for charging services, not for data or API access.

## Common Properties

- [Website](https://evie.com.au/)
- [About](https://evie.com.au/about-evie/)
- [Blog](https://evie.com.au/blog/)
- [Blog RSS](https://evie.com.au/feed/)
- [Support](https://evie.com.au/help-center/)
- [Privacy Policy](https://evie.com.au/privacy-policy/)
- [Terms of Service](https://evie.com.au/terms-of-service/)
- [LinkedIn](https://au.linkedin.com/company/evie-networks)
- [GitHub Organization](https://github.com/goevie)

## Maintainers

- Kin Lane — kin@apievangelist.com
