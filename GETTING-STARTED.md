# Getting started - UI 2026.10.20.1

## Requirements

Windows x64; installer minimum Windows 10 1809. This is a packaging floor, not a claim of support for every Windows build. Use a supported, updated operating system; broad Windows 11 and clean-machine validation remain pending. The Avalonia workspace bundles .NET 10; the elevated engine uses .NET Framework 4.8. No Windows service installation is required.

Use **Install Missing Dependencies** in the welcome wizard or Settings to check and install the required components. Working components are retained. Downloads come directly from official vendors; approve UAC and complete each installer. Stop balancing and exit the background engine before installing dependencies. Enable WinPcap API-compatible Mode in Npcap setup. Return to the wizard after installation for fresh readiness checks.

Load balancing requires these components: Official links checked 20 October 2026:

- [.NET Framework 4.8](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48).
- [Microsoft VC++ runtime downloads](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist): the legacy Pcap.Net layer needs **2010 SP1 x64**. Microsoft lists this as unsupported legacy software; installing only the newest v14 runtime does not replace this requirement. Engine dependency modernization remains planned.
- [Npcap](https://npcap.com/#download), with WinPcap-compatible API support. Review the vendor licence for your use. It is not bundled.
- [Compatible TAP-Windows adapter (tap0901)](https://github.com/OpenVPN/tap-windows6/releases). Compatibility with every package is not certified. Do not install a VPN client merely to use WAN Manager.

Keep working prerequisites. Do not uninstall shared network adapters or replace drivers simply because a newer package exists.

## Install or upgrade

1. If upgrading, use Stop, then Settings > Exit engine (balancing stopped), and close the workspace. The installer refuses to update running instances.
2. Back up the old engine's `Network_Manager.xml` locally after it exits. Do not publish that file.
3. Download `WAN-Manager-2026.10.20.1-Setup-x64.exe` and `SHA256SUMS.txt` from [preview.2](https://github.com/mallyonline/WAN-Manager-Releases/releases/tag/v0.1.0-preview.3). Run `Get-FileHash .\WAN-Manager-2026.10.20.1-Setup-x64.exe -Algorithm SHA256` and compare the installer entry. Hash matching verifies file integrity, not publisher trust; the installer is unsigned.
4. Run the installer. It installs per user under `%LOCALAPPDATA%\Programs\WAN Manager`. Existing settings are retained; portable settings are not automatically imported. Do not copy old configuration over an installed working setup without reviewing it.
5. Open WAN Manager using its Start menu shortcut. No engine or balancing starts merely by installing it.

## Guided first run

1. Open Setup & help and choose Load Controls. Approve Windows elevation if you intend to run the engine.
2. Connection discovery and readiness checks progress automatically. Completed steps show green ticks; technical details appear on the left. If a check fails, resolve that issue and retry.
3. Use independent internet sources, such as home broadband plus a phone using cellular data. PC-side checks cannot prove the phone's Wi-Fi/VPN configuration.
4. Select **at least TWO reachable WANs**. Read the disclaimer overlay, accept it, then choose Start Load Balance. Additional WANs have Previous/More buttons.
5. Start rechecks the selected WANs, including public-IP reachability. Confirmed Running displays Success and opens Overview. An address alone is not proof of independent capacity: VPNs and carrier NAT can alter the observed IP.
6. Open fresh streams/downloads to exercise new flow assignments. Existing connections can remain on their earlier path.

Use the red Stop button whenever you need to stop balancing. Closing the workspace alone leaves balancing running. Byte Counter stays off until you explicitly enable it.

## Remove or roll back

Stop balancing, exit the engine and close the workspace. Uninstall through Windows Installed apps / Apps & features. User-created configuration/logs may remain; external drivers remain installed. Preserve a configuration backup before replacing a newer build with an older one; compatibility is not guaranteed. Binary rollback does not restore prior routes or metrics. See [Recovery](https://github.com/mallyonline/WAN-Manager-Releases/blob/main/RECOVERY.md).

Continue with the [User guide](USER-GUIDE.md) or [Troubleshooting](TROUBLESHOOTING.md).
