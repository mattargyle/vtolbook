# quadrotorsim/projects/rapid_landing — Overview

Quick-descent landing trajectory generator and simulator. Plans a smooth
deceleration profile from cruise altitude to touchdown.

## Files

- `landing_trajectory.py` — `TrajectoryPlanner`: parameterizes the descent
  as a B-spline (`scipy.interpolate.BSpline`) and solves for control points
  with `scipy.optimize.minimize`. Outputs `MsgAutopilot` references (pos /
  vel / accel) at every control step.
- `quadrotorsim_rapid_landing.py` — entry point. Adds `'../..'` to
  `sys.path` and stitches together `chap2.QuadrotorViewer`,
  `chap3.DataViewer`, `chap4.QuadrotorDynamics`, `chap6.Autopilot`, and the
  local `TrajectoryPlanner` into a single closed-loop run.
