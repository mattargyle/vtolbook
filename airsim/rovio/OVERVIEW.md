# airsim/rovio — Overview

ROS / ROVIO visual-inertial-odometry integration. ROVIO consumes the AirSim
camera + IMU stream and publishes a state estimate that the Python harness
in `rovio_estimation.py` reads back.

See `readme.txt` for setup steps (symlinking the configs into a Catkin
workspace, copying `settings.json` into `~/Documents/AirSim/`).

## Files

- `airsim_camera.yaml` — camera calibration (intrinsics + distortion) in the
  format ROVIO expects.
- `rovio_airsim.info` — ROVIO runtime parameters tuned for the AirSim feed.
- `rovio_airsim_node.launch` — ROS launch file that starts ROVIO with the
  configs above.
- `settings.json` — AirSim client settings used while running ROVIO
  (distinct from `airsim/settings/settings.json`; the readme calls this out
  explicitly).
- `rovio_estimation.py` — Python entry point. Spins up `QuadDynamics`,
  `jakes_controller.Autopilot`, `circular_trajectory.TrajectoryGenerator`,
  and `quad_viewer.QuadViewer`, subscribes to ROVIO's state topic via
  `rospy`, and runs the closed-loop sim. Bootstraps `sys.path` so it can be
  invoked from this directory.
- `readme.txt` — setup instructions.
