# WAN Manager 0.1.0-preview.3

UI **2026.10.20.1**; unchanged background engine **2026.10.18.8**. Published 20 October 2026 as an evaluation prerelease.

## New in this release

- Install Missing Dependencies is available in Settings and the welcome wizard.
- Detects .NET Framework 4.8, Visual C++ 2010 SP1 x64, Npcap compatibility libraries/driver and an installed TAP-Windows adapter.
- Downloads only missing components directly from official vendor hosts, verifies Windows signatures and expected publishers, then opens vendor installers one at a time.
- Preserves detected components. Requires the background engine to be closed before installing. No silent installation, driver removal or automatic reboot.
- Shows progress and errors, stops on cancellation/failure/restart requirements, and rechecks installed components. Returning to the wizard resumes discovery/readiness after successful detection.

Npcap requires user acceptance of its licence and WinPcap API-compatible Mode. No third-party installer is bundled. The TAP download is the legacy standalone 9.24.7 installer; working existing TAP drivers are not upgraded. VC++ 2010 remains a legacy requirement.

## Download and upgrade

[Download the Windows x64 installer](https://github.com/mallyonline/WAN-Manager-Releases/releases/download/v0.1.0-preview.3/WAN-Manager-2026.10.20.1-Setup-x64.exe). SHA256SUMS.txt is attached. Stop balancing, exit the engine and close the workspace before upgrading. The app installer is unsigned.

## Verification and limits

Build, offline dependency workflow tests and wizard/management regressions passed. Headless layout checked. All four vendor downloads had valid expected-publisher signatures on 20 October 2026. Existing dependencies were detected on the development PC. No vendor installer was run during these tests; clean-machine installation still needs hands-on validation.

The load-balancing engine is unchanged. This release does not claim to fix historical intermittent stalls, guarantee VPN compatibility or combine a single connection across WANs. Existing capture/player, sustained streaming, hot-plug/recovery and broader Windows acceptance remain open. No Windows service is installed.

[Getting started](GETTING-STARTED.md) | [User guide](USER-GUIDE.md) | [Troubleshooting](TROUBLESHOOTING.md)
