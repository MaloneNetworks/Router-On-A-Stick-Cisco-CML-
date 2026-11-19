# Router-on-a-Stick | Cisco CML

A small enterprise network built in Cisco Modeling Labs.

## Topology

![Cisco CML Router-on-a-Stick topology](01%20-%20Topology/CML-RTR-On-A-Stick.png)

## What this lab covers

- VLANs and access ports
- 802.1Q trunking
- Router-on-a-stick inter-VLAN routing
- DHCP
- Switch management

## Network overview

| VLAN | Department | Network |
|---|---|---|
| 10 | Administration | 192.168.10.0/24 |
| 20 | IT | 192.168.20.0/24 |
| 30 | Operations | 192.168.30.0/24 |
| 99 | Management | 192.168.99.0/24 |

R1 provides the VLAN gateways and DHCP for the three department networks. SW1 and SW2 are managed through VLAN 99.

## Lab status

Core configuration is complete. Endpoint DHCP, inter-VLAN connectivity, and switch management reachability have been tested.

## Repository contents

1. `01 - Topology/` – CML topology image and project files
2. `02 - VLAN Configuration/` – VLAN database and access-port assignments
3. `03 - Trunk Configuration/` – 802.1Q trunk verification
4. `04 - Router Configuration/` – router subinterfaces, DHCP, and routing table
5. `05 - Management Connectivity/` – switch management reachability
6. `06 - Connectivity Testing/` – endpoint connectivity tests
7. `07 - Documentation/` – lab scenario and supporting notes
