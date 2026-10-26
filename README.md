# ShipFinder AIS Data API (shipfinder-ais-data-api)

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

ShipFinder, operated by Singapore-based ELANE GLOBAL PTE. LTD., publishes a REST/HTTP maritime data API that turns the global AIS feed into queryable vessel intelligence. Forty documented operations are organised into seven datasets: AIS (single, multi and fleet vessel positions, vessel search, vessels nearby, vessels in a zone, flag information), Voyage (port information, currently berthed and anchored vessels, expected arrivals), History (position tracks, ship-to-ship rendezvous, port-call records by vessel and by port), Prediction (point-to-point and port-to-port route planning with deviation-node constraints, and ETA), Meteorology (global tropical cyclones, tide gauge stations, marine weather), China region coastline navigational warnings, and an Event dataset whose fleet, geofence and speed-alert operations drive seven documented webhook push streams. Authentication is a single API key carried as the "key" query parameter (or body property on writes); every response is JSON in a {status, msg, data} envelope where status 0 means success and errors arrive with HTTP 200. ShipFinder publishes per-endpoint OpenAPI 3.0.1 fragments on its documentation host plus an llms.txt index, and several controlled vocabularies (AIS vessel type, navigation status, sea areas, deviation nodes, AtoN types, service return codes).

**APIs.json:** [https://shipfinder-ais-data-api.apievangelist.com/apis.yml](https://shipfinder-ais-data-api.apievangelist.com/apis.yml)

## Tags

- AIS
- Maritime Data
- Vessel Tracking
- Ship Tracking
- Vessel Data
- Historical AIS
- Geospatial
- GIS
- Logistics
- Supply Chain
- Weather
- Meteorology
- Trade
- Commodities
- Compliance
- Risk
- Event Streaming
- Webhooks

## Timestamps

- **Created:** 2026-08-04
- **Modified:** 2026-08-09

## APIs

### ShipFinder AIS Data API AIS Dataset API

The AIS Dataset API from ShipFinder AIS Data API — 7 operation(s) for ais dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- AIS Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-ais-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-ais-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-ais-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API China Coastline Warning Dataset API

The China Coastline Warning Dataset API from ShipFinder AIS Data API — 1 operation(s) for china coastline warning dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- China Coastline Warning Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-china-coastline-warning-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-china-coastline-warning-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-china-coastline-warning-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API Event Dataset API

The Event Dataset API from ShipFinder AIS Data API — 14 operation(s) for event dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- Event Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-event-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-event-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-event-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API History Dataset API

The History Dataset API from ShipFinder AIS Data API — 6 operation(s) for history dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- History Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-history-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-history-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-history-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API Meteorology Dataset API

The Meteorology Dataset API from ShipFinder AIS Data API — 5 operation(s) for meteorology dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- Meteorology Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-meteorology-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-meteorology-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-meteorology-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API Prediction Dataset API

The Prediction Dataset API from ShipFinder AIS Data API — 3 operation(s) for prediction dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- Prediction Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-prediction-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-prediction-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-prediction-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

### ShipFinder AIS Data API Voyage Dataset API

The Voyage Dataset API from ShipFinder AIS Data API — 4 operation(s) for voyage dataset.

- **Human URL:** [https://www.shipfinder.com/ais-data-api](https://www.shipfinder.com/ais-data-api)
- **Base URL:** `https://api.elaneglobal.com`

#### Tags

- Voyage Dataset

#### Properties

- [OpenAPI](openapi/shipfinder-ais-data-api-voyage-dataset-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/shipfinder-ais-data-api-voyage-dataset-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/shipfinder-ais-data-api-voyage-dataset-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [L L M S Txt](https://docs.shipfinder.com/llms.txt)

## Common Properties

- [Developer Portal](https://open.shipfinder.com/)
- [Documentation](https://docs.shipfinder.com/)
- [API Reference](https://docs.shipfinder.com/8952919m0)
- [Getting Started](https://docs.shipfinder.com/9177505m0)
- [Support](https://www.shipfinder.com/help-center)
- [Sign Up](https://www.shipfinder.com/home/register)
- [Login](https://www.shipfinder.com/home/login)
- [Pricing](https://www.shipfinder.com/home/plans_pricing)
- [Terms of Service](https://www.shipfinder.com/Home/TermsConditions)
- [Privacy Policy](https://www.shipfinder.com/Home/Privacy)
- [Console](https://open.shipfinder.com/v1/console/overview)
- [L L Ms Txt](llms/shipfinder-ais-data-api-llms.txt)
- [Plans](plans/shipfinder-ais-data-api-plans.yml)
- [Rate Limits](rate-limits/shipfinder-ais-data-api-rate-limits.yml)
- [Authentication](authentication/shipfinder-ais-data-api-authentication.yml)
- [Conventions](conventions/shipfinder-ais-data-api-conventions.yml)
- [Error Catalog](errors/shipfinder-ais-data-api-error-codes.yml)
- [Vocabulary](vocabulary/shipfinder-ais-data-api-vocabulary.yml)
- [Examples](examples/shipfinder-ais-data-api-examples.yml)
- [Data Model](data-model/shipfinder-ais-data-api-data-model.yml)
- [Lifecycle](lifecycle/shipfinder-ais-data-api-lifecycle.yml)
- [Conformance](conformance/shipfinder-ais-data-api-conformance.yml)
- [Overlay](overlays/shipfinder-ais-data-api-openapi-overlay.yaml)
- [Packages](packages/shipfinder-ais-data-api-packages.yml)
- [Well Known](well-known/shipfinder-ais-data-api-well-known.yml)
- [AsyncAPI](asyncapi/shipfinder-ais-data-api-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Webhooks](asyncapi/shipfinder-ais-data-api-webhooks.yml)
- [M C P Server](mcp/shipfinder-ais-data-api-mcp.yml)
- [Agent Skill](skills/_index.yml)
- [Arazzo](arazzo/track-a-vessel.yml) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Arazzo](arazzo/port-congestion-snapshot.yml) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Arazzo](arazzo/voyage-plan-and-eta.yml) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Agentic Access](agentic-access/shipfinder-ais-data-api-agentic-access.yml)
- [Domain Security](security/shipfinder-ais-data-api-domain-security.yml)

## Maintainers

**FN:** ShipFinder AIS Data API
**Email:** support@elaneglobal.com
**URL:** https://www.shipfinder.com/
