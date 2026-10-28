# Mecha map data

Versioned offline light-pollution datasets for Mecha. This public repository
contains data, a download catalog and documentation. App source code, keys,
APKs and individual calibration locations are not included.

## Downloads

- [North America, 2025 model, compact v2](https://github.com/MarcCA/mecha-map-data/releases/download/north-america-2025-v2-compact-1/north_america_lightpollution.mbtiles)
  (88,100,864 bytes; approximately 88.1 MB).
- [Checksum descriptor](https://github.com/MarcCA/mecha-map-data/releases/download/north-america-2025-v2-compact-1/lightpollution_dataset.json)
- [SHA-256 checksums](https://github.com/MarcCA/mecha-map-data/releases/download/north-america-2025-v2-compact-1/SHA256SUMS)
- [Download catalog](catalog.json)
- [Data attribution](ATTRIBUTION.md)
- [Numerical format](FORMAT.md)

Catalog URL for the app:
`https://raw.githubusercontent.com/MarcCA/mecha-map-data/main/catalog.json`

The catalog contains immutable versioned package URLs, exact sizes and SHA-256
hashes. Downloading a region once permits offline numerical readings and map
color rendering. Background roads, labels and terrain need separate downloads.

## Interpretation and limitations

This is an experimental annual zenith sky-brightness model derived from EOG
VIIRS data. It is not a direct SQM observation or an official EOG skyglow atlas.
The original calibration is based on western-US reference values from another
model; continental coverage does not establish continental accuracy. Terrain
shielding, spectra and weather are not modeled. Missing data remains missing,
including parts of the nominal northern bounds. SQM and estimated Bortle are
planning aids rather than guaranteed conditions on a particular night.

Source year: 2025. Nominal bounds (west, south, east,
north): -170.0, 15.0, -50.0, 75.0.
The package retains the existing detailed resolution and numerical values.
It uses lossless compression of the quantized data and renders colors on-device.

See [ATTRIBUTION.md](ATTRIBUTION.md) for source credits, upstream licensing and
the changes made to the source data.
