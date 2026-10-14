# Cisco Catalyst 9300/9500 Show Command Reference

## Overview

This repository provides a practical reference for commonly used Cisco Catalyst 9300 and 9500 show commands. It covers interface verification, VLANs, switching, routing, redundancy, system health, and network troubleshooting.

Each command includes its purpose and key items to check when interpreting the output.

## Command References

### Cisco Catalyst 9300

[**Open the Catalyst 9300 Command Reference**](C9300-Show-Commands.md)

Focus areas:
- Interface status and connectivity
- VLANs, trunk links, and MAC address tables
- Spanning tree and EtherChannel
- IP addressing and routing
- Power over Ethernet (PoE)
- Authentication and access lists
- System logs, hardware inventory, and health

### Cisco Catalyst 9500

[**Open the Catalyst 9500 Command Reference**](C9500-Show-Commands.md)

Focus areas:
- Core and distribution switching
- Uplink and interface troubleshooting
- Layer 2 and Layer 3 verification
- Routing tables and routing protocols
- EtherChannel and port-channel status
- Redundancy and StackWise Virtual
- Hardware health, authentication, and system logs

## Troubleshooting Scenarios

The references include example investigation workflows for endpoint connectivity, interface errors, and inter-network connectivity.

## How to Use This Reference

1. Select the appropriate switch reference.
2. Locate the command relevant to the issue.
3. Review the purpose and troubleshooting checks.
4. Compare the results with the expected network behavior.
5. Continue investigating based on the findings.

Only run commands on systems you are authorized to access.

## Technical Notes

- Command availability and syntax can vary by hardware model and Cisco IOS XE software version.
- StackWise Virtual commands apply only to supported Catalyst 9500 models and configurations.
- Replace placeholders such as `<interface>`, `<vlan-id>`, and `<ip-address>` with appropriate values.
- The examples are intended for educational reference and do not contain production configurations or confidential network information.

## Scope

This repository focuses on read-only verification and troubleshooting commands. It is a technical reference, not a complete configuration guide or a substitute for platform-specific documentation.
