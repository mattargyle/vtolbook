# quadrotorsim/chap7 — Overview

Chapter 7: sensor models. This chapter (and the next several) is inherited
from the fixed-wing `mavsim` lineage — hence the `mavsim_chapN.py` /
`mav_dynamics.py` names rather than `quadrotor*`.

## Files

- `mavsim_chap7.py` — entry point. Runs dynamics + autopilot and pumps the
  resulting state through the sensor models.
- `mav_dynamics.py` — dynamics class with sensor outputs (`MsgSensors`)
  layered on top of the rigid-body model.
- `sensor_viewer.py` — PyQtGraph viewer for the synthetic sensor signals.
