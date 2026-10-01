# RuuWin downloads

RuuWin is a local Windows 11 app for viewing nearby Ruuvi sensors. It listens to Bluetooth Low Energy advertisements while its window is open, including when minimized. Pairing and internet access are not needed. You can add, name, rename and remove sensors, view their latest readings and open sensor details. Only sensor names, identities and order are saved; readings are not logged.

## Download 0.1.0-preview.1

- [Release and validation limits](https://github.com/Ramshie/RuuWin-downloads/releases/tag/v0.1.0-preview.1)
- [Windows x64 EXE](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/RuuWin-0.1.0-preview.1-win-x64.exe)
- [SHA256SUMS.txt](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/SHA256SUMS.txt)
- [MIT license](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/LICENSE.txt) and [dependency notices](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/THIRD-PARTY-NOTICES.txt)

Requirements: Windows 11 x64 (build 22000 or later) and a Bluetooth LE adapter for sensor reception. The self-contained EXE needs no Visual Studio, .NET SDK, Developer Mode or manual package registration. Direct launch was tested on Windows 11 Enterprise 24H2 x64 build 26100.9457; other Windows builds remain unverified. Sensor compatibility is limited to Ruuvi data format 5 / RAWv2. Final-EXE physical Bluetooth behavior has not been validated.

Download the EXE and checksum file to the same folder. In PowerShell, run:

```powershell
Get-FileHash .\RuuWin-0.1.0-preview.1-win-x64.exe -Algorithm SHA256
```

Compare the result with the matching entry in `SHA256SUMS.txt` and this pinned SHA-256:

```text
2F38F9B6BAECCA30782547367DD9D286C92ECC4E2E2C4EBC31FCCD3927AC3813
```

EXE size: 94,817,875 bytes. If the hash differs, do not run the file. Keep the published filename and double-click it after verification. The EXE extracts its bundled runtime files to the current user's temporary directory at launch; first launch can take time.

**This experimental preview is unsigned.** Windows may show a publisher or reputation warning. Do not disable Windows security features to run it. Browser download, Mark-of-the-Web and SmartScreen behavior remain unverified; checksum verification does not establish Windows trust. See [release notes](RELEASE-NOTES.md) for passed checks and accepted deferrals.

## Use, update and remove

Use **Add sensor** to find nearby RAWv2 broadcasts. Saved sensors initially show **Waiting for reading**; after 60 seconds without a valid packet they show **No recent signal**. Missing measurements show `—`; battery percentage is not estimated. If scanning does not start, check Windows Bluetooth, LE adapter support and the sensor's broadcast format, then use **Retry scan**. Closing the app stops scanning.

There is no installer or auto-update. To update, close RuuWin, download the newer version, verify its checksum and launch it. Settings remain under `%LOCALAPPDATA%\RuuWin` when the EXE is replaced. To remove RuuWin, close it and delete the downloaded EXE. Delete that settings folder only if you also want to remove saved sensors and diagnostics. Windows may retain extracted runtime files under `%TEMP%\.net` until temporary files are cleaned.

`%LOCALAPPDATA%\RuuWin\sensors.json` stores sensor names, identities and order. A damaged settings file is preserved before the next successful save. An unhandled WinUI exception may create `last-error.txt` in the same folder. Review these files before sharing because they can contain sensor identities and diagnostics.

## Repository and license

This repository contains downloads and public documentation. Its independent Git history and version tag identify documentation, not the executable's source commit. Application source, source history and private development evidence are maintained separately. GitHub's automatic source archives contain only this repository's documentation and license material; download the EXE from the release assets to run RuuWin.

RuuWin is licensed under [MIT](LICENSE.txt). [Third-party notices](THIRD-PARTY-NOTICES.txt) cover bundled dependencies. The release's checksum file covers the EXE, license and notices.
