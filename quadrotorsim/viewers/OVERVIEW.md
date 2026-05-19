# quadrotorsim/viewers — Overview

PyQtGraph-based 3D viewers for the winged VTOL airframe.

## Files

- `draw_vtol.py` — `DrawVtol`: builds the airframe mesh from a `MsgState`
  and adds it to a `GLViewWidget`.
- `vtol_viewer.py` — `VtolViewer`: thin wrapper that creates the Qt app,
  the view widget, and a `DrawVtol` instance, exposing an `update(state)`
  call.
- `vtolsim_viewer.py` — scripted demo that wires `VtolViewer` to a
  `MsgState` driven from `parameters.simulation_parameters` — useful for
  sanity-checking the rendering without running a full chapter sim.
- `video_writer.py` — optional frame recorder.
