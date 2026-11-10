# MeteorRX

**Meteor-M LRPT weather-satellite receiver for Windows — version 2.0.0**

MeteorRX does one job well: receive **Meteor-M N2-3 / N2-4 LRPT** weather imagery at 137 MHz,
show you whether the signal is good (eye diagram, S-meter, live picture), and save the pictures —
automatically, pass after pass. It is self-contained: one folder, double-click, no install.

*By Stephan **9H2WB / F5OWB**, Malta Amateur Radio League (MARL).*

![MeteorRX](docs/screenshot.jpg)

---

## Download

Get the latest **`MeteorRX-x.y.z-win64.zip`** from the [**Releases**](../../releases) page, unzip it
anywhere, and run **`MeteorRX.exe`**. Nothing is installed into Windows. See the
[**User Guide**](docs/USER_GUIDE.md) to get going in five minutes.

## What it does

- Receives Meteor-M LRPT with an **RTL-SDR**, **SDRplay RSP** (any model), **HackRF One**,
  **LimeSDR Mini**, **Airspy** (R2 / Mini / HF+ — experimental), or **PlutoSDR**.
- **Automatic**: predicts passes (TLE), pre-corrects Doppler, and starts recording when the signal
  appears — leave it running and collect pictures.
- **Shows you the signal quality** while it decodes: eye diagram, constellation, SNR, Viterbi BER,
  S-meter in dBm / S-units, live image.
- Saves per-channel images and natural-colour / false-colour composites, with optional coastline and
  city-name overlays and earth-curvature correction.
- Interface in **English, French, Italian, Spanish and German**.

## Supported receivers

| Receiver | Notes |
|---|---|
| RTL-SDR (Blog V3/V4, generic R820T) | Driver bundled; Zadig offered if Windows bound the wrong USB driver |
| SDRplay RSP1 / 1A / 1B / 2 / duo / dx / dx-R2 | Install *SDRplay API 3.x* from sdrplay.com |
| HackRF One | Uses `hackrf.dll` from an installed SatDump / SDR++ |
| LimeSDR Mini 1.x / 2.0 | Uses `LimeSuite.dll` from an installed SatDump |
| Airspy R2 / Mini | **Experimental — in test, no warranty.** Uses `airspy.dll` from an installed SatDump / SDR++ |
| Airspy HF+ Discovery / Dual Port | **Experimental — in test, no warranty.** Tunes 137 MHz; uses `airspyhf.dll` from an installed SDR program |
| PlutoSDR (ADALM-Pluto) | Over the network — nothing to install |

A 137 MHz antenna (V-dipole, turnstile or QFH) and, ideally, a low-noise preamplifier with a
band-pass filter are what make the difference between noise and a clean picture. See the User Guide.

## Support

Questions and bug reports: the [**Issues**](../../issues) page. Please attach `data\meteorrx.log` and,
for a reception problem, the output of `MeteorRX-cli --live 30`.

## Licence

MeteorRX is **free-to-use amateur-radio software** under the **MeteorRX License 2.0** (see
[`LICENSE`](LICENSE)). Use it and test it freely, at home or at your club. It is **not** open-source:
please do not redistribute it or re-upload it elsewhere — point fellow operators to this page so they
always get the current, working version. Bundled third-party components keep their own licences
(see [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md)).

## Acknowledgements

Written at the request of **Joe 9H1VW**, with long hours of on-air testing by **Tony IK1HGI** and by
the operators who kept running after each new build — your logs found most of what got fixed.

A nod, too, to the anonymous contributor on the far side of the world who, during the private test
phase, took an early build and re-published it without a word of credit. No hard feelings — but it is
the reason MeteorRX 2.0 ships as a finished program rather than open sources: the code now stays home
until a version is ready, and the licence simply states in writing what good manners used to cover.

Coastlines: Natural Earth (public domain). City names: GeoNames (CC BY 4.0).
