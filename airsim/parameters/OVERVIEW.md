# airsim/parameters — Overview

Module-level constants. Imported as uppercase aliases:

```python
import parameters.simulation_parameters as SIM
import parameters.quadrotor_parameters as QUAD
```

then referenced as `SIM.ts_simulation`, `QUAD.mass`, etc.

## Files

- `quadrotor_parameters.py` — vehicle physical parameters (mass, inertia,
  motor map) and derived quantities including the camera-intrinsics inverse
  `K_inv` used by the optical-flow code.
- `detalied_quadrotor_parameters.py` — extended parameter set consumed by
  `dynamics/detailed_dynamics.py` (filename typo preserved to match imports).
- `simulation_parameters.py` — timing: `ts_simulation`, `start_time`,
  `end_time`, and any timing-related constants.
