# holodecksim/chap4 — Overview

Chapter 4: autopilot built from cascaded inner-loop controllers.

## Files

- `holodecksim_chap4.py` — entry point. Closes the loop around
  `multirotorDynamics` (from `chap3`) with an `autopilot`.
- `autopilot.py` — `autopilot` assembles `ctrlAngularRate`,
  `ctrlAttitudeSimple`, and `ctrlVelocity` (from `controllers.py`) into the
  cascade, with gains pulled from `parameters.control_parameters`.
- `controllers.py` — individual inner-loop controllers:
  `ctrlAngularRate` (torque on body rates), and the attitude / velocity
  controllers used by the autopilot.
