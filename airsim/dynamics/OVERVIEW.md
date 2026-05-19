# airsim/dynamics — Overview

Equations of motion for the quadrotor. State uses a unit quaternion for
attitude.

## Files

- `quad_dynamics.py` — `QuadDynamics`, the standard 6-DOF rigid-body model.
  Imports parameters via `parameters.quadrotor_parameters` and rotation
  helpers from `tools.rotations`.
- `detailed_dynamics.py` — extended model that adds motor / actuator dynamics
  on top of `QuadDynamics`. Includes a `__main__`-time `sys.path` bootstrap so
  the file can also be run from inside `dynamics/`.
- `test_dynamics.py` — driver that integrates the dynamics in isolation
  (no AirSim, no controller) for sanity checking.
