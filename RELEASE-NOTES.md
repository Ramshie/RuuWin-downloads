# RuuWin 0.1.0-preview.1

First Windows 11 x64 executable prerelease. It shows nearby RAWv2 Ruuvi broadcasts, sensor details and saved sensor names. It runs directly as a self-contained WinUI executable and saves settings under `%LOCALAPPDATA%\RuuWin`. It can import settings from one matching earlier development package when the new destination does not exist.

Download the [EXE](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/RuuWin-0.1.0-preview.1-win-x64.exe), [checksums](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/SHA256SUMS.txt), [license](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/LICENSE.txt) and [dependency notices](https://github.com/Ramshie/RuuWin-downloads/releases/download/v0.1.0-preview.1/THIRD-PARTY-NOTICES.txt). See the [public README](https://github.com/Ramshie/RuuWin-downloads/blob/main/README.md) for requirements, checksum verification, usage and updates.

**Unsigned experimental preview:** verify the EXE against `SHA256SUMS.txt`. Windows may show publisher or reputation warnings; do not disable security features. The EXE extracts bundled runtime files at launch. Browser download, Mark-of-the-Web and Windows trust/SmartScreen checks were explicitly deferred by the owner. Authenticated API download and checksum checks do not establish browser or SmartScreen behavior.

## Passed validation

The exact release EXE passed three cold launches across two fresh offline Windows 11 Enterprise 24H2 x64 Sandbox sessions (build 26100.9457). Checks included thirty original accessibility query completions, standard-user launch without manually installed prerequisites, discovery without an adapter, second-instance activation, normal shutdown, saved-fixture rename/persistence and malformed-settings recovery. Launch paths contained spaces and non-ASCII text, with a different working directory. These results cover the tested OS build.

File replacement and settings retention passed in a third fresh Sandbox session using a synthetic `0.0.0-baseline` built from the same source, followed by this exact preview EXE. This does not establish migration from a historical release or schema. These are existing private validation results; copying the same bytes to this downloads repository does not add a new hardware or Windows trust test.

## Accepted deferrals and limits

Final-executable physical Bluetooth checks were explicitly deferred by the owner: discovery and sensor operations, live readings/details, Bluetooth off/on, range recovery, sleep/resume and minimized reception remain unverified with physical hardware. RuuviTag Pro discovery and live readings were observed only in earlier local builds. RAWv2 decoding is supported; standard RuuviTag hardware has not been validated.

Manual keyboard navigation, display scaling and light/dark appearance checks were intentionally omitted and accepted by the owner for this preview. They are unverified, not passes. Browser download, Mark-of-the-Web and Windows publisher/reputation checks are also deferred. Anonymous asset-download verification is a separate distribution check and does not resolve these deferrals.

## Exact executable

- Filename: `RuuWin-0.1.0-preview.1-win-x64.exe`
- Size: 94,817,875 bytes (94.8 MB)
- SHA-256: `2F38F9B6BAECCA30782547367DD9D286C92ECC4E2E2C4EBC31FCCD3927AC3813`

The EXE and companion release assets are copied without rebuilding. This repository's `v0.1.0-preview.1` tag identifies its public documentation commit; executable source provenance is retained separately in private maintainer records.
