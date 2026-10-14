# Cisco Catalyst 9300/9500 Show Command Reference

## Overview

This repository provides a structured reference for commonly used show commands on Cisco Catalyst 9300 and 9500 series switches. It covers interface verification, VLANs, Layer 2 switching, Layer 3 routing, redundancy, hardware health, and network troubleshooting.

Each command includes its purpose and key details to check when interpreting its output.

## Command References

### Cisco Catalyst 9300

[**View the Catalyst 9300 Command Reference**](C9300-Show-Commands.md)

Topics include:
- Interface status and connectivity
- VLANs and trunk links
- MAC address tables and spanning tree
- EtherChannel verification
- IP addressing and routing
- Power over Ethernet (PoE)
- Authentication and access lists
- System logs and hardware health

### Cisco Catalyst 9500

[**View the Catalyst 9500 Command Reference**](C9500-Show-Commands.md)

Topics include:
- Core and distribution switching
- Uplink and interface troubleshooting
- Layer 2 and Layer 3 verification
- Routing tables and routing protocols
- EtherChannel and port-channel status
- Redundancy and StackWise Virtual
- Hardware health and system diagnostics

## Troubleshooting Workflows

The guides include example investigation workflows for endpoint connectivity, interface errors, routing issues, and redundancy checks where supported.

## How to Use This Reference

1. Open the reference for the relevant switch platform.
2. Find the command associated with the issue.
3. Review its purpose and troubleshooting checks.
4. Compare the output with the expected network behavior.
5. Continue investigating based on the findings.

Run commands only on devices you are authorized to access.

## Technical Notes

- Command availability and syntax vary by hardware model and Cisco IOS XE version.
- StackWise Virtual commands apply only to supported Catalyst 9500 models and configurations.
- Replace placeholders such as `<interface>` and `<vlan-id>` with appropriate values.
- Configuration and diagnostic output may contain sensitive information. Do not publish confidential device data.

## Scope

This repository focuses on read-only verification and troubleshooting. It is a technical reference, not a complete configuration guide or a substitute for platform-specific Cisco documentation.
