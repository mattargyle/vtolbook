# quadrotorsim/chap12 — Overview

Chapter 12: path planning with Rapidly-exploring Random Trees (RRT). Sits on
top of chap11's path manager and chap10's path follower.

## Files

- `mavsim_chap12.py` — entry point. Plans → manages → follows.
- `path_planner.py` — `pathPlanner`: top-level wrapper that instantiates both
  RRT variants and dispatches to the requested one.
- `rrt_straight_line.py` — `rrtStraightLine`: RRT producing fillet-type
  waypoints (`segment_length = 300`).
- `rrt_dubins.py` — `rrtDubins`: RRT that grows the tree using Dubins paths
  (`segment_length = 500`); depends on `chap11.dubins_parameters`.
- `world_viewer.py` — 3D viewer for the planning world (obstacles, tree,
  chosen path).
- `path_planner (Randy Beard's conflicted copy 2019-08-01).py` — stale
  Dropbox conflict file; ignore it. The canonical implementation is
  `path_planner.py`.
