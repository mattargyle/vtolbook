# quadrotorsim/chap6 — Overview

Chapter 6: autopilot wrapped around the chap4 dynamics.

## Files

- `quadrotorsim_chap6.py` — entry point. Drives `QuadrotorDynamics` with
  `Autopilot` under a reference trajectory.
- `autopilot.py` — `Autopilot`: cascaded position / attitude / rate
  controllers, parameter values from `parameters.control_parameters`.
