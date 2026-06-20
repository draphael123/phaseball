# PHASEBALL

A tilt-the-world marble game (Super Monkey Ball-style) with a **phase-through-walls** twist.
You don't steer the marble — you tilt the world and let gravity roll it home. Cyan walls
block you; **magenta phase-walls** can be passed through by going intangible for a moment,
but charges are limited per stage.

The presentation leans **Monkey-Ball-arcade** — a "READY?… GO!" countdown, bouncy
squash-and-stretch, **banana** pickups, screen shake, confetti, and a cheerful Web-Audio
soundtrack — all narrated by **the Circuit**, a dry, smug voice that quietly judges every roll.

**Play:** https://phaseball.vercel.app *(updates automatically on every push)*

## Character / feel
- **Sound** — fully synthesized in the browser (no audio files): rolling rumble that tracks
  speed, banana chimes that climb with your combo, a phase whoosh, fail/clear stings, and a
  looping music bed. Toggle with **M** or the 🔊 button.
- **Narrator** — "the Circuit" reacts to deaths, fast clears, wasted phase charges, idling,
  and full-banana runs. Edit the `QUIPS` bank to change its personality.
- **Juice** — countdown, screen shake, particle bursts, confetti at the goal, and a magenta
  vignette flash when you phase.
- **Scoring & medals** — bananas pay out by combo; clears award time, medal (🥇/🥈/🥉),
  full-banana, and no-phase bonuses. A faint **ghost** of your best run replays alongside you.

## Controls
- **W / A / S / D** or **arrow keys** — tilt the world
- **Space** — phase (go intangible to roll through magenta walls)
- **R** — restart stage
- **M** — mute / unmute
- Mobile: on-screen stick + PHASE button (auto-detected)

## Tech
Single file, no build step. Three.js loaded from CDN via importmap. The whole game is in
[`index.html`](index.html).

- **Levels** are pure data in the `LEVELS` array near the top — platforms, walls, bananas,
  goal, start, phase charges, and per-stage medal time targets (`medals:{g,s,b}`). Add a
  stage by adding an object.
- **Feel** is tuned via the `TUNE` object at the very top (gravity, tilt, damping, camera,
  combo window).
- **Personality** lives in the `QUIPS` bank (narrator lines) and the `Audio` module (all
  sound) — both pure data/functions, easy to retune.

## Editing on your phone
1. Open this repo in the GitHub mobile app (or github.com in a browser).
2. Open `index.html`, tap the pencil ✏️ to edit.
3. Change a number in `TUNE` or `LEVELS`, then **Commit changes**.
4. Vercel auto-deploys in ~30s — refresh the play URL to see it live.

> Tip: for bigger edits, press `.` on the GitHub repo page to open github.dev (a full
> web editor) right in the browser.
