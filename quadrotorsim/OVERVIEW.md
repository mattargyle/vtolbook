# quadrotorsim — Overview

Pure-Python quadrotor / VTOL simulator, organized by textbook chapter. This is
the simulator referenced throughout `vtolbook`. Each `chapN/` directory
contains a runnable script that exercises the material from that chapter.

> The pre-existing `README.md` describes this as "vtolsim — Python simulator
> to be used with vtolbook and other research projects."

## Chapter simulators

- `chap3/` — quadrotor dynamics.
  - `quadrotorsim_chap3.py`, `quadrotor_dynamics.py`, `data_viewer.py`.
- `chap4/` — trajectory-following dynamics.
  - `quadrotorsim_chap4.py`, `quadrotor_dynamics.py`.
- `chap6/` — autopilot.
  - `quadrotorsim_chap6.py`, `autopilot.py`.
- `chap7/` — sensor models + MAV dynamics.
  - `mavsim_chap7.py`, `mav_dynamics.py`, `sensor_viewer.py`.
- `chap8/` — state estimation / observers.
  - `mavsim_chap8.py`, `filters.py`, `observer.py`, `observer2.py`,
    `observer_full.py`.
- `chap10/` — path following.
  - `mavsim_chap10.py`, `path_follower.py`, `path_viewer.py`.
- `chap11/` — path manager and Dubins paths.
  - `mavsim_chap11.py`, `path_manager.py`, `dubins_parameters.py`,
    `waypoint_viewer.py`.
- `chap12/` — path planning (straight-line and Dubins RRT).
  - `mavsim_chap12.py`, `path_planner.py`, `rrt_straight_line.py`,
    `rrt_dubins.py`, `world_viewer.py`. A `path_planner (Randy Beard's
    conflicted copy 2019-08-01).py` is left in place as a historical artifact.

Run each simulator from inside its chapter directory; modules reach siblings
via `sys.path.append('..')`.

## Shared packages

- `message_types/` — inter-module messages (`msg_state`, `msg_autopilot`,
  `msg_delta`, `msg_sensors`, `msg_path`, `msg_waypoints`, `msg_map`).
- `parameters/` — vehicle, control, sensor, planner, and simulation
  parameter modules (`old_quadrotor_parameters.py` is the legacy variant).
- `tools/` — math/signal helpers: `rotations.py`, `wrap.py`, `signals.py`,
  `transfer_function.py`, `drawing.py`, `dirty_derivative.py`.
- `viewers/` — 3D viewers for the VTOL airframe: `vtol_viewer.py`,
  `vtolsim_viewer.py`, `draw_vtol.py`, `video_writer.py`.
- `state_plotter/` — vendored time-series plotting utility (also present in
  `holodecksim/`).

## Projects

- `projects/rapid_landing/` — quick-descent landing trajectory work:
  `quadrotorsim_rapid_landing.py` + `landing_trajectory.py`.

## Archive

- `quadrotorsim_old/` — earlier copy of the whole simulator (including its own
  `chapN/`, `state_plotter/`, `rapid_landing/`, and README). Kept for
  reference; new work should go in the top-level structure above.
