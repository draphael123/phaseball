# PHASEBALL

A **Super Monkey Ball-style** tilt-the-world marble game with an **Outrun synthwave** skin.
You don't steer the marble — you **tilt the whole stage** and let real gravity roll it home:
stay on the course through ramps, hills, turns and narrow bridges, grab the **bananas**, and
reach the goal before the clock. Built on a real physics core (cannon-es).

**Play:** https://phaseball.vercel.app *(updates automatically on every push)*

## How it works
Gravity is constant and points straight down; your input tilts it, and the whole stage is
**rendered rotated** so it looks like the board tilts with a level horizon. That's mathematically
a tilting stage but rock-solid in physics — the ball rolls, never launches. Rolling is a real
cannon-es rigid-body sphere on 3D course geometry (pads + matched-seam ramps).

## Features
- **5 rolling courses** — DESCENT, THE BEND, ROLLERCOASTER, THE NARROWS, SWITCHBACK — each a
  per-stage synthwave theme (banded-sun sky, neon grid, chrome marble with a face).
- **Visuals** — bloom + ACES tone mapping, VHS scanlines, PMREM reflections, dust, particle
  bursts/confetti. Post-processing loads from CDN with a plain-render fallback.
- **Audio** — synthesized in-browser: speed-tracked rolling rumble, banana chimes, clear/win
  fanfares, fall sting, countdown, and a looping music bed. Drop a CC0 loop at
  [`assets/music.ogg`](assets/) to replace the synth. Mute with **M** / 🔊.
- **The Circuit** — a dry, smug narrator reacting to your runs (edit the `QUIPS` bank).
- **Scoring & medals** — time + medal (🥇/🥈/🥉) + full-banana bonuses; per-stage best times
  and a results board.
- **Garage (🎨)** — earn **stars** from medals/bananas to unlock marble **colors** (incl. an
  animated Rainbow) and **hats**.
- **Settings (⚙ / Esc)** — music/SFX volume, screen shake, retro filter, performance mode.
- **Level select** on the title; **attract**-style title screen.
- **Mobile** — on-screen tilt stick + restart, performance mode auto-on for touch.

## Controls
- **W / A / S / D** or **arrow keys** — tilt the stage
- **R** — restart stage &nbsp;·&nbsp; **M** — mute &nbsp;·&nbsp; **Esc** — settings
- Mobile: on-screen stick + restart (auto-detected)

## Tech
Single file, no build step. [`index.html`](index.html) is the whole game. Three.js (rendering)
and cannon-es (physics) load from CDN via importmap.

- **Levels** are pure data in the `LEVELS` array — each `build()` lays out `pad()`s, `ramp()`s,
  `banana()`s and a `goal()`, plus `par` and `medals:{g,s,b}`. Keep pads overlapping so the
  course has no gaps. Add a stage by adding an object.
- **Feel** is tuned via `TUNE` (gravity, max tilt, tilt easing).
- **Personality** lives in the `QUIPS` bank, the `Audio` module, and the `COLORS`/`HATS` tables.

## Editing on your phone
1. Open this repo in the GitHub app (or github.com), open `index.html`, tap the pencil ✏️.
2. Tweak a number in `TUNE` or `LEVELS`, **Commit changes**.
3. Vercel auto-deploys in ~30s — refresh to see it live.
