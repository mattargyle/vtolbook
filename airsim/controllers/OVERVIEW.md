# airsim/controllers — Overview

Flight controllers used to drive the AirSim quadrotor. Each controller exposes
an `Autopilot` class with an `update(...)` method that consumes
`MsgState` / `MsgAutopilot` and produces a `MsgDelta` (or per-motor commands).

## Files

- `jakes_controller.py` — `Autopilot` using continuous-time LQR
  (`scipy.linalg.solve_continuous_are`) for position and attitude tracking,
  with a `DirtyDerivative` on position error and an integrator term.
- `motor_lost_controller.py` — `Autopilot` variant for the motor-failure case.
  Builds a reduced LQR (single-axis Q/R) and outputs motor commands via
  `MsgDelta` from `message_types.msg_motor_commands`.
- `test_jakes_controller.py` — standalone driver that exercises
  `jakes_controller` in closed loop.
- `test_motor_lost_controller.py` — driver for the motor-lost controller.
