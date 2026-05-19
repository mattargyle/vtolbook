# textbook — Overview

LaTeX source for the VTOL book. Built with the vendored Tufte-LaTeX class.

## Build

From this directory:

```
latexmk -pdf vtolbook.tex
```

`vtolbook.tex` is the master file; it pulls in `macros.tex`,
`table_of_contents.tex`, `contributors.tex`, and each chapter's `.tex` file.

## Top-level files

- `vtolbook.tex` — book entry point.
- `macros.tex` — shared math/typesetting macros.
- `table_of_contents.tex`, `contributors.tex` — front matter.
- `library_Beard.bib`, `library_Jackson.bib`, `refs_tmp.bib` — bibliographies.
- `tufte-book.cls`, `tufte-common.def`, `tufte.bst` — Tufte class files used
  by the build (vendored copies, kept alongside the source).
- `Quad Rotorcraft Control - Chapters 5-7.pdf` — reference PDF.
- `outline of course.rtf`, `to do.rtf`, `student_projects_book.xlsx` — author
  notes and tracking, not part of the build.

## Chapters

Each chapter has its own directory with a `.tex` source, a `figures/`
subdirectory, and (where applicable) a `papers/` subdirectory of supporting
PDFs:

- `chap1_intro/` — introduction.
- `chap2_preliminaries/` — math preliminaries (rotations, kinematics);
  includes `papers/transformations_jackson/` with figures.
- `chap3_multirotor/` — multirotor modeling and control.
- `chap4_trajectory_following/` — trajectory-following control.
- `chap5_trajectory_planning/` — planning; includes an `Astar planning/`
  writeup, a `splines/` workspace with `collision_avoidance/`, and a
  `matlab_old/` archive.
- `chap6_camera_features/` — camera models and features.
- `chap7_optical_flow/` — optical flow; includes
  `Roger Black IMU Aided KLT/` (with a `python/` reference implementation
  carrying its own README).
- `chap8_scene_reconstruction/` — scene reconstruction.
- `chap9_visual_servoing/` — visual servoing.
- `chap10_tracking/` — target tracking; includes a `2018 Target Following/`
  conference-paper source tree.
- `chap11_attitude_estimation/` — attitude estimation.
- `chap12_trajectory_estimation/` — trajectory estimation.
- `chap13_visual_odometry/` — visual odometry; includes an `odometry_old/`
  archive.
- `chap14_slam/` — SLAM.

## Other directories

- `contributors/` — per-contributor assets.
- `matlab_visualization/` — MATLAB plotting utilities (plus a `junk/` scratch
  folder).
- `tufte-latex-master/` — vendored upstream Tufte-LaTeX distribution. Treat as
  read-only third-party content; only the class files at the textbook root
  are actually loaded by the build.
