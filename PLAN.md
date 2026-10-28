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

## Day 20 · Hexagons — the impact of resolution  (data proven)
Two panels of the same area, side by side, sharing one colour scale:
- **Left:** ECMWF IFS 0.1° (~9 km) 2 m temperature, binned to H3 hexagons (res 5).
- **Right:** MeteoSwiss ICON-CH1 1 km, same parameter, binned to finer H3 hexagons (res 8).

The hexagon size encodes the model resolution; the 1 km panel resolves individual Alpine
valleys the 0.1 ° panel cannot. Both must use the **same run and valid time**. Render the
fine panel with a `PolyCollection` (~100 k hexagons).

Open question: shared vs per-panel colour scale — leaning **shared**, for a fair comparison.
MeteoSwiss ICON-CH1 is only published for the last ~24 h, so fetch it live on the day.

## Day 22 · Projections
One field (e.g. Z500) in Plate Carrée, Robinson and polar orthographic — the distortion
made visible. Reuses the Day 2 data pipeline.

## Day 26 · Water
Significant wave height across the North Atlantic from the ECMWF wave stream.

## Day 4 · Clusters
Cluster the ENS members by 500 hPa pattern — forecast spread shown as grouped maps.

## Day 29 · Raster
The same field on its native 0.1° grid — a paired "before" to the Day 20 hexagons.
