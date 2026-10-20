# WAN Manager

A Windows x64 workspace for multiple internet connections, connection-level IPv4 load balancing and live network diagnostics.

**Current prerelease: 0.1.0-preview.3 Â· UI 2026.10.20.1 / engine 2026.10.18.8.** Documentation refreshed 20 October 2026. Evaluation software: broader clean-machine, sustained-stream and recovery testing remains open.

[Download Windows x64 installer](https://github.com/mallyonline/WAN-Manager-Releases/releases/download/v0.1.0-preview.3/WAN-Manager-2026.10.20.1-Setup-x64.exe) Â· [Release and checksums](https://github.com/mallyonline/WAN-Manager-Releases/releases/tag/v0.1.0-preview.3) Â· [Getting started](GETTING-STARTED.md) Â· [User guide](USER-GUIDE.md) Â· [Troubleshooting](TROUBLESHOOTING.md) Â· [Release notes](RELEASE-NOTES.md)

## What it does

- Guided setup loads the background engine, checks connections and readiness, then asks you to choose at least two reachable WANs and accept the disclaimer.
- Overview shows stable adapter cards, live throughput, WAN share and simultaneous combined session peak.
- Modern IP Sessions includes opt-in Byte Counter, filtering, plain-text export and a detachable/full-screen window.
- Routes includes saved routes, guarded editing, IPv4 ping/trace and assignment counts/charts. Settings includes TAP settings and adapter property help.
- Speed test compares each selected WAN with combined throughput and exports results to text. Light/dark/system appearance and a global Stop control are included.

## Before installing

The installer includes the modern .NET runtime and compatibility engine. It does not install a Windows service or network drivers. Balancing requires separately installed .NET Framework 4.8, the legacy x64 VC++ 2010 runtime, compatible Npcap and TAP-Windows components; see Getting started. Keep working drivers installed. The app is unsigned.

Load balancing distributes connections; it is not single-stream bonding. A poor WAN may reduce performance. VPN/kill-switch combinations are not guaranteed. Byte Counter may affect media players. Speed results are a time-specific measurement, not guaranteed future capacity. Historical stalls and uneven throughput have been reported; recent successful tests do not establish universal reliability.

## Install, upgrade and stop

Stop balancing, exit the background engine normally and close the workspace before upgrading. Run the installer, open WAN Manager from its shortcut and follow Setup & help. Close workspace leaves the engine running. Use the red Stop button to stop balancing, then Settings > Exit engine or the engine tray Exit option to end it.

[Recovery guide](https://github.com/mallyonline/WAN-Manager-Releases/blob/main/RECOVERY.md) Â· [All releases, including older portable builds](https://github.com/mallyonline/WAN-Manager-Releases/releases) Â· [Report an issue](https://github.com/mallyonline/WAN-Manager-Releases/issues)

This public repository contains downloads and documentation only; development source remains private. Based on Network Manager by SortByte. Original MIT and third-party notices accompany downloads. Do not upload unredacted IPs, stream URLs/tokens, configuration or packet contents in issue reports.

## Dependency setup

Choose **Install Missing Dependencies** in Settings or the welcome wizard. Missing prerequisites are downloaded from official vendors and their signatures verified before setup opens. Approve Windows elevation and vendor terms. Working components are skipped. Stop balancing and exit the background engine before installing; the workspace stays open. See [Getting started](GETTING-STARTED.md) for details.
