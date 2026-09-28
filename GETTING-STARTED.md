# Getting started

## Requirements

Windows x64. The development/test machine uses Windows 10; broad Windows 11 and clean-machine validation are pending. The modern desktop includes its .NET 10 runtime; no separate .NET 10 installation or Windows service is needed. The compatibility engine needs .NET Framework 4.8 and administrator elevation.

For load balancing, separately install the x64 Visual C++ 2010 runtime required by the legacy Pcap.Net capture layer, Npcap with WinPcap-compatible API support, and a compatible TAP-Windows adapter (tap0901). Obtain prerequisites only from official sources:

- Microsoft .NET Framework 4.8: https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48
- Microsoft Visual C++ runtimes (find the 2010 entry): https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist
- Npcap: https://npcap.com/#download — review the vendor's licence for your use. Npcap is not redistributed here.
- OpenVPN TAP-Windows: https://github.com/OpenVPN/tap-windows6/releases — driver installation is separate; do not install a VPN client merely to use WAN Manager. Compatibility with every current driver package is not certified by this preview.

Keep working prerequisites already installed. Do not uninstall another application's network adapters to install this preview.

## First run

1. Extract the whole ZIP to a writable folder outside Program Files. Keep the engine subfolder and runtime DLLs together.
2. Run WanManager.Desktop.exe. It can show local adapter activity without the engine or capture.
3. Choose Load balancing > Open compatibility controls to launch engine/Network_Manager.exe. Approve Windows elevation if you choose to run network controls. No capture starts just by opening the modern workspace.
4. Use Refresh adapters, select two independently reachable WANs, and Check availability. Review collapsed Readiness details if checks fail. Start balancing only when the chosen setup is ready.
5. Reopen test streams/downloads after starting so new connections can use TAP. Equal assignment counts do not guarantee equal bandwidth. Some existing connections may continue on physical WANs.
6. Stop load balancing before quitting the engine. Closing the modern workspace alone leaves the engine running. Never treat closing its window as proof that balancing stopped.

Byte Counter is off by default. Enable it only when needed; capture may interrupt external players. Phone Wi-Fi, tethering/VPN and PC kill-switch settings affect results. WAN Manager does not automatically change VPN protection to make checks pass.

## Upgrade / remove

Stop balancing, quit the old engine normally and close its modern workspace. Back up the old engine/Network_Manager.xml locally. Extract the new release separately. For existing testers, copy that XML into the new engine folder only after the old engine has exited; review inherited saved routes/startup options. No user configuration is included in the download.

To remove, stop balancing and exit both processes, then remove the extracted folder. Drivers are external and may be shared; leave their removal to their official installers and your own configuration review. See RECOVERY.md for network recovery. Binary rollback does not restore prior metrics/routes automatically.

## Report a problem

Use Issues in https://github.com/mallyonline/WAN-Manager-Releases and include version, Windows version, adapter types, whether VPN/kill switch was active, steps, expected/actual results and whether streams began before balancing. Redact public/local IPs, stream URLs/tokens and personal data from screenshots/logs. Do not upload Network_Manager.xml or full packet payloads without reviewing them. Logs are local in the engine folder; WAN Manager does not automatically upload them.
