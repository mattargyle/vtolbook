# quadrotorsim/parameters — Overview

Module-level constants, imported as uppercase aliases (`SIM`, `QUAD`,
`CTRL`, `SENSOR`).

## Files

- `quadrotor_parameters.py` — vehicle physical parameters (mass, inertia,
  geometry, motor map).
- `old_quadrotor_parameters.py` — legacy parameter file kept for reference;
  not loaded by the current chapter sims.
- `control_parameters.py` — controller gains used by chap6's autopilot and
  the chap8 observers.
- `sensor_parameters.py` — noise / bias for the chap7 sensor models.
- `planner_parameters.py` — planner / path-manager configuration.
- `simulation_parameters.py` — timing: `ts_simulation`, `start_time`,
  `end_time`.
