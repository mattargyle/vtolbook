# airsim/tools — Overview

Math helpers shared across controllers, dynamics, and optical-flow code.

## Files

- `rotations.py` — rotation / quaternion utilities: `rotation_to_quaternion`,
  `quaternion_to_rotation`, `hat`, `vee`, `logR`, `leftJacobianInv`,
  `quat_hat`.
- `wrap.py` — angle wrapping for SO(2) measurements / setpoints.
- `dirty_derivative.py` — `DirtyDerivative`, a first-order low-pass
  derivative filter used wherever numeric differentiation is needed.
