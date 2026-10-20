# WAN Manager user guide

Applies to build 2026.10.18.8; reviewed 20 October 2026.

| Page | Controls and interpretation |
|---|---|
| Overview | Current selected-WAN throughput and simultaneous session peak. Adapter peaks are separate; adding peaks from different moments is not a combined record. Graph history controls the recent window. Physical counters include other applications. WSL adapters are hidden from Overview. |
| Adapters | Inspect current connections. Only selected WANs participate in balancing; a virtual adapter being present does not mean it is balancing traffic. |
| Load balancing | Refresh adapters, check availability, select WANs and Start/Stop. Readiness details explain missing requirements. VPN detection is advisory; actual connectivity checks still apply. |
| IP Sessions | Filter process/address/protocol/family; select an endpoint for copy, resolution or route-editor preparation. Byte Counter and UDP detection are opt-in. Start opens a confirmation in the current session window. Stop capture if playback changes. |
| Detached IP Sessions | Undock / full screen creates a movable window. F11 toggles full screen, Escape restores, Dock back returns to the workspace. Export plain text saves the filtered rows, including addresses and process paths. |
| Routes | Inspect active/saved routes; Use selected route copies fields into the editor only. Add, update metric, delete, load or unload require separate confirmation and stopped balancing. Save for later stores a template without activating it. |
| Ping & trace | IPv4 ICMP probes using current Windows routing, not the selected editor adapter. Enter a hostname or IPv4 address, not a URL. Cancel stops the operation. Missing replies cannot identify a firewall or establish provider fault. |
| Balancing assignments | Current tracked TCP/UDP connections, per-WAN bars and recent count chart. Snapshot maximum 4,000 entries. Counts are not Mbps, fairness guarantees or packet-loss statistics. |
| Settings | Workspace preferences, TAP configuration, adapter visibility and labelled properties with ? help. Incorrect TAP addresses/subnets/DNS can break connectivity. Driver setup remains an explicit Windows/vendor operation. |
| Link quality | Check an HTTP/HTTPS URL over the current Windows route. HTTP 200 does not prove continuous playback, authentication longevity or per-WAN reachability. Do not share URLs containing private tokens. |

## Speed comparison

Start balancing on two to four WANs first. Open Speed test, read the data-use notice and explicitly start the test. Each WAN is measured separately, then parallel transfers run through TAP. With two WANs, cards show WAN 1, WAN 2 and Load Balanced. Additional cards wrap. Export results to plain text retains timestamps, stage status and limitations.

Cloudflare endpoints receive the ordinary public source IP. Each download/upload direction runs for up to eight seconds or 128 MiB payload per stage. Two WANs plus combined allows up to 768 MiB payload plus overhead. Cancellation leaves completed results but does not claim a successful full comparison.

The sum of individual measurements is an estimate made at different times. Combined results are measured simultaneous transfers. Graphs show cumulative test rates. Adapter activity includes background apps, so counters do not prove exclusive attribution to the test.

Results are a snapshot, not a future-performance guarantee. Signal, congestion, VPNs, hardware, test-server conditions and competing traffic change. Load balancing cannot turn an intermittent WAN into a reliable one, or ensure one stream uses both WANs.

## Safe routing and exit

More-specific routes take precedence; metrics help select equally specific routes. A wrong default route, gateway or mask can interrupt internet and remote access. Read the in-app editor help, preserve working values and review every confirmation. Historical mobile gateways should be left alone unless a specific fault is established.

Stop balancing using the red Stop control, exit the engine through Settings or its tray Exit option, then close the workspace. Closing the UI does not terminate balancing. Capture owned by the workspace is stopped on closure and has a disconnection expiry safeguard. No automatic route rollback or Windows Service recovery is guaranteed.

## Installing missing prerequisites (UI 2026.10.20.1)

Choose Install Missing Dependencies in Settings or Setup & help. Stop balancing and exit the engine first; the workspace stays open. Review missing components, allow downloads, and complete each signed vendor installer. For Npcap enable WinPcap API-compatible Mode. Cancellation or failure stops the sequence. Restart only if requested, then Check again. An installed TAP may still be unavailable to the engine: fresh wizard readiness checks determine usability.
