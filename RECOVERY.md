# Network recovery procedure (manual, before experimental changes)

The baseline task took a read-only snapshot of adapters, IPv4/IPv6 addresses, interface DHCP/metrics, routes and DNS in the local baseline backup's network-state folder. Nothing was applied to the machine.

1. Keep a local copy of this document, the known baseline build and the snapshot before a network-changing experiment.
2. Record which WAN/VPN connections are intended to be active. A phone's tethering address/gateway can change; old snapshot addresses are evidence, not instructions to reapply them.
3. If an experiment disrupts connectivity, first use WAN Manager's normal Stop operation while its controller is responsive. Observe whether its TAP/routes are removed as intended.
4. Compare the current configuration with the pre-test snapshot. Restore only settings demonstrably changed by the experiment, on the correctly identified adapter GUID. Do not bulk-import captured routes, delete all default routes, or reset every adapter.
5. Keep Proton and its kill switch under the user's control. A VPN blocking direct access may be intentional; do not disable protection as an automatic recovery step.
6. For a tethering reconnect, obtain current DHCP configuration and verify its current gateway instead of restoring a stale mobile address. Confirm physical WAN reachability and then the intended VPN path.
7. If the GUI cannot stop the engine, preserve logs before manual intervention. Force-killing the app is not a guaranteed route rollback. Use the captured evidence to identify the exact owned TAP/route changes before correcting them.
8. Return to the versioned baseline build only after network state is understood. Binary rollback alone does not restore network configuration.

This is a cautious manual recovery procedure, not an automated restore tool or a successfully tested crash-recovery guarantee. Automated ownership-aware rollback is a service-migration acceptance requirement.
