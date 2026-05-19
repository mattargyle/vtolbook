# holodecksim/message_types — Overview

Inter-block message classes. Names are camelCase (`msgState`, `msgDelta`,
...), matching the holodecksim convention (`quadrotorsim` uses PascalCase
equivalents).

## Files

- `msg_state.py` — `msgState`: current vehicle state (position, velocity,
  attitude, body rates).
- `msg_delta.py` — `msgDelta`: control input fed to dynamics.
- `msg_autopilot.py` — reference inputs (position / velocity / acceleration)
  consumed by the autopilot.
- `msg_sensors.py` — sensor readings produced by the sensor models.
- `msg_path.py` — single path segment for the follower.
- `msg_waypoints.py` — waypoint list emitted by the planner / consumed by
  the manager.
- `msg_map.py` — map representation used by the planner.
