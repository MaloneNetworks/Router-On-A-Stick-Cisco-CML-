# Router-on-a-Stick | Cisco CML

A small enterprise LAN built in **Cisco Modeling Labs (CML)** to practice VLAN segmentation, 802.1Q trunking, inter-VLAN routing, DHCP, and switch management.

## Topology

![Cisco CML Router-on-a-Stick topology](01%20-%20Topology/CML-RTR-On-A-Stick.png)

The lab uses one router, two Layer 2 switches, and three Linux-based endpoint nodes.

## Network overview

| VLAN | Department | Network | Default gateway |
|---:|---|---|---|
| 10 | Administration | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Operations | 192.168.30.0/24 | 192.168.30.1 |
| 99 | Management | 192.168.99.0/24 | 192.168.99.1 |

R1 provides the default gateways and DHCP for VLANs 10, 20, and 30. VLAN 99 uses static addressing for switch management.

### Device connections

- R1 Ethernet0/0 ↔ SW1 Ethernet0/0
- SW1 Ethernet0/1 ↔ SW2 Ethernet0/0
- SW1 Ethernet0/2 ↔ PC-ADMIN
- SW2 Ethernet0/1 ↔ PC-IT
- SW2 Ethernet0/2 ↔ PC-OPS

### Management addressing

| Device | Management address |
|---|---|
| SW1 | 192.168.99.11/24 |
| SW2 | 192.168.99.12/24 |
| Management gateway | 192.168.99.1 |

## What this lab demonstrates

- Creating and assigning VLANs
- Configuring 802.1Q trunk links
- Configuring router-on-a-stick subinterfaces
- Providing DHCP for department networks
- Configuring switch management SVIs
- Testing endpoint addressing and inter-VLAN connectivity

## Lab walkthrough

Follow the folders in order:

1. [Topology](01%20-%20Topology/) – network layout
2. [VLAN Configuration](02%20-%20VLAN%20Configuration/README.md) – VLANs and access-port assignments
3. [Trunk Configuration](03%20-%20Trunk%20Configuration/README.md) – trunk links and allowed VLANs
4. [Router Configuration](04%20-%20Router%20Configuration/README.md) – router subinterfaces, DHCP, and routing
5. [Management Connectivity](05%20-%20Management%20Connectivity/README.md) – switch management addressing and ping tests
6. [Connectivity Testing](06%20-%20Connectivity%20Testing/README.md) – endpoint connectivity evidence
7. [Device Configurations](07%20-%20Device%20Configurations/README.md) – sanitized R1, SW1, and SW2 configurations
8. [CML Project](08%20-%20CML%20Project/README.md) – downloadable/importable CML project YAML
9. [Documentation](09%20-%20Documentation/README.md) – scenario and supporting notes

## Verification

The repository includes screenshots documenting VLAN membership, trunk configuration, router configuration, switch management reachability, and endpoint connectivity.

## Rebuild the lab

1. Import the [CML project YAML](08%20-%20CML%20Project/RouterOnAStick_Baseline.yaml) into Cisco Modeling Labs.
2. Start the nodes and allow the devices to finish booting.
3. Use the [device configurations](07%20-%20Device%20Configurations/README.md) as reference when configuring or reviewing the devices.
4. Follow the walkthrough above to review each configuration and its verification evidence.

*The configuration files are sanitized reference copies. Review interface names, addressing, and credentials before reusing them in another environment.*
