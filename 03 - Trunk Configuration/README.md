# Trunk Configuration

The links between R1, SW1, and SW2 carry multiple VLANs using 802.1Q trunking.

## Trunk links

| Device | Interface | Connected device | Allowed VLANs |
|---|---|---|---|
| SW1 | Ethernet0/0 | R1 Ethernet0/0 | 10, 20, 30, 99 |
| SW1 | Ethernet0/1 | SW2 Ethernet0/0 | 10, 20, 30, 99 |
| SW2 | Ethernet0/0 | SW1 Ethernet0/1 | 10, 20, 30, 99 |

## SW1 trunk interfaces

![SW1 trunk interfaces](SW1%20trunk%20int%20.png)

## SW2 trunk interface

![SW2 trunk interfaces](SW2%20trunk%20int%20.png)

## Configuration reference

The sanitized switch configurations are available here:

- [SW1 configuration](../07%20-%20Device%20Configurations/SW1.txt)
- [SW2 configuration](../07%20-%20Device%20Configurations/SW2.txt)

The switch configurations specify VLANs 10, 20, 30, and 99 as allowed on both trunk links.
