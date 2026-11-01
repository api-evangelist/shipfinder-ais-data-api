# ShipFinder AIS Data API

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

**Areas:** AIS · Maritime Data · Vessel Tracking · Ship Tracking · Vessel Data · Historical AIS · Geospatial · GIS · Logistics · Supply Chain · Weather · Meteorology

## ShipFinder AIS Data API on APIs.io

Everything profiled for ShipFinder AIS Data API is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/shipfinder-ais-data-api/](https://apis.io/providers/shipfinder-ais-data-api/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [ShipFinder AIS Data API 1 AIS Dataset/1.1 Vessel Position API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-1-ais-dataset-1-1-vessel-position-api/) — The 1 AIS Dataset/1.1 Vessel Position API from ShipFinder AIS Data API — 3 operation(s) for 1 ais dataset/1.1 vessel position.
- [ShipFinder AIS Data API 1 AIS Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-1-ais-dataset-api/) — The 1 AIS Dataset API from ShipFinder AIS Data API — 4 operation(s) for 1 ais dataset.
- [ShipFinder AIS Data API 2 Voyage Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-2-voyage-dataset-api/) — The 2 Voyage Dataset API from ShipFinder AIS Data API — 4 operation(s) for 2 voyage dataset.
- [ShipFinder AIS Data API 3 History Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-3-history-dataset-api/) — The 3 History Dataset API from ShipFinder AIS Data API — 6 operation(s) for 3 history dataset.
- [ShipFinder AIS Data API 4 Prediction Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-4-prediction-dataset-api/) — The 4 Prediction Dataset API from ShipFinder AIS Data API — 3 operation(s) for 4 prediction dataset.
- [ShipFinder AIS Data API 5 Meteorology Dataset/5.1 Global Tropical Cyclone API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-5-meteorology-dataset-5-1-global-tropical-cyclone-api/) — The 5 Meteorology Dataset/5.1 Global Tropical Cyclone API from ShipFinder AIS Data API — 2 operation(s) for 5 meteorology dataset/5.1 global tropical cyclone.
- [ShipFinder AIS Data API 5 Meteorology Dataset/5.2 Global Port Tide Predictions API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-5-meteorology-dataset-5-2-global-port-tide-predictions-api/) — The 5 Meteorology Dataset/5.2 Global Port Tide Predictions API from ShipFinder AIS Data API — 2 operation(s) for 5 meteorology dataset/5.2 global port tide…
- [ShipFinder AIS Data API 5 Meteorology Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-5-meteorology-dataset-api/) — The 5 Meteorology Dataset API from ShipFinder AIS Data API — 1 operation(s) for 5 meteorology dataset.
- [ShipFinder AIS Data API 6 China Region Coastline Warning Dataset API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-6-china-region-coastline-warning-dataset-api/) — The 6 China Region Coastline Warning Dataset API from ShipFinder AIS Data API — 1 operation(s) for 6 china region coastline warning dataset.
- [ShipFinder AIS Data API 7 Event Dataset/7.1 Monitored Fleet Management API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-7-event-dataset-7-1-monitored-fleet-management-api/) — The 7 Event Dataset/7.1 Monitored Fleet Management API from ShipFinder AIS Data API — 7 operation(s) for 7 event dataset/7.1 monitored fleet management.
- [ShipFinder AIS Data API 7 Event Dataset/7.2 Geofence Monitoring Push API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-7-event-dataset-7-2-geofence-monitoring-push-api/) — The 7 Event Dataset/7.2 Geofence Monitoring Push API from ShipFinder AIS Data API — 4 operation(s) for 7 event dataset/7.2 geofence monitoring push.
- [ShipFinder AIS Data API 7 Event Dataset/7.3 Vessel Speed Alert Push API](https://apis.io/apis/shipfinder-ais-data-api/shipfinder-ais-data-api-7-event-dataset-7-3-vessel-speed-alert-push-api/) — The 7 Event Dataset/7.3 Vessel Speed Alert Push API from ShipFinder AIS Data API — 3 operation(s) for 7 event dataset/7.3 vessel speed alert push.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Arazzo workflows (3)

Multi-step workflows that chain operations into a business task.

- [Resolve a port and read berthed, anchored and inbound vessels](https://apis.io/arazzos/shipfinder-ais-data-api/port-congestion-snapshot/)
- [Find a vessel and read its position and recent track](https://apis.io/arazzos/shipfinder-ais-data-api/track-a-vessel/)
- [Plan a port-to-port route, predict ETA and check active tropical cyclones](https://apis.io/arazzos/shipfinder-ais-data-api/voyage-plan-and-eta/)

#### AsyncAPI (2)

Event-driven and webhook contracts.

- [ShipFinder Event Dataset (push)](https://apis.io/asyncapis/shipfinder-ais-data-api/shipfinder-ais-data-api-events-asyncapi/)
- [Shipfinder Ais Data Api Webhooks](https://apis.io/asyncapis/shipfinder-ais-data-api/shipfinder-ais-data-api-webhooks/)

#### Event channels (7)

Individual events and webhooks the provider emits.

- [/](https://apis.io/channels/shipfinder-ais-data-api/arrivaldeparturepush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/geofencemonitoringpush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/realtimevesselpositionpush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/vesselaissignallosspush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/vesseldynamicetapush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/vesselspeedanomalypush/)
- [/](https://apis.io/channels/shipfinder-ais-data-api/vesselstseventpush/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [shipfinder](https://apis.io/servers/shipfinder-ais-data-api/shipfinder/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Shipfinder Ais Data Api Agentic Access](https://apis.io/agentic-access/shipfinder-ais-data-api/shipfinder-ais-data-api-agentic-access/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [ShipFinder maritime reference vocabularies](https://apis.io/vocabularies/shipfinder-ais-data-api/shipfinder-ais-data-api-vocabulary/)

#### Collections (7)

Postman and Open Collection request collections.

- [ShipFinder Global Maritime Data AIS Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-ais-dataset-api/)
- [ShipFinder Global Maritime Data China Coastline Warning Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-china-coastline-warning-dataset-api/)
- [ShipFinder Global Maritime Data Event Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-event-dataset-api/)
- [ShipFinder Global Maritime Data History Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-history-dataset-api/)
- [ShipFinder Global Maritime Data Meteorology Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-meteorology-dataset-api/)
- [ShipFinder Global Maritime Data Prediction Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-prediction-dataset-api/)
- [ShipFinder Global Maritime Data Voyage Dataset API](https://apis.io/collections/shipfinder-ais-data-api/open-shipfinder-ais-data-api-voyage-dataset-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Shipfinder Ais Data Api Openapi Overlay](https://apis.io/overlays/shipfinder-ais-data-api/shipfinder-ais-data-api-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Shipfinder Ais Data Api Authentication](https://apis.io/security/shipfinder-ais-data-api/shipfinder-ais-data-api-authentication/)
- [Shipfinder Ais Data Api Domain Security](https://apis.io/security/shipfinder-ais-data-api/shipfinder-ais-data-api-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Shipfinder Ais Data Api Plans](https://apis.io/plans/shipfinder-ais-data-api/shipfinder-ais-data-api-plans/)

#### Rate limits (1)

Published request limits.

- [Shipfinder Ais Data Api Rate Limits](https://apis.io/rate-limits/shipfinder-ais-data-api/shipfinder-ais-data-api-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.shipfinder.com/)
- [Documentation](https://docs.shipfinder.com/)
- [Getting started](https://docs.shipfinder.com/9177505m0)
- [API reference](https://docs.shipfinder.com/8952919m0)
- [Pricing](https://www.shipfinder.com/home/plans_pricing)
- [Sign up](https://www.shipfinder.com/home/register)
- [Support](https://www.shipfinder.com/help-center)
- [Terms of service](https://www.shipfinder.com/Home/TermsConditions)
- [Privacy policy](https://www.shipfinder.com/Home/Privacy)

## API Evangelist rating

**Kin Score 47.8** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 44.3 |
| Contract governance | 19.7 |
| Operational transparency | 7.9 |
| Developer ergonomics | 63.7 |
| Access clarity | 65.8 |

**Agent readiness 33.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 20.6** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/shipfinder-ais-data-api/](https://apis.io/providers/shipfinder-ais-data-api/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for ShipFinder AIS Data API: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/shipfinder-ais-data-api/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
