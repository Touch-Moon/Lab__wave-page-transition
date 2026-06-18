# Lab — Wave Page Transition

A page transition that keeps the thumbnail you clicked: it **freezes on its
current frame**, a **travelling wave** sweeps left→right across it, then a
**curtain** wipes up to reveal the next page sliding in from below. Extracted
from creative-moon.com's own navigation.

**▶ Live:** https://lab-wave-page-transition.creative-moon.com
**Write-up:** https://www.creative-moon.com/stories/wave-page-transition

Single self-contained `index.html` — vanilla JS + Canvas 2D, no build, no
dependencies (fonts via CDN).

## How it works

1. **Freeze** — the clicked thumbnail is cloned onto a `<canvas>` at its exact
   on-screen frame (works for a playing video too — `drawImage` doesn't read
   pixels back, so it's cross-origin safe).
2. **Wave** — a Gaussian-windowed sine travels across the frame, displacing
   image columns vertically (column-slice `drawImage`).
3. **Curtain** — the frame rises to the top, a `clip-path` curtain wipes
   bottom→top, and the next page slides up from `100svh`.

## Controls

A live **control panel** (top-right) tunes every step: wave amplitude, spread,
cycles, speed, rise duration, curtain duration — plus **Replay**.

## Run

Open `index.html` in a browser — fully static.
