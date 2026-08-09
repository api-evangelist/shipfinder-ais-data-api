---
name: Find and track a vessel
description: Resolve a vessel from a name, call sign, MMSI or IMO, read its current
  AIS position, and replay its recent track.
api: openapi/shipfinder-ais-data-api-openapi.yml
operations:
- getVesselSearch
- getVesselPositionSingle
- getVesselPositionMulti
- getVesselHistoryTrack
- getVesselFlagInfo
generated: '2026-08-09'
method: generated
source: openapi/shipfinder-ais-data-api-openapi.yml, conventions/shipfinder-ais-data-api-conventions.yml,
  errors/shipfinder-ais-data-api-error-codes.yml
---

# Find and track a vessel

## When to use this skill

The user names a ship ("where is the EVER GIVEN", "what is MMSI 413149000 doing") and wants its identity,
its current position, or where it has been.

## Before you start

- Every request carries your ShipFinder API key as the `key` query parameter. There is no bearer token.
- The base URL is `https://api.elaneglobal.com`.
- Read the response envelope, **not** the HTTP status. Every call returns HTTP 200 with
  `{"status": <int>, "msg": "...", "data": ...}`. `status: 0` means success. Any other value is an error —
  look it up in `errors/shipfinder-ais-data-api-error-codes.yml`.

## Steps

1. **Resolve the vessel** — if you do not already have an MMSI, call `getVesselSearch`
   (`GET /v1/AIS/VesselSearch`) with `keywords` set to the vessel name, call sign, MMSI or IMO. Take the `mmsi`
   from the match. If several vessels come back, disambiguate on `imo` and `ship_type` before continuing —
   vessel names are not unique.
2. **Read the current position** — call `getVesselPositionSingle` (`GET /v1/AIS/VesselPositionSingle`) with
   `mmsi`. For more than one vessel, call `getVesselPositionMulti` (`GET /v1/AIS/VesselPositionMulti`) with a
   comma-separated `mmsis` list instead of looping — the multi call is quota-cheaper and a loop will trip
   envelope status 23 (query frequency exceeds limit).
3. **Interpret the payload** — `lat`/`lng` are WGS84 decimal degrees. `sog` is speed over ground in knots
   (`-1` = invalid). `hdg` of `511` means heading unavailable. `navistat` is the AIS navigation status and
   `ship_type` the AIS vessel type — decode both with `vocabulary/shipfinder-ais-data-api-vocabulary.yml`.
   `last_time` and `eta` are Unix epoch seconds in UTC.
4. **Replay the track** — call `getVesselHistoryTrack` (`GET /v1/History/VesselHistoryTrack`) with `mmsi`,
   `start_time` and `end_time`. The default entitlement covers only the latest month; a wider window returns
   envelope status 28 (track query time exceeds limit) until ShipFinder enables it on the key.
5. **Add registry detail** — call `getVesselFlagInfo` (`GET /v1/AIS/VesselFlagInfo`) when the user asks about
   flag state, registration or vessel identity records.

## Failure handling

- `status: 9 / 6 / 7` — the key does not exist, has expired, or is locked. Stop; this is a credential problem.
- `status: 14` — the key is bound to a different domain. Stop; do not retry.
- `status: 21` — the key has no permission for this dataset. Stop and tell the user the service must be
  enabled by ShipFinder (support@elaneglobal.com); retrying will not help.
- `status: 23 / 29` — frequency limit. Back off and batch with `getVesselPositionMulti`.
- `status: 3` — the vessel does not exist in ShipFinder's data. Re-run step 1 with looser keywords.

## Do not

- Do not assume a non-200 HTTP status signals the error — errors arrive with HTTP 200.
- Do not retry a write blindly: ShipFinder documents no idempotency key.
