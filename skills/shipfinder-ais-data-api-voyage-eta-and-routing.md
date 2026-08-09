---
name: Plan a voyage and predict arrival
description: Plan a sea route between two ports or coordinates, predict ETA, and check
  the weather and cyclone picture along the way.
api: openapi/shipfinder-ais-data-api-openapi.yml
operations:
- getRoutePlanPortToPort
- getRoutePlanPointToPoint
- getETA
- getMarineWeather
- getCyclonesList
- getCycloneInfo
- getTideStationList
- getTideStationInfo
generated: '2026-08-09'
method: generated
source: openapi/shipfinder-ais-data-api-openapi.yml, conventions/shipfinder-ais-data-api-conventions.yml,
  errors/shipfinder-ais-data-api-error-codes.yml
---

# Plan a voyage and predict arrival

## When to use this skill

The user wants a route, a distance, an arrival estimate, or the environmental picture on a voyage leg.

## Steps

1. **Plan the route** — for a port pair call `getRoutePlanPortToPort`
   (`GET /v1/Prediction/RoutePlanPortToPort`) with `start_port_code` and `end_port_code`. For arbitrary
   coordinates call `getRoutePlanPointToPoint` (`GET /v1/Prediction/RoutePlanPointToPoint`) with
   `start_point` and `end_point`.
2. **Constrain the route** — both operations take `avoid` and `through` parameters that reference deviation
   nodes (Suez Canal, Panama Canal, Malacca Strait, Cape of Good Hope, …). Resolve the numeric ids from the
   `deviation_node` list in `vocabulary/shipfinder-ais-data-api-vocabulary.yml`. Never guess an id.
3. **Predict arrival** — call `getETA` (`GET /v1/Prediction/ETA`) with the vessel and destination. ETA is
   computed from the vessel's real-time speed, so it moves as the vessel's speed moves; re-query rather than
   caching it.
4. **Check conditions** — call `getMarineWeather` (`GET /v1/Meteorology/MarineWeather`) at a `lng`/`lat` and
   `weather_time` for wind, wave, current and visibility. Marine weather is a premium dataset.
5. **Check tropical cyclones** — call `getCyclonesList` (`GET /v1/Meteorology/CyclonesList`) for active
   systems, then `getCycloneInfo` (`GET /v1/Meteorology/CycloneInfo`) with `typhoon_id` for the track, wind
   radii and forecast cone of one system that threatens the route.
6. **Check tides at the destination** — `getTideStationList` (`GET /v1/Meteorology/TideStationList`) then
   `getTideStationInfo` (`GET /v1/Meteorology/TideStationInfo`) with `scode` for predicted tide heights, when
   draught or berthing windows matter.
7. **China coastline** — when the route touches Chinese waters, call `getNavigationalWarnings`
   (`GET /v1/Warning/NavigationalWarnings`) for official warnings and hazards.

## Failure handling

Read the envelope `status` first. `status: 100` means a required parameter is missing or malformed — check
that coordinates are WGS84 decimal degrees and that deviation-node ids came from the published table.
`status: 21` means a premium dataset (marine weather, warnings) is not enabled on the key.
