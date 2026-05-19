# quadrotorsim/chap11 — Overview

Chapter 11: path manager that sequences a list of waypoints into the path
segments consumed by chap10's follower, including Dubins paths.

## Files

- `mavsim_chap11.py` — entry point.
- `path_manager.py` — `pathManager`: state-machine that walks the current
  `msgWaypoints` list, tracks `(ptr_previous, ptr_current, ptr_next)`,
  detects halfspace crossings (`halfspace_n`, `halfspace_r`), and emits the
  next `msgPath` to the follower. Flags `flag_need_new_waypoints` when the
  list is exhausted.
- `dubins_parameters.py` — `dubinsParameters`: geometric Dubins-path
  construction between two `(position, course)` configurations of a given
  turn radius. Imported by both `chap11/path_manager.py` and
  `chap12/rrt_dubins.py`.
- `waypoint_viewer.py` — 3D viewer that draws the waypoint list and the
  vehicle trace.
