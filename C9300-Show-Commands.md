# Cisco Catalyst 9300 Show Command Reference

## Overview

This project documents commonly used Cisco Catalyst 9300 show commands for network monitoring, verification, and troubleshooting.

The reference is intended for learning and professional development in network support, NOC operations, network administration, and cybersecurity.

All examples are generic and contain no customer or production network information.

## Command Reference

| Command | Explanation |
|---|---|
| `show version` | Displays the IOS XE software version, switch model, uptime, and system information. |
| `show inventory` | Displays hardware inventory and installed components. |
| `show switch` | Displays switch stack members, roles, priorities, and status. |
| `show interfaces status` | Shows interface status, VLAN, speed, duplex, and interface type. |
| `show interfaces description` | Displays interface descriptions and operational status. |
| `show interfaces` | Displays detailed interface statistics, traffic information, and errors. |
| `show interfaces counters errors` | Helps identify interface errors that may indicate connectivity or physical-layer issues. |
| `show interfaces <interface> switchport` | Shows Layer 2 switchport configuration and operational information for an interface. |
| `show vlan brief` | Lists configured VLANs and associated access ports. |
| `show interfaces trunk` | Displays trunk ports and their VLAN information. |
| `show mac address-table` | Displays MAC addresses learned by the switch and their associated ports. |
| `show spanning-tree` | Displays Spanning Tree Protocol status and information. |
| `show etherchannel summary` | Shows EtherChannel groups and the status of their member links. |
| `show ip interface brief` | Summarizes Layer 3 interfaces, IP addresses, and operational status. |
| `show ip route` | Displays the IPv4 routing table. |
| `show arp` | Shows mappings between IPv4 addresses and MAC addresses. |
| `show cdp neighbors` | Identifies directly connected Cisco devices. |
| `show lldp neighbors` | Identifies neighboring devices discovered through LLDP. |
| `show logging` | Displays system log messages that can help identify errors and operational events. |
| `show processes cpu` | Displays CPU utilization and process information. |
| `show processes memory` | Displays memory utilization and process information. |
| `show environment` | Displays available hardware environmental information, such as temperature and power status. |
| `show power inline` | Displays Power over Ethernet status and power usage on supported interfaces. |
| `show authentication sessions` | Displays access-authentication session information where supported and configured. |
| `show ip access-lists` | Displays configured IPv4 access control lists and their entries. |

## Common Troubleshooting Examples

### Interface Connectivity

Use these commands to investigate interface status, descriptions, and errors.

```text
show interfaces status
show interfaces description
show interfaces counters errors
```

### VLAN and Switching

Use these commands to verify VLAN membership, trunk configuration, and learned MAC addresses.

```text
show vlan brief
show interfaces trunk
show mac address-table
```

### Network Connectivity

Use these commands to review Layer 3 interface status, routing, and ARP information.

```text
show ip interface brief
show ip route
show arp
```

### Stack and System Health

Use these commands to check stack status, logs, and system resource utilization.

```text
show switch
show logging
show processes cpu
show processes memory
```

## Notes

- Replace `<interface>` with the appropriate interface identifier.
- Command availability and output can vary by IOS XE version, hardware, and configuration.
- These are verification and monitoring commands; they do not replace a complete troubleshooting process.
- This project is a generic technical reference, not a claim that every command has been used in a production environment.

## Skills Demonstrated

- Cisco IOS XE command familiarity
- Network monitoring and troubleshooting concepts
- Layer 2 switching and VLANs
- Layer 3 routing fundamentals
- Interface and system health verification
- Technical documentation
