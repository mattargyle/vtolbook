# quadrotorsim/projects — Overview

Standalone research projects that build on top of the chapter simulators,
rather than belonging to any single chapter. Each project lives in its own
subdirectory and bootstraps `sys.path` with `'../..'` so it can import the
top-level shared packages (`message_types`, `parameters`, `tools`, ...).

## Subdirectories

- `rapid_landing/` — quick-descent landing trajectory generated with
  B-splines and `scipy.optimize.minimize`. See its own `OVERVIEW.md`.
