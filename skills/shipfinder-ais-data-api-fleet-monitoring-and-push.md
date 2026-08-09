---
name: Monitor a fleet and receive push events
description: Create a monitored fleet, bind vessels to it, and subscribe to ShipFinder
  push events for position, arrival/departure, ETA, AIS signal loss and ship-to-ship
  activity.
api: openapi/shipfinder-ais-data-api-openapi.yml
operations:
- postAddFleet
- getFleet
- postUpdateFleetInfo
- postAddVesselToFleet
- postUpdateFleetVessel
- postDeleteFleetVessel
- postDeleteFleet
generated: '2026-08-09'
method: generated
source: openapi/shipfinder-ais-data-api-openapi.yml, conventions/shipfinder-ais-data-api-conventions.yml,
  errors/shipfinder-ais-data-api-error-codes.yml
---

# Monitor a fleet and receive push events

## When to use this skill

The user wants standing monitoring rather than a one-off query: "tell me when any of these ships arrives",
"alert me if a vessel goes dark".

## Before you start

- These are the write operations. They are `POST` with a JSON body, and the API key travels as a `key`
  property **in the body**, not as a query parameter.
- Push delivery is a premium capability. The receiving URL is configured by a human in the ShipFinder console
  (Fleet & Areas → Webhook URL Management) — there is no API for it. Confirm the URL is live and configured
  before creating the fleet, or events will be generated and dropped.
- There is no idempotency key. A repeated `postAddFleet` creates a second fleet. Check with `getFleet` first.

## Steps

1. **Check for an existing fleet** — call `getFleet` (`GET /v1/Event/GetFleet`) before creating anything.
2. **Create the fleet** — call `postAddFleet` (`POST /v1/Event/AddFleet`) with `fleet_name`, a comma-separated
   `mmsis` list, and `monitor`. `monitor` is a comma-separated list of the push types to enable:
   `1` fleet vessel query, `2` real-time position push, `3` arrival/departure push, `4` dynamic ETA push,
   `5` AIS abnormal event push, `6` geofence monitoring push, `7` vessel alongside (STS) push. Each type
   requires its own permission on the key; asking for one you do not hold fails the whole call.
3. **Maintain membership** — `postAddVesselToFleet` (`POST /v1/Event/AddVesselToFleet`) to add,
   `postUpdateFleetVessel` (`POST /v1/Event/UpdateFleetVessel`) to replace the list in bulk,
   `postDeleteFleetVessel` (`POST /v1/Event/DeleteFleetVessel`) to remove. Binding beyond the vessel quota on
   the key fails — the quota is per key, not per fleet.
4. **Rename or retarget** — `postUpdateFleetInfo` (`POST /v1/Event/UpdateFleetInfo`).
5. **Tear down** — `postDeleteFleet` (`POST /v1/Event/DeleteFleet`).
6. **Receive the events** — ShipFinder POSTs JSON to your configured URL. The seven documented event payloads
   are catalogued in `asyncapi/shipfinder-ais-data-api-webhooks.yml` and described as AsyncAPI in
   `asyncapi/shipfinder-ais-data-api-events-asyncapi.yml`. Position and ETA pushes arrive every 10 minutes;
   AIS signal-loss fires after 15 minutes without a report; STS fires after 5 minutes of side-by-side
   behaviour.

## Security note for the receiving endpoint

ShipFinder documents **no webhook signature, no retry policy and no replay protection**. Treat the receiving
endpoint as unauthenticated input: validate every payload against the published schema, deduplicate on
`mmsi` + `event_time`, and do not take irreversible action on a single unverified push.
