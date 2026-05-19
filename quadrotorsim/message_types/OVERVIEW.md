# quadrotorsim/message_types — Overview

Inter-block message classes. Class names are PascalCase
(`MsgState`, `MsgDelta`, ...), distinguishing them from holodecksim's
camelCase variants.

## Files

- `msg_state.py` — `MsgState`: current vehicle state (position, velocity,
  attitude, body rates).
- `msg_delta.py` — `MsgDelta`: control input to dynamics.
- `msg_autopilot.py` — autopilot reference (position / velocity /
  acceleration).
- `msg_sensors.py` — sensor outputs from chap7+ dynamics models.
- `msg_path.py` — `msgPath`: single path segment for the follower.
- `msg_waypoints.py` — `msgWaypoints`: waypoint list emitted by planners.
- `msg_map.py` — world / obstacle map used by chap12.
