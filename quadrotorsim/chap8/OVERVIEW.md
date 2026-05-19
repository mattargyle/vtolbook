# quadrotorsim/chap8 — Overview

Chapter 8: state estimation. Multiple observer implementations are kept side
by side so the reader can compare them.

## Files

- `mavsim_chap8.py` — entry point.
- `filters.py` — building blocks. `alphaFilter` is a first-order low-pass
  (`y[k] = α·y[k-1] + (1-α)·u[k]`) used as a primitive throughout the
  observers.
- `observer.py` — chapter-baseline observer: combines gyro + accel + GPS via
  alpha filters and small EKF-like updates.
- `observer2.py` — variant that uses `tools.rotations.Euler2Rotation` for the
  attitude propagation.
- `observer_full.py` — full nonlinear observer; the only one that depends on
  `parameters.aerosonde_parameters` (a fixed-wing parameter file inherited
  from `mavsim`).
