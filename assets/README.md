# Music (optional, CC0)

Drop a looping synthwave track here and the game plays it automatically as the
soundtrack. If no file is present, PHASEBALL falls back to its built-in
Web-Audio synth bed — so the game always works.

## How to add a track
1. Download a **CC0** (public-domain, no-attribution) synthwave/Outrun loop.
2. Save it in this folder as **`music.ogg`** (preferred) and/or **`music.mp3`**
   (Safari fallback). The game tries `music.ogg` first, then `music.mp3`.
3. Commit + push — Vercel redeploys and the track loops in-game.

Keep it small and seamless: aim for **~2–4 MB**, a clean loop point, and a
moderate tempo (~110–120 BPM fits the dash rhythm).

The track is routed through the master gain, so the in-game **mute (M / 🔊)**
and volume already apply to it.

## CC0 sources (no attribution required)
- **Pixabay – Synthwave / Outrun** — https://pixabay.com/music/search/outrun/
  and https://pixabay.com/music/search/synthwave%20loop/ (mark: "no copyright",
  no attribution). Good fits: *Asphalt Superstar*, *Synthwave Outrun*,
  *Under the Streetlights*.
- **OpenGameArt – CC0 synthwave**:
  - Retro Synthwave Loops — https://opengameart.org/content/retro-synthwave-loops
  - Eyeless (Retrowave) — https://opengameart.org/content/eyeless-retrowave
  - Retro Wave (Collection) — https://opengameart.org/content/retro-wave-collection

> Double-check each track's license on its page before shipping. CC0 needs no
> credit; if you ever use a CC-BY track instead, add a credit line to the
> top-level README.
