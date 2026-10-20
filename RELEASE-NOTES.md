# WAN Manager 0.1.0-preview.2

Application and engine **2026.10.18.8**. Public documentation refreshed 20 October 2026. An evaluation prerelease, not a stable release.

## Changes since preview.1

- One modern Avalonia workspace for guided setup, IP Sessions, active/saved routes, TAP settings and adapter properties.
- Automatic wizard discovery/readiness progression, clear two-WAN selection, disclaimer overlay and confirmed Success-to-Overview transition.
- Opt-in capture confirmation works in detached IP Sessions; plain-text export and full-screen/multi-monitor window support.
- Individual and combined WAN speed tests, three-column results, charts and text export with data-use and variability notices.
- IPv4 ping/trace, route editor guidance/warnings, assignment counts/charts, consistent fonts and adapter property help.
- Prominent raised Stop button, accurate selected-WAN participation, WSL Overview filtering and normal tray engine exit.
- Per-user x64 installer; no drivers or Windows service are installed.

## Download

[Windows x64 installer](https://github.com/mallyonline/WAN-Manager-Releases/releases/download/v0.1.0-preview.2/WAN-Manager-2026.10.18.8-Setup-x64.exe) and SHA256SUMS.txt are attached to this release. Read GETTING-STARTED.md before installation. The previous portable preview remains available for history; do not overwrite a working setup with its older files.

## Verification and limits

Modern/Framework builds, offline wizard/management/capture lifecycle/speed/IPC tests and rendered light/dark layouts passed. The local .8 installation verified 298 packaged files on 18 October; refreshed documentation packaging is separately checked before publication. Live speed testing worked in the preceding .7 build and was confirmed by the user; no benchmark result is a performance guarantee.

Clean-machine, broader Windows 11, sustained streaming, hot-plug/rollback, native file-picker/multi-monitor and capture/player acceptance remain open. Historical intermittent stalls and uneven throughput are not represented as conclusively fixed. Single-flow bonding, guaranteed VPN aggregation and automatic network rollback are not supported claims.

The compatibility engine remains a separate elevated .NET Framework process. The application is unsigned and retains a legacy VC++ 2010 dependency. Npcap/Nmap and TAP installers are not bundled. Full adapter-profile editing, Windows Service extraction, packet metadata and optional video/download panels remain future work.

Source remains private. Licence notices accompany the binaries. [Getting started](GETTING-STARTED.md) Â· [User guide](USER-GUIDE.md) Â· [Troubleshooting](TROUBLESHOOTING.md) Â· [Recovery](https://github.com/mallyonline/WAN-Manager-Releases/blob/main/RECOVERY.md).
