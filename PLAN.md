# Plan — the six days

Hexagon-anchored, mostly one toolchain (`ecmwf-opendata` → `earthkit-data` →
matplotlib/cartopy, plus `h3` for the hex days). Day 2 is the reference notebook; the
rest reuse its skeleton.

## Notebook anatomy (every day)
1. **Title + theme**
2. **Method** — the meteorology and the mapping idea, in plain words
3. **Licence & attribution** — data licence block + attribution string
4. **Tools** — with install line
5. **Retrieve → Read/process → Plot** — commented
6. **Output** — map inline + saved PNG for posting

---

## Day 2 · Lines — Jet stream  (built)
`day02_lines_jet.ipynb` → `day02_lines_jet.png`.
250 hPa wind: isotach field (speed by brightness) + streamlines, over Europe and the
eastern Atlantic. Palette is luminance-monotonic, so it stays legible for colourblind
viewers and in greyscale; `cividis` is offered as a by-construction-safe alternative.
`DATE=0` re-runs live on the day.

## Day 20 · Hexagons — the impact of resolution  (built)
`day20_hexagons.ipynb` → `day20_hexagons.png`. **Three grids**, coarse to fine:
- **ECMWF 25 km** (0.25°, H3 res 4) · **ECMWF 9 km** (0.1°, H3 res 5) · **MeteoSwiss 1 km**
  (ICON-CH1, H3 res 8) — 24 h total precipitation, all clipped to Switzerland, shared scale.

Hexagon size mirrors the model grid; the 1 km panel resolves orographic rain the coarse
grids smooth away (max precip 9 → 12 → 20 mm). City call-outs + a one-place bar chart.
`YlGnBu` sequential (colourblind-safe), white background, ECMWF logo + attribution.
ICON-CH1 caps at 33 h, so the window is ≤ 33 h (24 h used); fetched live via `ogd_api`.

## Day 22 · Projections
One field (e.g. Z500) in Plate Carrée, Robinson and polar orthographic — the distortion
made visible. Reuses the Day 2 data pipeline.

## Day 26 · Water
Significant wave height across the North Atlantic from the ECMWF wave stream.

## Day 4 · Clusters
Cluster the ENS members by 500 hPa pattern — forecast spread shown as grouped maps.

## Day 29 · Raster
The same field on its native 0.1° grid — a paired "before" to the Day 20 hexagons.
