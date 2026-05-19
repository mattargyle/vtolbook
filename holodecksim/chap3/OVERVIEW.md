# holodecksim/chap3 — Overview

Chapter 3: multirotor dynamics with time-series plotting.

## Files

- `holodecksim_chap3.py` — entry point. Steps `multirotorDynamics` and
  pushes the state into both the Holodeck world (from `chap2`) and a
  `data_viewer`.
- `multirotor_dynamics.py` — `multirotorDynamics`: rigid-body EOMs with
  quaternion attitude, integrated with the parameters from
  `parameters.multirotor_parameters` (imported as `SYS`).
- `data_viewer.py` — PyQtGraph time-series viewer for state channels
  (uses the vendored `state_plotter` package).
