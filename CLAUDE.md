# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository contents

This repo holds the LaTeX source of the VTOL book (*Vision-Based Estimation and Control of Multirotor and Winged-VTOL Systems* by R. Beard) alongside several Python simulators used in the book and for related research. There is no package manifest, build script, lint config, or test suite — each simulator is a collection of scripts run directly with Python, and the book is built with `latexmk`/`pdflatex`.

## Top-level layout

- `textbook/` — LaTeX source. Master file is `textbook/vtolbook.tex`, which uses the local `tufte-book` class (`tufte-book.cls`, `tufte-common.def`, plus the upstream copy in `textbook/tufte-latex-master/`). Each chapter lives in its own `chapN_<topic>/` directory and is `\include`d from `vtolbook.tex`. Bibliography is split across `library_Beard.bib` and `library_Jackson.bib`; shared macros are in `macros.tex`. Build from inside `textbook/` (e.g. `pdflatex vtolbook.tex` then `bibtex vtolbook` then two more `pdflatex` passes, or `latexmk -pdf vtolbook.tex`). `*.toc/*.aux/*.log/...` and `vtolbook.pdf` are gitignored. To compile a single chapter while iterating, uncomment the relevant `\includeonly{...}` line near the top of `vtolbook.tex`.
- `quadrotorsim/` — Main Python simulator for the book. Standalone (uses PyQtGraph viewers, no external sim).
- `holodecksim/` — Variant simulator using BYU's Holodeck environment for visualization.
- `airsim/` — Variant simulator that talks to Microsoft AirSim over its Python client. `airsim/helloDrone.py` has a hard-coded `airsim_install` path that needs to be edited locally before it will run.
- `splines/` — Standalone utilities (currently just `bspline_basis.py`).

## Simulator architecture (quadrotorsim, holodecksim, airsim)

All three simulators follow the same chapter-driven pattern that mirrors the book's chapters; new code is normally added by copying the previous chapter's directory and extending it.

- Entry points are `chapN/<simname>_chapN.py` (e.g. `quadrotorsim/chap3/quadrotorsim_chap3.py`, `holodecksim/chap4/holodecksim_chap4.py`). They are scripts, not modules — run them from inside the `chapN/` directory so that the `sys.path.append('..')` at the top resolves the sibling packages. Several `chapN/mavsim_chapN.py` files in `quadrotorsim/` are inherited from the fixed-wing `mavsim` lineage.
- Each `chapN_*.py` follows the same shape: instantiate a viewer, a dynamics object, and a `MsgDelta` input; loop from `SIM.start_time` to `SIM.end_time` in steps of `SIM.ts_simulation`, updating dynamics then viewer.
- Shared packages (siblings of each `chapN/`):
  - `message_types/` — plain data classes that flow between blocks: `MsgState`, `MsgDelta` (control inputs), `MsgSensors`, `MsgAutopilot`, `MsgPath`, `MsgWaypoints`, `MsgMap`. These are the contracts between dynamics, controllers, planners, and viewers.
  - `parameters/` — module-level constants imported as `SIM`, `QUAD`/`SYS`, etc. `simulation_parameters.py` owns timing (`ts_simulation`, `start_time`, `end_time`); vehicle/sensor/control/planner parameters live in their own files.
  - `tools/` — math helpers (`rotations.py`, `wrap.py`, `dirty_derivative.py`, `transfer_function.py`, `signals.py`, `drawing.py`).
  - `viewers/` (quadrotorsim) or `chapN/*_viewer.py` (others) — PyQtGraph-based 3D and time-series plots; `video_writer.py` exists in each sim for optional recording.
- Chapter dependencies climb: chap3 introduces dynamics, chap4 adds an autopilot/controllers (`autopilot.py`, `controllers.py` in holodecksim), later chapters in `quadrotorsim/` (chap10–12) add path following, waypoint management, and RRT-based planners (`rrt_straight_line.py`, `rrt_dubins.py`, `dubins_parameters.py`). When working in a higher chapter, expect it to import the lower chapters' modules by relative path (`from chap3.quadrotor_dynamics import ...`).
- `quadrotorsim/state_plotter/` and `holodecksim/state_plotter/` are vendored copies of the same plotting library — keep them in sync if you change one.
- There is a stale `quadrotorsim/chap12/path_planner (Randy Beard's conflicted copy 2019-08-01).py` from a Dropbox conflict; the canonical file is `path_planner.py` in the same directory.

## Conventions to preserve

- Run simulator scripts from their own `chapN/` directory; do not "fix" the `sys.path.append('..')` idiom to package-style imports unless you are restructuring the whole sim, since every chapter relies on it.
- Parameters are imported as uppercase module aliases (`import parameters.simulation_parameters as SIM`) and referenced as `SIM.ts_simulation`, etc. Keep that style when adding new parameter files.
- Naming differs by sim: `quadrotorsim` uses PascalCase classes (`QuadrotorDynamics`, `MsgDelta`); `holodecksim` uses camelCase (`multirotorDynamics`, `msgDelta`). Match the surrounding file rather than unifying them.
