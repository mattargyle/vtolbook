# airsim — Overview

AirSim-based quadrotor simulation harness. Python code that talks to the
[Microsoft AirSim](https://microsoft.github.io/AirSim/) simulator to fly a
quadrotor under various controllers and trajectory generators, with hooks for
ROVIO-based visual-inertial estimation.

## Entry point

- `helloDrone.py` — minimal AirSim connection / takeoff sanity check.

## Subdirectories

- `controllers/` — flight controllers used with AirSim.
  - `jakes_controller.py`, `motor_lost_controller.py` and matching `test_*.py`
    drivers (the motor-lost variant handles single-motor-failure recovery).
- `dynamics/` — quadrotor dynamics models.
  - `quad_dynamics.py` (standard), `detailed_dynamics.py` (extended model),
    `test_dynamics.py` (driver).
- `trajectory_generators/` — reference trajectories fed to the controllers.
  - `circular_trajectory.py`, `circular_trajectory_new_frame.py`,
    `user_waypoints.py`, `pixel_to_ned.py` (image-pixel-to-NED projection),
    plus `altitude_map.png` used as a height field.
- `optical_flow/` — time-to-collision from optical flow.
  - `time_to_collision.py` + `test_TTC.py`.
- `viz/` — visualization helpers (`quad_viewer.py`).
- `message_types/` — dataclass-style messages shared across the package
  (`msg_state`, `msg_autopilot`, `msg_delta`, `msg_motor_commands`).
- `parameters/` — vehicle and simulation constants
  (`quadrotor_parameters.py`, `detalied_quadrotor_parameters.py` [sic],
  `simulation_parameters.py`).
- `tools/` — small math utilities (`rotations.py`, `wrap.py`,
  `dirty_derivative.py`).
- `rovio/` — ROVIO visual-inertial odometry integration: ROS launch file
  (`rovio_airsim_node.launch`), config (`rovio_airsim.info`,
  `airsim_camera.yaml`), AirSim settings (`settings.json`), and the Python
  bridge (`rovio_estimation.py`). See `readme.txt`.
- `settings/` — AirSim client `settings.json` (camera/vehicle config copied
  into `~/Documents/AirSim/`).

## Conventions

Modules import siblings via `sys.path.append('..')` from a script run inside
one of the leaf directories, matching the `quadrotorsim`/`holodecksim`
convention described in the repo's top-level `CLAUDE.md`.
