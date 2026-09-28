# WAN Manager 0.1.0-preview.1

First public Windows x64 prerelease. Build 2026.9.28.3. For evaluation on a recoverable test setup; this is not a production-stability release.

## Included

- Modern .NET 10 / Avalonia desktop: live adapter graphs, stable card positions, combined traffic and simultaneous session peak, light/dark/system/night themes.
- WAN selection, availability checks and Start/Stop. Independent round-robin assignment of new TCP and UDP flows; existing connections remain pinned.
- Per-WAN flow-assignment counters, local URL diagnostics, compatibility IP Sessions and adapter/routing tools.
- Byte Counter is opt-in. Shutdown/restart handling prevents overlapping capture workers.
- Manual updates; no legacy upstream automatic updater. No network drivers are bundled.

## Known limitations

- Intermittent throughput stalls and uneven sustained traffic remain under investigation. Recovery to normal speeds has been observed; packet loss and root cause are not established. Equal flow counts do not mean equal Mbps.
- Physical-adapter graphs include traffic outside the balancer. Connections opened before balancing may keep using a physical interface. Combined throughput is observed traffic, not a speed test or proof of bonding.
- VPN detection is advisory; VPN/kill-switch/split-tunnel compatibility is not guaranteed. This is connection-level IPv4 balancing, not single-connection bonding or a VPN aggregation service.
- Engine requires administrator elevation and .NET Framework 4.8. It remains a separate compatibility process, not an installed Windows service. IP Sessions/full settings still use compatibility controls.
- Capture can affect media playback. Byte Counter is OFF by default. IPv6 and VPN-tunnel capture coverage are limited.
- Existing engine metric changes persist; stopping or replacing the binary is not a guaranteed network rollback. Review RECOVERY.md before testing. Hot-plug/crash recovery and clean-machine installation need broader acceptance testing.
- Application binaries are unsigned. Prerequisite installers are obtained independently from their official vendors. This download has no automatic installer or auto-update service.

## Download and verify

Download the Windows-x64 ZIP and SHA256SUMS.txt from this release. Compare `Get-FileHash .\WAN-Manager-0.1.0-preview.1-windows-x64.zip -Algorithm SHA256` with SHA256SUMS.txt, extract the complete folder, and read GETTING-STARTED.md. Do not run from inside the ZIP.

No Npcap/Nmap, TAP driver installer, personal settings, IP addresses, logs, test executables or signing tools are included. The source repository remains private; this repository hosts downloads and public documentation only. Third-party licence notices are included with the binary.
