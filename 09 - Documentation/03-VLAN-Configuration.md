# VLAN Configuration

## VLANs created

The following VLANs are present on both switches:

| VLAN ID | Name | Purpose |
|---:|---|---|
| 10 | ADMIN | Administration |
| 20 | IT | IT department |
| 30 | OPS | Operations |
| 99 | MANAGEMENT | Switch management |

## Access-port assignments

The `show vlan brief` output confirmed these access-port assignments:

| Switch | Interface | VLAN | Connected endpoint |
|---|---|---:|---|
| SW1 | Ethernet0/2 | 10 | PC-ADMIN |
| SW2 | Ethernet0/1 | 20 | PC-IT |
| SW2 | Ethernet0/2 | 30 | PC-OPS |

The trunk interfaces do not appear as access ports in the `show vlan brief` output. They are verified separately in the trunk configuration section.

## Notes

- VLANs 10, 20, 30, and 99 are present and active on both switches.
- SW1 Ethernet0/3 appears in the default VLAN 1 in the captured output.
- VLAN 99 has no access ports listed; it is used for the switch management SVIs and is carried over the trunk links.
- The screenshots show the output of `show vlan brief` on SW1 and SW2.

## Verification command

Run this command on each switch to review VLAN membership:

```cisco
show vlan brief
```
