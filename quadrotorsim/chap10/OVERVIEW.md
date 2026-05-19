# quadrotorsim/chap10 — Overview

Chapter 10: path following. Takes a `msgPath` (line, orbit, fillet) and
generates the autopilot reference that drives the vehicle along it.

## Files

- `mavsim_chap10.py` — entry point. Closes the loop around
  dynamics + observer + autopilot + `pathFollower`.
- `path_follower.py` — `pathFollower`: converts a `msgPath` into an
  autopilot command.
- `path_viewer.py` — 3D PyQtGraph viewer that draws both the path and the
  vehicle.
