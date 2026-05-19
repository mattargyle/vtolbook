# quadrotorsim/chap3 — Overview

Chapter 3: open-loop quadrotor dynamics with a time-series viewer.

## Files

- `quadrotorsim_chap3.py` — entry point. Steps `QuadrotorDynamics` under a
  scripted `MsgDelta` input and plots the response in a `DataViewer`.
- `quadrotor_dynamics.py` — `QuadrotorDynamics`: 6-DOF rigid-body model
  (quaternion attitude) integrated with parameters from
  `parameters.quadrotor_parameters` (imported as `QUAD`).
- `data_viewer.py` — PyQtGraph time-series viewer (built on the vendored
  `state_plotter`).
