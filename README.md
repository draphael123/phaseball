# PHASEBALL

A **Super Monkey Ball-style** tilt-the-world marble game, dressed in a full **Outrun synthwave**
look — banded sun on the horizon, chrome marble, neon grid, VHS scanlines — across **5 rolling
courses**, with a live attract-mode title and a results board. You don't steer the marble — you
tilt the world and let gravity roll it home: stay on the course through turns and narrow bridges,
grab bananas, and reach the goal before the clock. Tap **Space** for an optional **turbo boost**
(a recharging meter) to carry speed — a clean no-boost run scores higher.

The presentation leans **Monkey-Ball-arcade** — a "READY?… GO!" countdown, bouncy
squash-and-stretch, **banana** pickups, screen shake, confetti, and a cheerful Web-Audio
soundtrack — all narrated by **the Circuit**, a dry, smug voice that quietly judges every roll.

**Play:** https://phaseball.vercel.app *(updates automatically on every push)*

## Character / feel
- **Turbo boost (optional)** — tap Space (or the on-screen TURBO) for a burst of speed along
  your heading, from a meter that refills over time. No course requires it; a no-boost clear
  scores higher. Tuned in `TUNE` (`dashBoost`, `dashCost`, `energyRegen`).
- **Sound** — fully synthesized in the browser (no audio files): rolling rumble that tracks
  speed, banana chimes that climb with your combo, a turbo whoosh, barrier smash, fail/clear
  stings, and a looping music bed. Toggle with **M** or the 🔊 button.
- **Narrator** — "the Circuit" reacts to deaths, fast clears, empty turbo, idling, and
  full-banana runs. Edit the `QUIPS` bank to change its personality.
- **Juice** — countdown, screen shake, particle bursts, confetti at the goal, barrier debris,
  and a vignette flash when you dash. Dashing also punches the FOV out, fires a shockwave ring,
  pulses the chromatic aberration, and a barrier smash adds a crunchy freeze-frame (hitstop).
- **Level select** — pick any of the 5 stages from the title/results screen (with each stage's
  best time + medal); **Press Start** runs the full circuit from stage 1.
- **Settings** — a ⚙ menu (or **Esc**) pauses the game and exposes music/SFX volume, screen-shake,
  chase-camera, and retro-filter (scanlines) toggles, plus a reset for best times — all saved
  to localStorage.
- **Unlockables (🎨 Garage)** — earn **stars** from your best runs (per stage: +1 cleared,
  +2 gold / +1 silver, +1 all-bananas) and spend them to unlock **marble colors** (incl. an
  animated Rainbow) and **3D hats** (halo, cap, top hat, crown, party, antenna, star). Equip
  your look; it's saved and previewed live on the attract-screen marble.
- **A face in the ball** — eyes that blink and glance where you're rolling, a grin when you
  grab a banana, a shocked "O" on a fall, and a dizzy spin after a hard landing.
- **Chase camera** — the camera swings behind your direction of travel, with camera-relative
  controls so "forward" always means away from the camera. Toggle via `TUNE.camFollow`.
- **Par timer** — each stage has a `par`; the clock turns red and ticks in the final seconds,
  and running out is a **TIME OVER** fail.
- **Outrun synthwave look** — a painted poster sky (gradient + banded sun + mountains + stars),
  a chrome marble with a glowing face, a neon grid floor, magenta/cyan palettes, and hammy
  arcade callouts ("PERFECT!" / "GREAT!") played against the Circuit's deadpan.
- **Visuals** — bloom + ACES tone mapping make the neon glow, a core synthwave environment map
  gives the chrome real reflections, plus VHS scanlines and subtle chromatic aberration.
  Post-processing loads from the CDN and gracefully falls back to a plain render if unavailable;
  the chrome reflections work either way.
- **Attract mode** — the title screen and results board orbit a live stage in the background.
- **Results board** — finishing shows a per-stage breakdown of best times and medals, plus
  total time and score.
- **Scoring & medals** — bananas pay out by combo; clears award time, medal (🥇/🥈/🥉),
  full-banana, and efficiency (no wasted boosts) bonuses. A faint **ghost** of your best run
  replays alongside you.

## Controls
- **W / A / S / D** or **arrow keys** — tilt the world
- **Space** — turbo boost (optional speed burst along your heading)
- **R** — restart stage
- **M** — mute / unmute
- Mobile: on-screen stick + TURBO + restart buttons (auto-detected); **Performance mode**
  (lighter shadows/bloom/pixel-ratio) defaults on for touch and is toggleable in Settings

## Tech
Single file, no build step. Three.js loaded from CDN via importmap. The whole game is in
[`index.html`](index.html).

- **Levels** are pure data in the `LEVELS` array near the top — connected platforms, bananas,
  goal, start, per-stage medal time targets (`medals:{g,s,b}`), and a `par`. Keep platforms
  overlapping so the course has no gaps. (Walls still support `breakable:true` dash barriers if
  you want to add one.) Add a stage by adding an object.
- **Feel** is tuned via the `TUNE` object at the very top (gravity, tilt, damping, camera,
  combo window).
- **Personality** lives in the `QUIPS` bank (narrator lines) and the `Audio` module (all
  sound) — both pure data/functions, easy to retune.
- **Music** — drop a **CC0** loop at [`assets/music.ogg`](assets/) (and/or `.mp3`) and it
  plays as the soundtrack through the mute/volume controls; with no file, the built-in synth
  bed plays instead. See [`assets/README.md`](assets/README.md) for sources and tips.

## Editing on your phone
1. Open this repo in the GitHub mobile app (or github.com in a browser).
2. Open `index.html`, tap the pencil ✏️ to edit.
3. Change a number in `TUNE` or `LEVELS`, then **Commit changes**.
4. Vercel auto-deploys in ~30s — refresh the play URL to see it live.

> Tip: for bigger edits, press `.` on the GitHub repo page to open github.dev (a full
> web editor) right in the browser.
