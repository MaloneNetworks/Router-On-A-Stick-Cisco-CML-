# Device Configurations

This folder contains sanitized running configurations for the three devices used in the Router-on-a-Stick lab.

## Configuration files

| Device | Description | Configuration |
|---|---|---|
| R1 | Router-on-a-stick subinterfaces, VLAN gateways, and DHCP pools | [R1.txt](R1.txt) |
| SW1 | Trunk links, ADMIN access port, and management SVI | [SW1.txt](SW1.txt) |
| SW2 | Trunk link, IT and OPS access ports, and management SVI | [SW2.txt](SW2.txt) |

## Notes

- These files are reference configurations from the completed lab.
- Password hashes and generated PKI certificate material have been removed.
- Review interface names and IP addressing before reusing these configurations in another topology.
