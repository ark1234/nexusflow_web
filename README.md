# NexusFlow — Project Page

Static project page for **NexusFlow: Unifying Disparate Tasks under Partial Supervision via Invertible Flow Networks** (CVPR 2026).

## Local preview

```bash
cd web
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy on GitHub Pages

1. Push this `web/` directory to the `gh-pages` branch (or set Pages to serve from `/web` on `main`).
2. Add an empty `.nojekyll` file so paths with underscores serve correctly.

## Replace placeholders

- `static/pdfs/nexusflow_cvpr2026.pdf` — drop the final paper PDF here and wire up the `#paper-link` and `#arxiv-link` hrefs in `index.html`.
- Videos in `static/videos/` were transcoded from `opensource_code/materials/{Baseline,Ours}_with_map.avi` via:
  ```bash
  ffmpeg -i Baseline_with_map.avi -vf "scale=1832:500" -c:v libx264 -crf 26 -movflags +faststart -an baseline.mp4
  ffmpeg -i Ours_with_map.avi     -vf "scale=1832:500" -c:v libx264 -crf 26 -movflags +faststart -an nexusflow.mp4
  ```
- Figure PNGs were generated from `Figure/*.pdf` via:
  ```bash
  pdftoppm -r 160 -png -singlefile FIG.pdf FIG
  ```
