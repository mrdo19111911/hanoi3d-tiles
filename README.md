# hanoi3d-tiles

Cell tiles of the 3D street map (hanoi3d `page_local/3d.html`). The page reads them straight from
`raw.githubusercontent.com/mrdo19111911/hanoi3d-tiles/main/<city>/`, one 1.4 km cell at a time (the open cell and its
8 neighbours), so nothing has to be copied to the machine that shows the map.

| folder | area |
|---|---|
| `hn/`  | Nội thành Hà Nội (12 pre-2025 urban districts) |
| `hcm/` | TP Hồ Chí Minh (22 pre-2025 units) |
| `hnf/` | Toàn Hà Nội (30 pre-2025 units) |

Per city: `index.json` (grid and cell list; a cell is usable when `status` is `ok`), and per cell
`<id>.json.gz` (scene data, gzip) and `<id>_cover.png` (land-cover class per 0.5 m cell, value = class × 32).

Written by `scene3d_work/s9/city_build/pack_tiles.py` from the output of `run_grid.py`. Sources: OpenStreetMap
(ODbL), Google/Microsoft Open Buildings, Copernicus DEM, ESA WorldCover. Satellite imagery is used only to derive
classes and colours; no imagery pixels are stored here.
