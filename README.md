# #30DayMapChallenge 2026 — ECMWF open data

Beautiful, reproducible weather maps for the
[#30DayMapChallenge](https://30daymapchallenge.com/), built on **ECMWF 9 km (0.1°)
open data** (and MeteoSwiss 1 km where it earns its place), using ECMWF's own
open-source tooling.

Each day is a **self-contained Jupyter notebook**: method, code, output, tools and
licence in one place, runnable on any laptop with `pip`.

## Setup

```bash
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

## Data & licence

All ECMWF fields come from the [Open Data](https://www.ecmwf.int/en/forecasts/datasets/open-data)
service via the [`ecmwf-opendata`](https://github.com/ecmwf/ecmwf-opendata) client,
read with [`earthkit-data`](https://earthkit-data.readthedocs.io).

> Access to ECMWF Open Data is governed by the **Creative Commons CC-BY-4.0** licence
> and the associated [Terms of Use](https://apps.ecmwf.int/datasets/licences/general/).
> Attribution: `© ECMWF · Source: www.ecmwf.int · CC-BY-4.0 and ECMWF Terms of Use`.

**Gotcha:** the Client defaults to 0.25°. Pass `resol="0p1"` for the real 9 km grid.

## Days

| Day | Theme | Map | Data |
|----:|-------|-----|------|
| 2 | Lines | Jet stream — 250 hPa isotach glow + streamlines | IFS oper |
| 20 | **Hexagons** | 9 km vs 1 km over Switzerland, side by side — "the impact of resolution" | IFS + MeteoSwiss ICON-CH1 |
| 22 | Projections | One field, three projections | IFS oper |
| 26 | Water | Significant wave height, N. Atlantic | IFS wave |
| 4 | Clusters | ENS members clustered by Z500 pattern | IFS enfo |
| 29 | Raster | The honest native grid behind the art | IFS oper |

See [`PLAN.md`](PLAN.md) for the full brief on each day.
