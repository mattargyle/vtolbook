# airsim/message_types — Overview

Plain dataclass-style messages passed between dynamics, controllers,
trajectory generators, and viewers. Class names are PascalCase
(`MsgState`, `MsgDelta`), matching `quadrotorsim`.

## Files

- `msg_state.py` — `MsgState`: inertial position, velocity, rotation matrix
  / quaternion, and body rates. The canonical "current state" passed to every
  block.
- `msg_delta.py` — `MsgDelta`: control input (forces / torques / collective
  + body-rate setpoints).
- `msg_motor_commands.py` — alternate per-motor command message used by
  `controllers/motor_lost_controller.py`.
- `msg_autopilot.py` — reference signals (position, velocity, acceleration)
  fed by trajectory generators into the autopilot.
