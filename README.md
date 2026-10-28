# 30dmc2026

Maps for the 2026 [#30DayMapChallenge](https://30daymapchallenge.com/), built on open
weather and climate data — primarily **ECMWF IFS open data** (0.1°, the ~9 km IFS
regridded) and **MeteoSwiss ICON-CH1** (1 km) — using ECMWF's open-source Python stack.

Each day is a **self-contained Jupyter notebook**: method, code, output, data licence and
tools in one place, reproducible on any laptop with `pip`.

## Setup

```bash
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

## Data & licences

- **ECMWF Open Data** — retrieved with [`ecmwf-opendata`](https://github.com/ecmwf/ecmwf-opendata),
  read with [`earthkit-data`](https://earthkit-data.readthedocs.io). Licensed
  **CC-BY-4.0** ([Terms of Use](https://apps.ecmwf.int/datasets/licences/general/)).
  Attribution: `© ECMWF · Source: www.ecmwf.int · CC-BY-4.0 and ECMWF Terms of Use`.
  Note: the client defaults to 0.25°; pass `resol="0p1"` for the 0.1° grid.
- **MeteoSwiss Open Data** — ICON-CH1-EPS via [`meteodata-lab`](https://github.com/MeteoSwiss/meteodata-lab)
  (STAC API, `data.geo.admin.ch`). Open Government Data; attribute **MeteoSwiss** as source.

Code licence: see [`LICENSE`](LICENSE).

## Days

| Day | Theme | Map | Status |
|----:|-------|-----|--------|
| 2 | Lines | Jet stream — 250 hPa isotach field + streamlines | built |
| 20 | Hexagons | 25 / 9 / 1 km precipitation over Switzerland, H3 hexbins (ECMWF + MeteoSwiss) | built |
| 22 | Projections | One field, three projections | planned |
| 26 | Water | Significant wave height, N. Atlantic | planned |
| 4 | Clusters | ENS members clustered by 500 hPa pattern | planned |
| 29 | Raster | The native grid behind the hexagons | planned |

See [`PLAN.md`](PLAN.md) for the brief on each day.
