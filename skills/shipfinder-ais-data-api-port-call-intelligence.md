---
name: Build port call intelligence for a port
description: Look up a port, list what is berthed, anchored and inbound right now,
  and pull its historical port-call record.
api: openapi/shipfinder-ais-data-api-openapi.yml
operations:
- getPortInfo
- getPortBerthedVessels
- getPortAnchoredVessels
- getPortExpectedArrivals
- getPortCallRecordsByPort
generated: '2026-08-09'
method: generated
source: openapi/shipfinder-ais-data-api-openapi.yml, conventions/shipfinder-ais-data-api-conventions.yml,
  errors/shipfinder-ais-data-api-error-codes.yml
---

# Build port call intelligence for a port

## When to use this skill

The user asks what is happening at a port — congestion, who is alongside, who is arriving, how busy it has
been.

## Before you start

- Ports are addressed by UN/LOCODE in the `port_code` parameter (for example `SGSGP`, `CNSHA`).
- Auth, base URL and the `{status, msg, data}` envelope rules are the same as every other ShipFinder call.

## Steps

1. **Resolve the port** — call `getPortInfo` (`GET /v1/Voyage/PortInfo`) to confirm the UN/LOCODE, name,
   coordinates and time zone before you query anything else. A wrong `port_code` returns envelope status 3,
   and a port outside your entitlement returns status 27.
2. **Read the current picture** — call `getPortBerthedVessels` (`GET /v1/Voyage/PortBerthedVessels`) for
   vessels alongside and `getPortAnchoredVessels` (`GET /v1/Voyage/PortAnchoredVessels`) for vessels waiting
   at anchor. The ratio of anchored to berthed is the congestion signal.
3. **Look forward** — call `getPortExpectedArrivals` (`GET /v1/Voyage/PortExpectedArrivals`) for inbound
   vessels with predicted ETA. This is a premium dataset: without entitlement it returns envelope status 21.
4. **Look back** — call `getPortCallRecordsByPort` (`GET /v1/History/PortCallRecordsByPort`) with
   `start_time`/`end_time` for arrivals and departures over a window. The default entitlement is the latest
   month; longer history must be enabled on the key.
5. **Set the time base** — several of these operations accept `time_zone`. Set it explicitly, or state in your
   answer that timestamps are UTC epoch seconds. Do not mix the two.

## Failure handling

Same envelope-first rules as every ShipFinder skill: `status: 21` means the dataset is not enabled on the key
(stop, do not retry), `status: 27` means the port is outside the entitled port set, `status: 12` and
`status: 30` mean the request asked for more data than the key is allowed to pull in one call — narrow the
time window rather than retrying.
