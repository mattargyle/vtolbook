# holodecksim/parameters — Overview

Module-level constants, imported as uppercase aliases (e.g.
`import parameters.multirotor_parameters as SYS`).

## Files

- `multirotor_parameters.py` — vehicle physical parameters (mass, inertia,
  geometry, motor mapping). Imported as `SYS`.
- `control_parameters.py` — controller gains used by `chap4/autopilot.py`
  (`Kp_angular_rate`, `Kp_attitude_simple`, `J`, etc.).
- `sensor_parameters.py` — noise / bias parameters for the sensor models.
- `planner_parameters.py` — planner / path-manager configuration.
- `simulation_parameters.py` — timing: `ts_simulation`, `start_time`,
  `end_time`.
