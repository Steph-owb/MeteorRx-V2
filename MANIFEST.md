# Third-party licence texts

GPL, LGPL, PSF, BSD, MIT and MPL all require the **full licence text** to be distributed with the
program (a link is not enough). `tools/make_deploy.py` copies this whole folder into the release and
warns if any required file is missing. Drop the official, verbatim texts here before a public release:

| File | Covers | Canonical source |
|---|---|---|
| `GPL-2.0.txt` | `rtlsdr.dll` (RTL-SDR Blog driver) | https://www.gnu.org/licenses/old-licenses/gpl-2.0.txt |
| `GPL-3.0.txt` | `zadig.exe` (Zadig / libwdi) | https://www.gnu.org/licenses/gpl-3.0.txt |
| `LGPL-3.0.txt` | PySide6 / Qt 6 | https://www.gnu.org/licenses/lgpl-3.0.txt |
| `LGPL-2.1.txt` | libusb (static inside `rtlsdr.dll`) | https://www.gnu.org/licenses/old-licenses/lgpl-2.1.txt |
| `PSF.txt` | CPython 3.12 runtime | https://docs.python.org/3/license.html |
| `BSD-3-Clause.txt` | NumPy | https://numpy.org/doc/stable/license.html |
| `MIT.txt` | sgp4 | https://pypi.org/project/sgp4/ |
| `MPL-2.0.txt` | certifi | https://www.mozilla.org/MPL/2.0/ |

Keep each file's name exactly as above. See `../THIRD_PARTY_NOTICES.md` for what each component is and
`../SECURITY-MODEL.md` for the open licensing questions (Reed-Solomon / libfec, `rtlsdr.dll` linking).
