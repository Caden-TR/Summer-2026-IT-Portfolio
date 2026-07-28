# Packet Tracer LAN Lab

## Objective

Create a simple LAN and demonstrate communication between two devices using Cisco Packet Tracer.

## Network Design

Devices:

- PC0
- Switch0
- PC1

IP Addressing:

PC0:
- IP Address: 192.168.1.10
- Subnet Mask: 255.255.255.0

PC1:
- IP Address: 192.168.1.11
- Subnet Mask: 255.255.255.0

## Testing

Connectivity was tested using ping.

Result:

- 4 packets sent
- 4 packets received
- 0% packet loss

## Packet Analysis

### ARP

PC0 generated an ARP request to discover PC1's MAC address.

The request was broadcast through the switch until PC1 responded with its MAC address.

### ICMP

After MAC address resolution, PC0 sent an ICMP Echo Request to PC1.

PC1 successfully received the packet, demonstrating successful network communication.

## Skills Demonstrated

- IP addressing
- Subnetting
- Switching
- MAC address learning
- ARP
- ICMP troubleshooting
- Packet analysis