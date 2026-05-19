# airsim/viz — Overview

AirSim-side visualization.

## Files

- `quad_viewer.py` — `QuadViewer`: thin wrapper around
  `airsim.VehicleClient`. Each `update(state)` call converts a `MsgState`
  into a pose (via `tools.rotations.rotation_to_quaternion`) and forwards it
  to AirSim with `simSetVehiclePose`, so the on-screen vehicle tracks the
  Python-side dynamics.
