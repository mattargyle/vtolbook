# holodecksim — Overview

[Holodeck](https://github.com/BYU-PCCL/holodeck)-based multirotor simulator,
organized by textbook chapter. Each `chapN/` directory holds the runnable
simulator for that chapter, building on the previous one.

## Chapter simulators

- `chap2/` — world setup and video capture.
  - `holodecksim_chap2.py` (entry point), `holodeck_world.py` (world wrapper),
    `video_writer.py`.
- `chap3/` — multirotor dynamics + state plotting.
  - `holodecksim_chap3.py`, `multirotor_dynamics.py`, `data_viewer.py`.
- `chap4/` — autopilot and inner-loop controllers.
  - `holodecksim_chap4.py`, `autopilot.py`, `controllers.py`.

Run each simulator from inside its chapter directory; modules reach siblings
via `sys.path.append('..')`.

## Shared packages

- `message_types/` — inter-module messages: `msg_state`, `msg_autopilot`,
  `msg_delta`, `msg_sensors`, `msg_path`, `msg_waypoints`, `msg_map`.
- `parameters/` — multirotor, control, sensor, planner, and simulation
  parameter modules.
- `tools/` — math/signal helpers: `rotations.py`, `wrap.py`, `signals.py`,
  `transfer_function.py`, `drawing.py`.
- `state_plotter/` — vendored time-series plotting utility (`Plotter.py`,
  `state_data.py`, `state_plot.py`, `state_plotbox.py`, `plotter_args.py`)
  with a `test/` subfolder.
