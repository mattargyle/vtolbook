# holodecksim/chap2 — Overview

Chapter 2: hook the simulator up to the Holodeck environment and capture
video frames.

## Files

- `holodecksim_chap2.py` — entry point. Instantiates `holodeckWorld` and a
  `msgState` and drives the simulator loop. Run from inside this directory.
- `holodeck_world.py` — `holodeckWorld` wraps a `holodeck.make(...)` env
  (the `"UrbanCity-MaxDistance"` package by default) and exposes
  `update(state)` that pushes the current pose into the renderer.
- `video_writer.py` — optional frame recorder driven from the main loop.
