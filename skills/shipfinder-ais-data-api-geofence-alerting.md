---
name: Geofence a sea area and alert on entry and exit
description: Create a monitored geographic area with a vessel filter, and receive
  entry/exit push events for it.
api: openapi/shipfinder-ais-data-api-openapi.yml
operations:
- postAddGeofence
- getGeofence
- postUpdateGeofence
- deleteGeofence
- getVesselsInZone
- getVesselsNearby
generated: '2026-08-09'
method: generated
source: openapi/shipfinder-ais-data-api-openapi.yml, conventions/shipfinder-ais-data-api-conventions.yml,
  errors/shipfinder-ais-data-api-error-codes.yml
---

# Geofence a sea area and alert on entry and exit

## When to use this skill

The user wants to know when any vessel — or a specific class of vessel, or their own fleet — enters or leaves
a defined sea area.

## Steps

1. **Look at the area first** — call `getVesselsInZone` (`GET /v1/AIS/VesselsInZone`) for a one-off snapshot
   of who is inside a polygon right now, or `getVesselsNearby` (`GET /v1/AIS/VesselsNearby`) for a radius
   around a coordinate. If the user only wants a snapshot, stop here; do not create a geofence.
2. **Create the geofence** — call `postAddGeofence` (`POST /v1/Event/AddGeofence`) with the area geometry, a
   name and a vessel filter (all vessels / by `ship_type` / restricted to one of your fleets). Filtering to a
   fleet requires the fleet to exist first — see the fleet monitoring skill.
3. **List and verify** — call `getGeofence` (`GET /v1/Event/GetGeofence`) and keep the returned `area_id`;
   every push event carries it.
4. **Adjust** — `postUpdateGeofence` (`POST /v1/Event/UpdateGeofence`); remove with `deleteGeofence`
   (`DELETE /v1/Event/DeleteGeofence`).
5. **Receive entry/exit events** — ShipFinder POSTs the geofence event to your receiving URL with
   `event_type` `1` = area entry, `2` = area exit, `3` = suspected area crossing, plus `area_id`, `area_name`,
   vessel identity and `event_time` (UTC epoch seconds). A zone-level webhook URL, configured on the
   individual area in the console, takes priority over the account-level URL — use that when different areas
   must reach different systems.

## Failure handling

`status: 16` means a regional vessel query fell outside the area you are permitted to query. `status: 21`
means geofence push is not enabled on the key. Treat `event_type: 3` (suspected crossing) as lower confidence
than `1`/`2` and do not act on it alone.
