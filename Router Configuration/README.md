# Router Configuration

This section documents the router configuration used for inter-VLAN routing and DHCP in the Router-on-a-Stick lab.

## Router subinterfaces

The subinterfaces on R1 provide the default gateway for each VLAN using 802.1Q tagging.

![R1 router subinterfaces](Router%20Subinterfaces.png)

## DHCP configuration

R1 provides DHCP addressing for the department VLANs.

![R1 DHCP pools and bindings](R1%20DHCP%20pools.png)

## Routing table

The routing table is used to verify the networks known to R1.

![R1 routing table](r1%20show%20ip%20route.png)

## Configuration overview

| VLAN | Purpose | Network | Default gateway |
|---:|---|---|---|
| 10 | Administration | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Operations | 192.168.30.0/24 | 192.168.30.1 |
| 99 | Management | 192.168.99.0/24 | 192.168.99.1 |

The department VLANs use DHCP. VLAN 99 uses static management addressing for the switches.
