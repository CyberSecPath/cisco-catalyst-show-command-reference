# Cisco Catalyst 9500 Show Command Reference

## Overview

This guide covers common show commands for Cisco Catalyst 9500 switches, with an emphasis on core and distribution switching, Layer 3 routing, high-speed uplinks, redundancy, and system health.

Command availability and output may vary by hardware model, IOS XE version, and enabled features. StackWise Virtual is supported only on applicable models and configurations.

## 1. Redundancy and StackWise Virtual

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show redundancy` | Review redundancy configuration and information. | Available redundancy information and operating mode. |
| `show redundancy states` | Inspect redundancy state details where supported. | Current and standby roles and reported state. |
| `show stackwise-virtual` | Review StackWise Virtual status on supported systems. | Domain and operational information reported by the platform. |
| `show stackwise-virtual link` | Inspect StackWise Virtual link status where supported. | Link state and configured member interfaces. |
| `show stackwise-virtual dual-active-detection` | Review dual-active detection information where supported. | Detection method and operational status. |

StackWise Virtual commands are not applicable to every Catalyst 9500 model. Confirm platform support and software requirements before relying on them.

## 2. System Information and Hardware

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show version` | Identify software, hardware, and uptime. | IOS XE version, model, uptime, and system image. |
| `show inventory` | Review hardware components. | Product IDs, serial numbers, and component inventory. |
| `show running-config` | Review the active configuration. | Relevant interface, routing, and feature settings; protect any sensitive output. |
| `show startup-config` | Review the saved startup configuration. | Whether the saved configuration contains expected settings. |
| `show boot` | Review boot-related settings where supported. | Boot variables and image selection information. |
| `show environment all` | Review environmental information where supported. | Temperature, fans, and power status. |
| `show platform` | Review platform-specific hardware information. | Reported hardware state and component status. |
| `show platform software status control-processor brief` | Review control-processor resource information where supported. | CPU and memory health indicators. |
| `show license summary` | Review license information where supported. | License status and relevant feature entitlements. |

## 3. Interfaces and Uplinks

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show interfaces status` | Quickly review interface status. | Unexpected down or disabled interfaces. |
| `show interfaces description` | Review interface descriptions and state. | Expected descriptions and operational status. |
| `show interfaces` | Inspect detailed interface statistics. | Operational state, speed, traffic, and errors. |
| `show interfaces counters errors` | Investigate interface error counters. | CRC, input, and other abnormal error counts. |
| `show interfaces <interface>` | Inspect a specific interface. | Link state, counters, and relevant operational details. |
| `show interfaces transceiver detail` | Inspect optical diagnostics where supported. | Optical levels, temperature, and transceiver alarms. |

## 4. VLANs and Layer 2 Switching

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show vlan brief` | Review VLANs and port membership. | Expected VLANs and active status. |
| `show interfaces trunk` | Review trunk operation. | Trunk state and allowed/active VLANs. |
| `show interfaces <interface> switchport` | Inspect Layer 2 settings where applicable. | Access/trunk mode and VLAN information. |
| `show mac address-table` | Review learned MAC addresses. | Expected addresses, VLANs, and interfaces. |
| `show spanning-tree` | Review spanning-tree operation. | Root information, port roles, and states. |
| `show spanning-tree summary` | Review spanning-tree summary information. | Mode and reported consistency information. |
| `show spanning-tree vlan <vlan-id>` | Inspect spanning tree for a particular VLAN. | Root bridge, port roles, and blocking/forwarding states where applicable. |
| `show etherchannel summary` | Review EtherChannel status. | Whether expected member links are bundled. |
| `show etherchannel detail` | Inspect EtherChannel details. | Member-port state and bundle information. |
| `show interfaces port-channel` | Review port-channel interfaces. | Operational state and interface statistics. |

## 5. Layer 3 Routing

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show ip interface brief` | Review Layer 3 interface addressing and state. | Expected addresses and operational status. |
| `show ip interface` | Inspect Layer 3 interface details. | IP settings and relevant interface features. |
| `show ip route` | Inspect the IPv4 routing table. | Expected destination routes and next hops. |
| `show ip route connected` | Review directly connected routes where supported. | Networks associated with operational Layer 3 interfaces. |
| `show ip route static` | Review static routes where supported. | Expected configured static routes. |
| `show ip route summary` | Review routing-table summary information where supported. | Route counts and summarized table information. |
| `show ip protocols` | Review routing protocol information where applicable. | Active protocols and relevant routing settings. |
| `show arp` | Review IPv4 neighbor mappings. | Expected IP-to-MAC entries. |

## 6. Neighbor Discovery and Troubleshooting

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show cdp neighbors` | Identify directly connected Cisco devices. | Neighbor identity, local interface, and remote port. |
| `show cdp neighbors detail` | Review detailed CDP neighbor information. | Reported platform and network information. |
| `show lldp neighbors` | Identify LLDP-advertising neighbors. | Neighbor identity and connected interfaces. |
| `show lldp neighbors detail` | Review detailed LLDP neighbor information. | Advertised device and interface details. |
| `show logging` | Review system messages. | Link events, redundancy events, and recurring errors. |
| `show processes cpu` | Review CPU utilization. | High utilization or unusual process activity. |
| `show processes memory` | Review process memory usage. | Unusual resource consumption. |
| `show authentication sessions` | Inspect authentication sessions where supported. | Session status and access information. |
| `show ip access-lists` | Review configured IPv4 access lists and counters. | Relevant entries and match counters. |

## 7. Time Synchronization and Diagnostic Collection

| Command | Purpose / When to Use | What to Check |
|---|---|---|
| `show ntp status` | Review NTP synchronization status where supported. | Whether the device is synchronized. |
| `show ntp associations` | Review NTP peers where supported. | Peer state and synchronization information. |
| `show tech-support` | Collect broad diagnostic information when authorized. | Use when requested by an administrator or support team; output can be extensive and sensitive. |

## Troubleshooting Scenarios

### Scenario 1: An uplink is down or unstable

Start with:

```text
show interfaces status
show interfaces <interface>
show interfaces counters errors
show interfaces trunk
show logging
```

**Investigation:**
1. Confirm the expected interface is operational.
2. Review interface statistics and error counters.
3. Check trunk operation and VLAN forwarding requirements if the link carries VLAN traffic.
4. Review logs for link flaps or related events.
5. Investigate optics, cabling, peer configuration, and the connected device as appropriate.

### Scenario 2: A destination network is unreachable

Start with:

```text
show ip interface brief
show ip route
show ip protocols
show arp
```

**Investigation:**
1. Verify the relevant Layer 3 interfaces are operational.
2. Determine whether the routing table contains a route to the destination.
3. Check the next hop and relevant neighbor information.
4. If routing protocols are in use, inspect their status and expected route advertisements.
5. Continue with authorized end-to-end testing and upstream-device checks.

### Scenario 3: Redundancy or StackWise Virtual requires investigation

On a supported StackWise Virtual deployment, start with:

```text
show stackwise-virtual
show stackwise-virtual link
show stackwise-virtual dual-active-detection
show redundancy
show logging
```

**Investigation:**
1. Confirm the platform supports the feature.
2. Review the reported StackWise Virtual and link status.
3. Inspect dual-active detection information.
4. Review redundancy state and related system logs.
5. Follow the organization's change-control and escalation procedures before making configuration changes.

## Notes

- These references focus on verification and troubleshooting, not configuration changes.
- Command availability and syntax depend on the specific hardware, software version, and enabled features.
- Some commands and outputs are platform-specific; verify support against the relevant Cisco documentation.
- Treat configuration and diagnostic output as potentially sensitive. Do not publish real device configurations, IP addressing plans, credentials, or customer information.
