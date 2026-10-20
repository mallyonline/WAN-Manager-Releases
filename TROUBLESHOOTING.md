# Troubleshooting

Applies to 2026.10.18.8. Preserve working configuration and change one thing at a time.

| Symptom | What to check |
|---|---|
| Engine unavailable | Use Load Controls and approve elevation. Verify the installer placed the engine folder next to the workspace. Cancelled UAC is retryable; reinstalling drivers is not the first step. |
| Fewer than two WANs | Check cable/tethering, adapter state and whether each connection has independent internet access. Phone Wi-Fi/VPN state must be checked on the phone. |
| Public IP blank / failed checks | Retry availability and inspect technical details. VPN/kill switch, captive portal, filtering or cellular availability can affect probes. Do not bypass VPN protection automatically. |
| Same public IP on multiple adapters | A common router/VPN or carrier NAT may be involved. This alone neither establishes nor disproves usable independent WANs. |
| Start unavailable | Select two reachable eligible WANs, finish readiness, read and accept the disclaimer. Changing selection revokes acceptance. |
| One WAN busy, another quiet | Existing flows stay pinned; streams burst and vary in size. Try fresh concurrent connections. Equal flow counts do not imply equal bandwidth. If playback degrades, Stop normally and compare each WAN independently. |
| Player stops after capture | Stop Byte Counter/UDP detection and retry the player. Capture is optional; record whether it caused a repeatable change. |
| Detached Byte Counter seems inactive | Its confirmation appears inside the detached pane. Confirm there, inspect capture state, and wait for initialization. Report any failure message; do not repeatedly start workers. |
| Ping/trace times out | ICMP may be filtered or unanswered. Compare URL access; a timeout cannot locate a firewall or prove a dead WAN. |
| Uninstall/update refuses | Stop balancing, exit the engine through Settings/tray, then close all workspaces including detached windows. |
| Network remains affected after stopping | Follow RECOVERY.md. Do not delete all gateways, reset every adapter or force-kill the engine expecting rollback. |

Report version, Windows version, adapter types, intended VPN/kill-switch state, exact steps and messages at https://github.com/mallyonline/WAN-Manager-Releases/issues. Redact IPs, stream URLs/tokens and configuration. Logs/configuration are local beside the engine. No automatic bug-report upload occurs.
