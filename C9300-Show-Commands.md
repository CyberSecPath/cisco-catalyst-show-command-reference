# Cisco Catalyst 9300 Show Command Reference

## Overview

This guide covers common show commands for Cisco Catalyst 9300 series switches. It focuses on access-layer operations, endpoint connectivity, VLAN verification, Power over Ethernet (PoE), Layer 2 switching, and system health.

Commands are intended for monitoring and troubleshooting. Availability and output may vary by hardware model and Cisco IOS XE version.

## 1. System Information and Health

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show version` | Identify software and hardware information. | IOS XE version, uptime, model, and system image. |
| `show inventory` | Review installed hardware components. | Product IDs and component inventory. |
| `show switch` | Inspect physical switch-stack membership. | Member numbers, roles, and reported states on supported configurations. |
| `show environment all` | Review environmental information where supported. | Temperature, fan, and power status. |
| `show logging` | Review system messages. | Link flaps, authentication failures, and recurring errors. |
| `show processes cpu` | Inspect CPU utilization. | High utilization or unusual process activity. |
| `show processes memory` | Review process memory usage. | Unusual memory consumption or resource pressure. |

## 2. Interfaces and Connectivity

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show interfaces status` | Quickly review port status. | Unexpected `notconnect`, `disabled`, or other abnormal states. |
| `show interfaces description` | Review interface descriptions and status. | Missing descriptions and unexpected interface states. |
| `show interfaces` | Inspect detailed interface statistics. | Operational state, speed, duplex, traffic, and errors. |
| `show interfaces counters errors` | Investigate interface error counters. | CRC errors, input errors, and other abnormal counters. |
| `show interfaces <interface> switchport` | Verify Layer 2 port settings. | Access/trunk mode and VLAN assignment. |
| `show interfaces transceiver detail` | Inspect optical diagnostics where supported. | Optical levels, temperature, and transceiver alarms. |

Replace `<interface>` with the appropriate interface identifier, such as `GigabitEthernet1/0/1`.

## 3. VLANs and Layer 2 Switching

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show vlan brief` | Review VLANs and access-port assignments. | Expected VLANs, active status, and port membership. |
| `show interfaces trunk` | Review trunk ports. | Trunk status and allowed/active VLANs. |
| `show mac address-table` | Inspect learned MAC addresses. | Expected MAC addresses, VLANs, and interfaces. |
| `show spanning-tree` | Review spanning-tree operation. | Root bridge information, port roles, and states. |
| `show spanning-tree summary` | Review spanning-tree mode and summary. | Configured mode and reported status. |
| `show etherchannel summary` | Check EtherChannel bundles. | Whether expected member interfaces are bundled and operational. |

## 4. IP Addressing and Routing

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show ip interface brief` | Review Layer 3 interface addresses and status. | Expected IP addresses and operational state. |
| `show ip route` | Inspect the IPv4 routing table. | Expected routes, next hops, and default route where required. |
| `show arp` | Review IPv4-to-MAC address mappings. | Whether expected neighboring devices have learned entries. |

## 5. Neighbor Discovery, Authentication, and Access Lists

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show cdp neighbors` | Identify directly connected Cisco devices. | Neighbor identity, local interface, and remote port. |
| `show lldp neighbors` | Identify devices advertising LLDP information. | Neighbor identity and connected interfaces. |
| `show authentication sessions` | Inspect port-based authentication sessions where supported. | Session state and authentication information. |
| `show ip access-lists` | Review configured IPv4 access lists. | Relevant entries and match counters. |

## 6. Power over Ethernet

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show power inline` | Review PoE status on supported hardware. | Power allocation, delivery status, and available power budget. |

## Troubleshooting Workflows

### Scenario 1: An endpoint cannot connect

Start with:

```text
show interfaces status
show interfaces description
show vlan brief
show interfaces <interface> switchport
show mac address-table
show authentication sessions
```

**Investigation steps:**

1. Check whether the interface is operational.
2. Verify that the port is assigned to the expected VLAN.
3. Check whether the endpoint's MAC address is learned in the expected VLAN.
4. If authentication is configured, inspect the session state.
5. If the issue remains unresolved, investigate physical connectivity, endpoint settings, and upstream network connectivity.

### Scenario 2: An interface reports errors

Start with:

```text
show interfaces <interface>
show interfaces counters errors
show logging
```

**Investigation steps:**

1. Review interface statistics and error counters.
2. Determine whether error counters are increasing over time, if repeated measurements are available.
3. Check logs for link flaps or related events.
4. Investigate the physical connection, transceiver, speed/duplex compatibility, and connected device as appropriate.

A nonzero counter alone does not establish the cause of a fault.

### Scenario 3: A device cannot reach another network

Start with:

```text
show ip interface brief
show ip route
show arp
show interfaces trunk
```

**Investigation steps:**

1. Verify the relevant Layer 3 interfaces are operational.
2. Check whether a route exists to the destination network.
3. Review ARP information for the relevant local neighbor or next hop.
4. If the path crosses VLANs or trunks, verify that the required VLANs and links are operational.
5. Continue with authorized connectivity testing and upstream-device checks.

## Notes

- These commands are primarily for verification and troubleshooting.
- Command availability varies by model, software version, and enabled features.
- Physical stacking, PoE, transceiver diagnostics, and authentication features depend on the hardware and deployment.
- This guide is a general reference and does not represent a production switch configuration.
