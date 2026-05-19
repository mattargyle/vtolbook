# holodecksim/tools — Overview

Math and signal helpers used across the simulator.

## Files

- `rotations.py` — rotation / quaternion conversions, `hat`, `vee`, `skew`,
  Euler-rotation utilities.
- `wrap.py` — angle wrapping.
- `signals.py` — reference signal generators (steps, ramps, sinusoids).
- `transfer_function.py` — discrete `transferFunction` class used inside the
  autopilot for filters / compensators.
- `drawing.py` — 3D drawing helpers used by the viewers.
