# Changelog

## [2.0.0] — 2026-11-09

### Added
- **Experimental Airspy support (in test, no warranty):** Airspy R2 / Mini and Airspy HF+
  (`device = airspy` / `device = airspyhf` in `meteorrx.ini`). Please report how they work for you.
- **Brighton and Liverpool** are now always labelled on the map when a pass covers them.

### Changed
- **Faster, lighter, and distributed as a finished program.** MeteorRX 2.0 starts immediately (no
  first-run preparation wait) and runs a little faster on every pass.
- **Licensing.** MeteorRX is now **free-to-use amateur-radio software** under the **MeteorRX License
  2.0** (see `LICENSE`): use and test it freely; please do not redistribute it — direct fellow
  operators to the official download page so they always get the current, working version.

### Notes
- Your settings (`meteorrx.ini`), receiver profiles and saved pictures from earlier versions are kept.
- Supported receivers (RTL-SDR, SDRplay RSP, HackRF One, LimeSDR Mini, PlutoSDR) are unchanged.

_Earlier version history is kept in the private development repository._
