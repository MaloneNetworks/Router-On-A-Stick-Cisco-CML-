# VLAN Configuration

The following screenshots show the VLANs configured on both switches, including the department access-port assignments.

## SW1

![SW1 VLAN configuration](SW1%20Vlan%20Br.png)

## SW2

![SW2 VLAN configuration](SW2%20Vlan%20Br.png)

## VLAN overview

| VLAN ID | Name | Purpose |
|---:|---|---|
| 10 | ADMIN | Administration |
| 20 | IT | IT department |
| 30 | OPS | Operations |
| 99 | MANAGEMENT | Switch management |

## Access-port assignments

| Switch | Interface | VLAN | Connected endpoint |
|---|---|---:|---|
| SW1 | Ethernet0/2 | 10 | PC-ADMIN |
| SW2 | Ethernet0/1 | 20 | PC-IT |
| SW2 | Ethernet0/2 | 30 | PC-OPS |

The trunk interfaces are verified separately in the trunk configuration section.

## Verification

The VLAN database and access-port membership were checked using:

```cisco
show vlan brief
```
