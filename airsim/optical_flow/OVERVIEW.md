# airsim/optical_flow — Overview

Time-to-collision estimation from sparse optical flow on the AirSim camera
feed.

## Files

- `time_to_collision.py` — `TimeToCollision`: tracks corner features with
  `cv2.goodFeaturesToTrack` + Lucas-Kanade (`cv2.calcOpticalFlowPyrLK`),
  uses `DirtyDerivative` for flow derivatives and the camera intrinsics
  from `parameters.quadrotor_parameters.K_inv` to recover TTC.
- `test_TTC.py` — driver script that pipes AirSim images through
  `TimeToCollision`.
