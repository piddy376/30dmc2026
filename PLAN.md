# Plan — the six days

Hexagon-anchored, mostly one toolchain (`ecmwf-opendata` → `earthkit-data` →
matplotlib/cartopy, plus `h3` for the hex days). Day 2 is the reference notebook;
the rest reuse its skeleton.

## Notebook anatomy (every day)
1. **Title + theme**
2. **Method** — the meteorology and the mapping idea, in plain words
3. **Licence & attribution** — CC-BY-4.0 block + attribution string
4. **Tools** — with install line
5. **Retrieve → Read/process → Plot** — commented
6. **Output** — map inline + saved PNG for posting

---

## Day 2 · Lines — Jet stream  ✅ built
`day02_lines_jet.ipynb` → `day02_lines_jet.png`.
250 hPa wind: isotach glow (speed by brightness) + fine streamlines, dark, Europe +
E Atlantic. Palette tuned to be **luminance-monotonic → colourblind-safe** (verified by
CVD simulation + greyscale); `cividis` offered as the by-construction-safe swap.
`DATE=0` → re-run on **2 Nov 2026** for that day's jet, then post to LinkedIn.

## Day 20 · Hexagons — "the impact of resolution"  ⭐ the hero
Emma's spec (2026-10-28):
- **Two plots side by side, same area**, touching, with a **thick divider** down the middle.
- **Left:** ECMWF **9 km** (0.1°) grid over Switzerland — **2T** (2 m temperature),
  binned into H3 hexagons.
- **Right:** **MeteoSwiss 1 km** (ICON-CH1) over the *same* area, same parameter
  (2T — or precipitation), binned into finer H3 hexagons.
- The point: **see the resolution jump** 9 km → 1 km made visceral through hex size/detail.
- "It might look shite but I love it." → keep it bold; don't over-polish away the contrast.
- Open Q: fixed shared colour scale across both panels (fair comparison) vs per-panel
  (max detail). Lean: **shared scale**, so the eye compares like with like.
- Data: MeteoSwiss ICON-CH1-EPS open data (STAC, AWS) — its own licence; confirm & attribute.

## Day 22 · Projections
One field (e.g. Z500 or the jet) in Plate Carrée vs Robinson vs polar orthographic —
weather makes the distortion vivid. Reuses Day 2 data pipeline.

## Day 26 · Water
Significant wave height across the N. Atlantic from the **wave** stream — a dataset few
challenge entries will have.

## Day 4 · Clusters
Cluster the **ENS** members (`enfo`) by 500 hPa pattern — deeply NWP; shows forecast
spread as grouped maps.

## Day 29 · Raster
The same field as its honest native 0.1° grid — a deliberate "before" to the hexagon
"after". Low effort, high payoff as a pair with Day 20.
