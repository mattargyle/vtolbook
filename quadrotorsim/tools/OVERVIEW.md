# quadrotorsim/tools — Overview

Math and signal helpers used across every chapter.

## Files

- `rotations.py` — rotation / quaternion conversions and SO(3) utilities
  (`euler_to_rotation`, `rotation_to_quaternion`, `hat`, `vee`,
  `Euler2Rotation`, ...).
- `wrap.py` — angle wrapping for SO(2) measurements.
- `signals.py` — reference signal generators (step / ramp / sinusoid).
- `transfer_function.py` — discrete-time `transferFunction` class used inside
  the autopilot and observers as filters / compensators.
- `drawing.py` — 3D drawing helpers used by the viewers (`drawWaypoints`,
  `drawMap`, ...).
- `dirty_derivative.py` — first-order low-pass derivative filter.
