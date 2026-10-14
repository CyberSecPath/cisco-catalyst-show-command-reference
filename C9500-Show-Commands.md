# Cisco Catalyst 9500 Show Command Reference

## Overview

This project documents commonly used Cisco Catalyst 9500 show commands for network monitoring, verification, and troubleshooting.

The reference focuses on core and distribution switching, Layer 2 and Layer 3 operations, interface health, routing, and system diagnostics.

All examples are generic and contain no customer or production network information.

## Command Reference

| Command | Explanation |
|---|---|
| `show version` | Displays the IOS XE software version, switch model, uptime, and system information. |
| `show inventory` | Displays hardware inventory and installed components. |
| `show running-config` | Displays the currently active configuration. |
| `show startup-config` | Displays the saved configuration used during startup. |
| `show interfaces status` | Summarizes interface status, VLAN, speed, duplex, and interface type. |
| `show interfaces description` | Displays interface descriptions and operational status. |
| `show interfaces` | Displays detailed interface statistics, traffic information, and errors. |
| `show interfaces counters errors` | Helps identify interface errors that may indicate link or communication problems. |
| `show interfaces transceiver detail` | Displays detailed optical transceiver information where supported. |
| `show interfaces trunk` | Displays trunk interfaces and their VLAN information. |
| `show vlan brief` | Lists configured VLANs and associated access ports. |
| `show mac address-table` | Displays MAC addresses learned by the switch and their associated ports. |
| `show spanning-tree` | Displays Spanning Tree Protocol status and information. |
| `show spanning-tree summary` | Provides a summary of Spanning Tree status and configuration. |
| `show etherchannel summary` | Shows EtherChannel groups and the status of member links. |
| `show interfaces port-channel` | Displays operational information and statistics for port-channel interfaces. |
| `show ip interface brief` | Summarizes Layer 3 interfaces, IP addresses, and operational status. |
| `show ip route` | Displays the IPv4 routing table. |
| `show ip route summary` | Provides a summary of the IPv4 routing table. |
| `show arp` | Shows IPv4-to-MAC address mappings maintained by the switch. |
| `show ip protocols` | Displays information about configured IP routing protocols. |
| `show cdp neighbors` | Identifies directly connected Cisco devices. |
| `show lldp neighbors` | Identifies neighboring devices discovered through LLDP. |
| `show logging` | Displays system log messages that can help identify operational events and errors. |
| `show processes cpu` | Displays CPU utilization and process information. |
| `show processes memory` | Displays memory utilization and process information. |
| `show environment` | Displays available hardware environmental information, including temperature and power status. |
| `show redundancy` | Displays redundancy and high-availability information where supported. |
| `show platform` | Displays platform-specific hardware and software information. |
| `show authentication sessions` | Displays access-authentication session information where supported and configured. |
| `show ip access-lists` | Displays configured IPv4 access control lists and their entries. |

## Common Troubleshooting Examples

### Uplink and Interface Problems

Use these commands to review interface state, descriptions, errors, and trunk configuration.

```text
show interfaces status
show interfaces description
show interfaces counters errors
show interfaces trunk
```

### VLAN and Switching Problems

Use these commands to verify VLAN configuration, learned MAC addresses, and Spanning Tree behavior.

```text
show vlan brief
show mac address-table
show spanning-tree
show spanning-tree summary
```

### Routing and Connectivity Problems

Use these commands to review Layer 3 interfaces, routing information, and ARP entries.

```text
show ip interface brief
show ip route
show ip route summary
show arp
```

### EtherChannel and Redundancy

Use these commands to examine link aggregation and available redundancy information.

```text
show etherchannel summary
show interfaces port-channel
show redundancy
```

### System Health

Use these commands to review system logs, processor usage, memory, and hardware status.

```text
show version
show logging
show processes cpu
show processes memory
show environment
```

## Notes

- Command availability and output can vary by Catalyst 9500 model, IOS XE version, license, and configuration.
- Replace interface placeholders with the appropriate interface identifier when using interface-specific commands.
- These commands are for monitoring and verification; they do not replace a complete troubleshooting process.
- This project is a generic technical reference, not a claim that every command has been used in a production environment.

## Skills Demonstrated

- Cisco IOS XE command familiarity
- Core and distribution switching concepts
- Layer 2 switching and VLANs
- Layer 3 routing fundamentals
- Uplink and EtherChannel verification
- Network monitoring and troubleshooting concepts
- Technical documentation
