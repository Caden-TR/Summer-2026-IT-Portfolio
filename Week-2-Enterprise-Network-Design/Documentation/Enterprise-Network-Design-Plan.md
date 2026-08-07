# Enterprise Network Design Plan

## Scenario

A small business requires a secure and organised network infrastructure. The network must support employees, servers, guest users, and network management devices.

The network will use VLANs to separate different types of traffic and improve security, performance, and troubleshooting.

## VLAN Design

| VLAN ID | Name | Purpose |
|---|---|---|
| 10 | Employees | Staff computers and normal business devices |
| 20 | Servers | Internal servers and business services |
| 30 | Guests | Visitor devices and guest Wi-Fi |
| 99 | Management | Network equipment administration |

## IP Addressing Plan

| VLAN | Network | Purpose |
|---|---|---|
| VLAN 10 | 192.168.10.0/24 | Employee devices |
| VLAN 20 | 192.168.20.0/24 | Servers |
| VLAN 30 | 192.168.30.0/24 | Guest devices |
| VLAN 99 | 192.168.99.0/24 | Network management |