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

### VLAN and addressing plan

| VLAN | Department | Network | Gateway |
|---:|---|---|---|
| 10 | Administration | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Operations | 192.168.30.0/24 | 192.168.30.1 |
| 99 | Management | 192.168.99.0/24 | 192.168.99.1 |

SW1 uses 192.168.99.11/24 and SW2 uses 192.168.99.12/24 for management. Both use 192.168.99.1 as their default gateway.

### Expected outcome

Each endpoint should receive an address from the correct department subnet, use its VLAN gateway, and communicate with endpoints in the other department VLANs through R1.

The switches should have management addresses in VLAN 99 and be reachable through the management network.

### Lab status

The lab configuration and verification evidence are organized in this repository. The walkthrough includes VLAN membership, trunk configuration, router subinterfaces and DHCP, switch management reachability, and endpoint connectivity.

See the [root README](../README.md) for the project walkthrough and links to each section.
