# Compact numerical map format

The file is a custom SQLite container with an .mbtiles extension. General
MBTiles viewers cannot display it directly. It contains a `metadata` table
and a `numeric_tiles` table, with columns `zoom_level`, `tile_column`,
`tile_row`, `tile_data`. Tile rows use TMS ordering; pixels are top-to-bottom.
There is no PNG `tiles` table.

Numerical tiles are 256 x 256 pixels at zooms 3-8. Point readings use zoom 8.
Lower zooms are display overviews averaged in linear artificial/natural
brightness ratio. Missing values are not interpreted as natural darkness.

Encoding: `log1p_ratio_u16_delta_shuffle_zlib_v2`.
1. Decompress with zlib, requiring exactly 131072 output bytes.
2. The first 65536 bytes are low bytes; the next 65536 are high bytes.
3. Reconstruct unsigned 16-bit differences.
4. Within each row, cumulatively add differences modulo 65536. Restart at
   zero for each row; its first difference is the first absolute code.
5. Code 65535 means no data. All other codes decode to
   `ratio = expm1(code / 4096)`.

The ratio is artificial / assumed natural zenith brightness. Interpolate
neighboring valid ratios in linear brightness before converting to SQM:
`SQM = 22 - 2.5 * log10(1 + ratio)`.
Natural brightness is fixed at 171.16846478579998 microcd/m2.
Artificial brightness is natural brightness times ratio; total brightness is
natural brightness times (1 + ratio). Divide microcd/m2 by 1000 for mcd/m2.
Bortle classes are approximate interpretations of SQM, not direct measurements.

Use `lightpollution_dataset.json` to verify length, SHA-256 and compatible
schema/encoding before installing. Download to a temporary file, validate,
then atomically replace the installed package. The catalog's package URLs are
versioned; released files should not be changed in place.
