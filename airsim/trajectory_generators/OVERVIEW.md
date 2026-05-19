# airsim/trajectory_generators — Overview

Reference trajectories fed to the autopilot as `MsgAutopilot`
(position / velocity / acceleration).

## Files

- `circular_trajectory.py` — `TrajectoryGenerator` producing a planar circle
  with a sinusoidal vertical oscillation.
- `circular_trajectory_new_frame.py` — same idea, expressed in a different
  reference frame.
- `user_waypoints.py` — generator that interpolates between user-specified
  waypoints.
- `pixel_to_ned.py` — utility that converts image pixel coordinates and
  greyscale intensity from `altitude_map.png` into NED position + altitude
  (used to click-select destinations on the altitude map).
- `altitude_map.png` — greyscale heightfield used as input to
  `pixel_to_ned.py`.
