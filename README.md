# Rule 30 Explorer

An interactive, single-file explorer for [Wolfram's Rule 30](https://en.wikipedia.org/wiki/Rule_30) — one of the elementary cellular automata, and the one Stephen Wolfram is most famous for. Starting from a single live cell, it grows into a triangle with an ordered, repeating stripe pattern on the left and irreducibly chaotic noise on the right. It's random enough that Wolfram Research has used it as an actual random number generator.

**[Live demo →](https://tkluysk.github.io/rule-30-explorer/)**

## Features

- **Rule table diagram** — all 8 neighborhood patterns and which ones fire, with Rule 30's binary (`00011110`) laid out visually.
- **Editable seed row** — tap/click a cell to toggle it before pressing play (a few presets are included: single cell, random noise, spaced pairs, dense noise).
- **Pan & pinch-zoom** — drag to pan, pinch or scroll to zoom, live while the simulation runs or while paused.
- **Fixed 2:1 canvas** — the simulation frame is always exactly twice as wide as it is tall (the natural proportion for a single-seed light cone), with an adjustable height (default 2000px, width auto-follows at 4x).
- **Down to 1 physical pixel per cell** — retina-accurate rendering.
- **PNG export** — download the full-resolution rendered pattern at any point.

## Usage

It's a single self-contained HTML file — no build step, no dependencies.

```bash
# just open it
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Hosting on GitHub Pages

1. Push this repo to GitHub (see below).
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save — your site will be live at `https://<username>.github.io/<repo-name>/` within a minute or two.

## How Rule 30 works

Each cell's next state depends only on itself and its two immediate neighbors — 8 possible 3-cell patterns in total. Rule 30 is named for its rule number: `30` in binary is `00011110`, meaning 4 of those 8 patterns produce a live cell next generation and 4 produce a dead one. That's it — the entire rule. Iterating it from one live cell produces the well-known asymmetric triangle.

## License

MIT — see [LICENSE](LICENSE).
