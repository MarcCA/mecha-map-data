# Mecha map data

Optional offline light-pollution maps derived from EOG VIIRS annual 2025 data.
This repository contains public data and documentation, not application source.

## Global downloads

The current app uses [catalog-world-v1.json](catalog-world-v1.json). Its seven
regions cover the complete available atlas, including oceans and the date line.
All regions together require 489,033,728 bytes (about 489.0 MB).

- [North America](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/north_america_lightpollution.mbtiles): 99.4 MB.
- [South America](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/south_america_lightpollution.mbtiles): 50.5 MB.
- [Europe](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/europe_lightpollution.mbtiles): 118.2 MB.
- [Africa](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/africa_lightpollution.mbtiles): 55.5 MB.
- [Asia](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/asia_lightpollution.mbtiles): 142.4 MB.
- [Oceania](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/oceania_lightpollution.mbtiles): 21.3 MB.
- [South Pacific](https://github.com/MarcCA/mecha-map-data/releases/download/world-2025-v2-compact-1/south_pacific_lightpollution.mbtiles): 1.8 MB.

The source covers approximately 65°S to 75°N. Requiring the full 300 km source
footprint reduces valid coverage near those polar edges. The exact available
latitude envelope and exhaustive tile-union checks are in [coverage.json](coverage.json).
No missing polar data is filled with an invented dark-sky value. Regional ocean
areas are intentionally included, so downloading all regions leaves no seams or
unassigned ocean areas within the available atlas.

The model is experimental: western-US reference calibration is applied unchanged
worldwide. Complete geographic coverage does not establish worldwide accuracy.
Terrain shielding, spectrum, weather and current Moon conditions are not modeled.
Roads, place labels and terrain use separate basemap downloads.

[ATTRIBUTION.md](ATTRIBUTION.md) credits the source and describes modifications.
[FORMAT.md](FORMAT.md) documents the numerical format. The legacy North America
[catalog.json](catalog.json) remains available for earlier app versions; it is
deliberately not expanded because those versions read only one region.

Release: [world-2025-v2-compact-1](https://github.com/MarcCA/mecha-map-data/releases/tag/world-2025-v2-compact-1).
