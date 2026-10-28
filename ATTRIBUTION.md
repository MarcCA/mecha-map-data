# Data sources and attribution

This product was made utilizing VIIRS Nighttime Lights (VNL) data produced by the
Earth Observation Group, Payne Institute for Public Policy, Colorado School of Mines.

- Source product: EOG annual VIIRS Nighttime Lights, 2025, version 2,
  Suomi NPP masked median radiance.
- Product information: https://eogdata.mines.edu/products/vnl/
- Upstream license: Creative Commons Attribution 4.0 International (CC BY 4.0).
- License: https://creativecommons.org/licenses/by/4.0/
- EOG data-access and licensing notice:
  https://eogdata.mines.edu/files/EOG_products_CC_License.pdf

Changes: Mecha converts upward satellite radiance into an experimental modeled
zenith sky-brightness estimate, using area-weighted distance propagation and an
empirical calibration. It resamples the result into numerical tiles with a
fixed natural-sky baseline of 22 SQM and lossless predictive compression of
the quantized values. This is a modified derivative, not an official EOG
zenith-brightness product. No endorsement by EOG is implied.

Calibration used manually transcribed modeled reference readings from
https://lightpollutionmap.app/ (layer/year not recorded). These are model
comparison values, not ground measurements. Individual calibration locations
and the source website's maps or imagery are not distributed here.

This repository contains downloadable data and documentation, not the Mecha
application source code. The upstream license and attribution remain applicable
to the EOG source material; publishing these data does not license app code.
