# PHASEBALL

A tilt-the-world marble game (Super Monkey Ball-style) with a **phase-through-walls** twist.
You don't steer the marble — you tilt the world and let gravity roll it home. Cyan walls
block you; **magenta phase-walls** can be passed through by going intangible for a moment,
but charges are limited per stage.

**Play:** https://phaseball.vercel.app *(updates automatically on every push)*

## Controls
- **W / A / S / D** or **arrow keys** — tilt the world
- **Space** — phase (go intangible to roll through magenta walls)
- **R** — restart stage
- Mobile: on-screen stick + PHASE button (auto-detected)

## Tech
Single file, no build step. Three.js loaded from CDN via importmap. The whole game is in
[`index.html`](index.html).

- **Levels** are pure data in the `LEVELS` array near the top — platforms, walls, gems,
  goal, start, phase charges. Add a stage by adding an object.
- **Feel** is tuned via the `TUNE` object at the very top (gravity, tilt, damping, camera).

## Editing on your phone
1. Open this repo in the GitHub mobile app (or github.com in a browser).
2. Open `index.html`, tap the pencil ✏️ to edit.
3. Change a number in `TUNE` or `LEVELS`, then **Commit changes**.
4. Vercel auto-deploys in ~30s — refresh the play URL to see it live.

> Tip: for bigger edits, press `.` on the GitHub repo page to open github.dev (a full
> web editor) right in the browser.
