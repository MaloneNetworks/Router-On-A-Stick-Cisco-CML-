# Cisco CML – Router-on-a-Stick Lab

A hands-on Cisco Modeling Labs project documenting the design, configuration, verification, and troubleshooting of a small enterprise LAN.

## Lab 01: Small Enterprise LAN

**Status:** Core configuration and endpoint connectivity have been completed. Documentation and evidence capture are next.

### Scenario

Build a small enterprise network with three department VLANs across two Layer 2 switches. R1 provides inter-VLAN routing through router-on-a-stick and DHCP services. VLAN 99 is reserved for switch management.

### Topology connections

| Device A | Interface | Device B | Interface |
|---|---|---|---|
| R1 | Ethernet0/0 | SW1 | Ethernet0/0 |
| SW1 | Ethernet0/1 | SW2 | Ethernet0/0 |
| SW1 | Ethernet0/2 | PC-ADMIN | eth0 |
| SW2 | Ethernet0/1 | PC-IT | eth0 |
| SW2 | Ethernet0/2 | PC-OPS | eth0 |

These are the actual Ethernet interface names used by the CML nodes in this lab.

### VLAN and addressing plan

| VLAN | Name | Network | Gateway | Purpose |
|---:|---|---|---|---|
| 10 | ADMINISTRATION | 192.168.10.0/24 | 192.168.10.1 | Administration clients |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 | IT clients |
| 30 | OPERATIONS | 192.168.30.0/24 | 192.168.30.1 | Operations clients |
| 99 | MANAGEMENT | 192.168.99.0/24 | 192.168.99.1 | Switch management |

### Management addresses

| Device | Interface | Address |
|---|---|---|
| R1 | Ethernet0/0.99 | 192.168.99.1/24 |
| SW1 | VLAN 99 SVI | 192.168.99.11/24 |
| SW2 | VLAN 99 SVI | 192.168.99.12/24 |

Both switches use 192.168.99.1 as their default gateway.

### DHCP allocation strategy

R1 provides DHCP for VLANs 10, 20, and 30. VLAN 99 uses static management addresses.

For each employee subnet:
- `.1` is reserved for the router gateway.
- `.2–.20` are excluded from DHCP for static infrastructure assignments.
- `.21–.254` are available for DHCP clients.
- `.255` is the broadcast address.

Reserving the lower addresses provides room for statically addressed infrastructure such as printers, servers, and network devices while keeping the DHCP pool predictable. The DHCP pools advertise the corresponding VLAN gateway and DNS server `8.8.8.8`.

### Implementation sequence

1. Apply baseline device configuration.
2. Create VLANs 10, 20, 30, and 99 on both switches.
3. Configure 802.1Q trunks between R1 and SW1, and between SW1 and SW2.
4. Assign endpoint-facing access ports to their department VLANs.
5. Configure R1 router-on-a-stick subinterfaces.
6. Configure DHCP exclusions and pools on R1.
7. Configure switch management SVIs in VLAN 99.
8. Obtain DHCP leases on the Linux-based CML endpoints.
9. Verify addressing and inter-VLAN connectivity.

### Endpoint note

The endpoint nodes in this topology are Linux-based CML nodes, not VPCS. DHCP and interface checks therefore use Linux commands such as `udhcpc -i eth0`, `ip addr show eth0`, and `ip route`.

### Verification status

Reported as completed successfully:
- VLANs, trunk links, and access-port assignments were configured and checked.
- R1 router-on-a-stick subinterfaces were verified as up/up.
- DHCP pools and exclusions were configured.
- All three Linux endpoints obtained DHCP addresses.
- Inter-VLAN connectivity tests between endpoints passed.

Switch management SVIs have been configured. Dedicated management reachability checks and final screenshots are still to be captured and documented.

## Repository contents

- `Topology/` – CML topology export and topology diagram.
- `Documentation/` – scenario, addressing, configuration rationale, and verification walkthroughs.
- `Configurations/` – sanitized device configurations.
- `Screenshots/` – evidence captured from the actual CML lab.
- `CML/` – exported CML topology file.

## Learning objectives

- VLAN segmentation and broadcast domains
- Access ports and 802.1Q trunking
- Router-on-a-stick inter-VLAN routing
- DHCP pools and address exclusions
- Switch management SVIs
- Connectivity verification and troubleshooting

> This is a learning lab built in Cisco Modeling Labs. Interface names and supported commands can vary by node image. Never commit real passwords, private keys, or production credentials to this repository.
