# quadrotorsim/chap4 — Overview

Chapter 4: trajectory-following dynamics. Extends the chap3 dynamics with
whatever additional inputs / outputs the chapter requires.

## Files

- `quadrotorsim_chap4.py` — entry point.
- `quadrotor_dynamics.py` — chapter-local copy of `QuadrotorDynamics`. The
  chapters keep their own copies so each one can stand alone and so the
  reader can diff against the previous chapter; chap4 is the version
  introduced with the trajectory-following material.
