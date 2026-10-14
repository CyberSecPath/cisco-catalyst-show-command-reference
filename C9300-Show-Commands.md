# Cisco Catalyst 9300 Show Command Reference

## Overview

This guide covers common show commands for Cisco Catalyst 9300 switches. It emphasizes access-layer operations, endpoint connectivity, VLAN verification, Power over Ethernet, Layer 2 switching, and routine system checks.

Command availability and output may vary by hardware model and IOS XE version.

## 1. System Information and Health

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show version` | Identify software and hardware information. | IOS XE version, uptime, model, and system image. |
| `show inventory` | Review installed hardware components. | Product IDs, serial numbers, and component inventory. |
| `show switch` | Inspect physical switch-stack membership. | Member numbers, roles, and reported states on supported stack configurations. |
| `show environment all` | Review available environmental information. | Temperature, fan, and power status where supported. |
| `show logging` | Review system messages. | Link flaps, authentication failures, hardware events, and recurring errors. |
| `show processes cpu` | Inspect CPU utilization. | High utilization and processes consuming CPU. |
| `show processes memory` | Review process memory usage. | Unusual memory consumption or resource pressure. |

## 2. Interfaces and Connectivity

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show interfaces status` | Quickly review port status. | Unexpected `notconnect`, `disabled`, or other abnormal states. |
| `show interfaces description` | Review interface descriptions and status. | Missing descriptions or unexpected interface states. |
| `show interfaces` | Inspect detailed interface statistics. | Operational state, speed, duplex, errors, and traffic. |
| `show interfaces counters errors` | Investigate interface error counters. | CRC errors, input errors, and other abnormal counters. |
| `show interfaces <interface> switchport` | Verify Layer 2 port settings. | Access/trunk mode, administrative mode, and VLAN assignment. |
| `show interfaces transceiver detail` | Inspect optical transceiver diagnostics where supported. | Optical transmit/receive levels, temperature, and alarm indicators. |

Replace `<interface>` with an interface identifier, such as `GigabitEthernet1/0/1` or `TenGigabitEthernet1/1/1`, as applicable to the model.

## 3. VLANs and Layer 2 Switching

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show vlan brief` | Review VLANs and access-port assignments. | Expected VLANs, active status, and port membership. |
| `show interfaces trunk` | Review trunk ports. | Trunk status, encapsulation where displayed, and allowed/active VLANs. |
| `show mac address-table` | Inspect learned MAC addresses. | Whether expected MAC addresses appear on the correct VLAN and port. |
| `show spanning-tree` | Review spanning-tree operation. | Root bridge information, port roles, and port states. |
| `show spanning-tree summary` | Review spanning-tree mode and summary information. | Configured mode and indications of inconsistent settings. |
| `show etherchannel summary` | Check EtherChannel bundles. | Whether expected member interfaces are bundled and operational. |

## 4. IP Addressing and Routing

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show ip interface brief` | Review Layer 3 interface addresses and status. | Expected IP addresses and interfaces that are down. |
| `show ip route` | Inspect the IPv4 routing table. | Expected routes, next hops, and the default route where required. |
| `show arp` | Review IPv4-to-MAC address mappings. | Whether expected neighboring devices have learned entries. |

## 5. Discovery, Authentication, and Access Controls

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show cdp neighbors` | Identify directly connected Cisco devices. | Neighbor identity, local interface, and remote port. |
| `show lldp neighbors` | Identify devices advertising LLDP information. | Neighbor identity and connected interfaces. |
| `show authentication sessions` | Inspect port-based authentication sessions. | Session state, authentication method, and assigned access information where supported. |
| `show ip access-lists` | Review configured IPv4 access lists and counters. | Relevant entries and match counters. |

## 6. Power over Ethernet

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show power inline` | Review PoE status on supported switches and interfaces. | Power allocation, delivery status, and available power budget. |

## Troubleshooting Scenarios

### Scenario 1: An endpoint cannot connect to the network

Start with:

```text
show interfaces status
show interfaces description
show vlan brief
show interfaces <interface> switchport
show mac address-table
show authentication sessions
```

**Investigation:**
1. Confirm that the interface is in the expected operational state.
2. Check whether the port is assigned to the correct VLAN.
3. Look for the endpoint's MAC address in the expected VLAN.
4. If port-based authentication is used, inspect the session state.
5. If the issue remains unresolved, investigate cabling, endpoint configuration, upstream connectivity, and relevant logs as appropriate.

### Scenario 2: An interface reports errors

Start with:

```text
show interfaces <interface>
show interfaces counters errors
show logging
```

**Investigation:**
1. Review the interface's error counters and operational statistics.
2. Determine whether errors are increasing over time, if repeated measurements are available.
3. Review logs for link flaps or related events.
4. Investigate physical connections, optics, speed/duplex compatibility, and the connected device as appropriate.

A nonzero counter alone does not establish the cause of a fault.

### Scenario 3: A device cannot reach another network

Start with:

```text
show ip interface brief
show ip route
show arp
show interfaces trunk
```

**Investigation:**
1. Verify that the relevant Layer 3 interfaces are operational.
2. Check for a route to the destination network.
3. Review ARP information for the next hop or local neighbor.
4. If traffic crosses VLANs or trunks, verify that the required VLANs and links are operational.
5. Continue with authorized end-to-end testing and upstream-device checks.

## Notes

- These are primarily verification and troubleshooting commands; they do not intentionally change device configuration.
- Output varies by platform, software version, interface type, and feature configuration.
- Physical stacking, PoE, transceiver diagnostics, and authentication features depend on the particular hardware and deployment.
- Use placeholders appropriate to the target device and follow organizational access procedures.
