# Cisco Catalyst 9500 Show Command Reference

## Overview

This reference documents commonly used Cisco Catalyst 9500 show commands for network monitoring, routing, redundancy, and troubleshooting.

It emphasizes core and distribution switching, high-availability concepts, uplink verification, and system health.

All examples are generic and contain no customer, production, or proprietary network information.

## Command Reference

| Command | Explanation |
|---|---|
| `show stackwise-virtual` | Displays StackWise Virtual status and related information on supported platforms. |
| `show stackwise-virtual link` | Displays StackWise Virtual link information and operational status. |
| `show stackwise-virtual dual-active-detection` | Displays dual-active detection configuration and status. |
| `show redundancy` | Displays redundancy and high-availability information. |
| `show redundancy states` | Displays the current redundancy state and supervisor roles where supported. |
| `show version` | Displays the IOS XE software version, switch model, uptime, and system information. |
| `show inventory` | Displays hardware inventory and installed components. |
| `show running-config` | Displays the configuration currently active on the switch. |
| `show startup-config` | Displays the saved configuration used during startup. |
| `show boot` | Displays boot-related information and configured boot variables. |
| `show interfaces status` | Summarizes interface status, VLAN, speed, duplex, and interface type. |
| `show interfaces description` | Displays interface descriptions and operational status. |
| `show interfaces` | Displays detailed interface statistics, traffic information, and errors. |
| `show interfaces counters errors` | Displays interface error counters that can help identify link or communication problems. |
| `show interfaces <interface>` | Displays detailed operational information and statistics for a specific interface. |
| `show interfaces trunk` | Displays trunk interfaces and their VLAN information. |
| `show interfaces transceiver detail` | Displays detailed optical transceiver information where supported. |
| `show vlan brief` | Lists configured VLANs and associated access ports. |
| `show interfaces <interface> switchport` | Displays Layer 2 switchport configuration and operational information for an interface. |
| `show mac address-table` | Displays MAC addresses learned by the switch and their associated ports. |
| `show spanning-tree` | Displays Spanning Tree Protocol status and information. |
| `show spanning-tree summary` | Provides a summary of Spanning Tree status and configuration. |
| `show spanning-tree vlan <vlan-id>` | Displays Spanning Tree information for a specific VLAN. |
| `show etherchannel summary` | Shows EtherChannel groups and the status of their member links. |
| `show etherchannel detail` | Displays detailed information about configured EtherChannel groups. |
| `show interfaces port-channel` | Displays operational information and statistics for port-channel interfaces. |
| `show ip interface brief` | Summarizes Layer 3 interfaces, IP addresses, and operational status. |
| `show ip interface` | Displays detailed IP configuration and operational information for interfaces. |
| `show ip route` | Displays the IPv4 routing table. |
| `show ip route connected` | Displays routes associated with directly connected networks. |
| `show ip route static` | Displays statically configured IPv4 routes. |
| `show ip route summary` | Provides a summary of the IPv4 routing table. |
| `show ip protocols` | Displays information about configured IP routing protocols. |
| `show arp` | Displays IPv4-to-MAC address mappings maintained by the switch. |
| `show cdp neighbors` | Identifies directly connected Cisco devices discovered through CDP. |
| `show cdp neighbors detail` | Displays detailed information about neighboring Cisco devices. |
| `show lldp neighbors` | Identifies neighboring devices discovered through LLDP. |
| `show lldp neighbors detail` | Displays detailed LLDP neighbor information. |
| `show logging` | Displays system log messages that may help identify errors and operational events. |
| `show processes cpu` | Displays CPU utilization and process information. |
| `show processes memory` | Displays memory utilization and process information. |
| `show environment` | Displays available environmental information, such as temperature and power status. |
| `show platform` | Displays platform-specific hardware and software information. |
| `show platform software status control-processor brief` | Displays control-processor CPU and memory status where supported. |
| `show authentication sessions` | Displays access-authentication session information where supported and configured. |
| `show ip access-lists` | Displays configured IPv4 access control lists and their entries. |
| `show ntp status` | Displays Network Time Protocol synchronization status. |
| `show ntp associations` | Displays NTP peers and association information. |
| `show license summary` | Displays a summary of software licensing information. |
| `show tech-support` | Collects extensive system and troubleshooting information for diagnostics and technical support. |

## Common Troubleshooting Examples

### 1. StackWise Virtual and Redundancy

Use these commands to inspect StackWise Virtual status and redundancy on supported configurations.

```text
show stackwise-virtual
show stackwise-virtual link
show stackwise-virtual dual-active-detection
show redundancy
show redundancy states
```

### 2. Uplink and Interface Problems

Use these commands to investigate interface status, errors, and trunk configuration.

```text
show interfaces status
show interfaces description
show interfaces counters errors
show interfaces trunk
show interfaces transceiver detail
```

### 3. VLAN and Switching Problems

Use these commands to verify VLAN membership, learned MAC addresses, and Spanning Tree behavior.

```text
show vlan brief
show mac address-table
show spanning-tree
show spanning-tree summary
```

### 4. EtherChannel Problems

Use these commands to review port-channel configuration and member-link status.

```text
show etherchannel summary
show etherchannel detail
show interfaces port-channel
```

### 5. Routing and Connectivity Problems

Use these commands to examine Layer 3 interfaces, routing information, and ARP entries.

```text
show ip interface brief
show ip route
show ip route summary
show arp
show ip protocols
```

### 6. System Health

Use these commands to review logs, resource utilization, and hardware status.

```text
show version
show logging
show processes cpu
show processes memory
show environment
show platform
```

## Notes

- StackWise Virtual commands apply only to supported Catalyst 9500 models and software releases.
- StackWise Virtual links connect the two physical switches participating in a supported virtual-switch configuration.
- Replace `<interface>` with the appropriate interface identifier.
- Replace `<vlan-id>` with the appropriate VLAN number.
- Command availability and output can vary by model, IOS XE release, licensing, and configuration.
- These commands are for monitoring and verification; they do not configure or change the switch.
- Confirm command syntax against Cisco documentation for the target model and software release.

## Skills Demonstrated

- Cisco IOS XE command familiarity
- Core and distribution switching concepts
- StackWise Virtual and redundancy concepts
- Layer 2 switching and VLANs
- Layer 3 routing fundamentals
- Uplink and EtherChannel verification
- Network monitoring and troubleshooting concepts
- Technical documentation
