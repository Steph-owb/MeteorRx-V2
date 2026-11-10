# Third-party notices

MeteorRX is licensed under the **MeteorRX License 2.0** (see `LICENSE`) — free-to-use
amateur-radio software, not open-source.

Copyright (C) 2026 Stephan, 9H2WB / F5OWB.

MeteorRX bundles the third-party components listed below. Each remains under its own licence; the
MeteorRX License applies only to the Author's own work, not to these components.

## Algorithms

The **demodulation and timing-recovery chain** — polyphase channelizer, OQPSK demodulator (Farrow
interpolator, AGC, FLL, RRC, Costas loop, Mueller & Müller timing recovery) — is an independent
implementation by the Author, in C (`meteorrx/_dspnative`) and Python, written from public
specifications: the CCSDS recommendations for TM synchronization and channel coding (CCSDS 131.0-B),
the published Meteor-M LRPT signal description, and standard DSP textbook algorithms. The open-source
decoders **SatDump** and **meteor_demod / meteor_decode** (dbdexter-dev) were consulted for signal
parameters and for cross-checking decoded output.

The **forward-error-correction codecs** — convolutional encoder and Viterbi decoder (K=7, rate 1/2),
and the Reed-Solomon (255,223) codec — are an independent implementation of the published **CCSDS
channel-coding standard** (CCSDS 131.0-B), whose field polynomial, dual basis, first consecutive root
and primitive element fully determine the codec.

## Development and test only (NOT part of a release build)

| Component | Licence | Use |
|---|---|---|
| Numba, llvmlite | BSD-2-Clause | Reference DSP backend used only in an uncompiled source checkout (`meteorrx/_dsp_ref.py`) to validate the native kernels. Not shipped. |
| `tests/data/meteor_m2_real_soft.npz` | derived from a recording under the MIT licence (github.com/lar-tech/satellite-decoder) | Test vector. Not shipped. |

## Map overlay data (bundled in `meteorrx/data/`)

| File | Content | Licence | Source |
|---|---|---|---|
| `coastline.bin.gz` | Natural Earth 1:10m coastline, packed to float32 polylines | Public domain | https://www.naturalearthdata.com |
| `cities.tsv.gz` | GeoNames populated places ≥ 50 000 inhabitants | CC BY 4.0 | https://www.geonames.org |
| `font.bin.gz` | DejaVu Sans Bold 15 px, baked to 1-bit glyphs | DejaVu Fonts License (permissive) | https://dejavu-fonts.github.io |

The GeoNames attribution required by CC BY 4.0 is shown in the application whenever the overlays are
used (`meteorrx.overlay.ATTRIBUTION`).

## Bundled in the Windows package

| Component | Licence | Source |
|---|---|---|
| `rtlsdr.dll` — RTL-SDR Blog driver library v1.3.6 (x64) | GPL-2.0-or-later | https://github.com/rtlsdrblog/rtl-sdr-blog (tag v1.3.6) |
| `zadig.exe` — Zadig 2.9 (libwdi v1.5.1), signed by Akeo Consulting | GPL-3.0 | https://github.com/pbatard/libwdi (tag v1.5.1) |
| Python 3.12 runtime | PSF License | https://www.python.org |
| NumPy | BSD-3-Clause | https://numpy.org |
| PySide6 / Qt 6 | LGPL-3.0 | https://www.qt.io/qt-for-python |
| sgp4 | MIT | https://pypi.org/project/sgp4/ |
| certifi | MPL-2.0 | https://pypi.org/project/certifi/ |

**GPL components.** `rtlsdr.dll` (GPL-2.0-or-later) and `zadig.exe` (GPL-3.0) are redistributed
unmodified under their own terms. Their complete corresponding source is available at the URLs above
and is identified, with SHA-256 checksums, in the `SOURCE.txt` file shipped beside each binary in the
package. `zadig.exe` runs as a separate program; `rtlsdr.dll` is loaded dynamically at runtime. These
components are not part of the Author's work and remain under their own licences.

**LGPL component.** Qt / PySide6 is used as a dynamically-linked library under the LGPL-3.0; a user
may replace it with a compatible version. Its source is available at the URL above.

## Used from other installed programs (not distributed)

- SDRplay API 3.x (`sdrplay_api.dll`, proprietary, installed separately from sdrplay.com)
- `hackrf.dll` (GPL-2.0) and `LimeSuite.dll` (Apache-2.0) of an SDR program the user has installed
  (SatDump, SDR++, PothosSDR). MeteorRX loads them if present but does not distribute them.
- `airspy.dll` (libairspy) and `airspyhf.dll` (libairspyhf), from the Airspy project, of an installed
  SDR program (SatDump, SDR++, PothosSDR). Used by the **experimental** Airspy backends; MeteorRX loads
  them if present but does not distribute them. See github.com/airspy/airspyone_host and
  github.com/airspy/airspyhf for their sources and licences.
