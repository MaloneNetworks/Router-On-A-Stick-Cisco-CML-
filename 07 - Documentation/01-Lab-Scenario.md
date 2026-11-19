# Lab Scenario

## Small Enterprise LAN

### Objective

Build a small enterprise network in Cisco Modeling Labs (CML) that separates three departments into individual VLANs while allowing them to communicate through a central router.

### Network requirements

- Create separate VLANs for Administration, IT, and Operations.
- Connect two Layer 2 switches and carry the required VLANs across trunk links.
- Use router-on-a-stick on R1 to provide inter-VLAN routing.
- Configure R1 to provide DHCP for the three department networks.
- Use a separate management VLAN for the switches.
- Verify endpoint addressing and inter-VLAN connectivity.

### Devices

| Device | Role |
|---|---|
| R1 | Default gateways, inter-VLAN routing, and DHCP |
| SW1 | Access switching and connection to R1 and SW2 |
| SW2 | Access switching for IT and Operations endpoints |
| PC-ADMIN | Administration endpoint |
| PC-IT | IT endpoint |
| PC-OPS | Operations endpoint |

### Expected outcome

Each endpoint should receive an address from the correct department subnet, use its VLAN gateway, and communicate with endpoints in the other department VLANs through R1.

The switches should have management addresses in VLAN 99.

### Lab status

The core VLAN, trunk, router-on-a-stick, DHCP, and endpoint connectivity configuration has been completed. This document will be updated as the lab is reviewed and final verification evidence is collected.
