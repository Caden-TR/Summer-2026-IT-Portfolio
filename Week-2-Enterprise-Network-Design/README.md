# Enterprise Network Design

## Overview

In this project, I designed and built a small enterprise network using Cisco Packet Tracer.

The purpose of this project was to gain practical experience with network segmentation, VLAN configuration, inter-VLAN routing, and network troubleshooting.

The network was designed to support different users and services, including employees, servers, guest devices, and network management resources.

VLANs (Virtual Local Area Networks) were used to improve security, performance, and troubleshooting by separating different categories of network traffic.

This project extends the concepts learned in Week 1 by applying basic LAN principles to a small enterprise network configuration.

## Objectives

- Design an enterprise network topology.
- Understand the importance of network segmentation.
- Configure VLANs on Cisco switches.
- Configure trunk ports for connecting network devices.
- Configure inter-VLAN routing.
- Configure IPv4 addressing for different network segments.
- Test network connectivity.
- Troubleshoot network connectivity issues.
- Create professional technical documentation.

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS Command Line Interface
- Ethernet networking
- VLANs
- Router-on-a-stick
- IPv4 addressing
- Visual Studio Code
- Markdown
- Git and GitHub

## Network Design

This network was designed for a small enterprise environment that required network segmentation for different categories of users and services.

The network uses VLAN segmentation to separate different types of devices and reduce unnecessary traffic, improving security, performance, and troubleshooting.

### VLAN Design

| VLAN ID | Name | Purpose |
|---|---|---|
| 10 | Employees | Staff computers and normal business devices |
| 20 | Servers | Internal servers and business services |
| 30 | Guests | Visitor devices and guest Wi-Fi |
| 99 | Management | Network equipment administration |

### IP Addressing Plan

| VLAN | Network | Purpose |
|---|---|---|
| VLAN 10 | 192.168.10.0/24 | Employee devices |
| VLAN 20 | 192.168.20.0/24 | Servers |
| VLAN 30 | 192.168.30.0/24 | Guest devices |
| VLAN 99 | 192.168.99.0/24 | Network management |

## Implementation

The enterprise network was built in Cisco Packet Tracer using a Cisco switch and router.

The network was configured using VLAN segmentation.

### VLAN Creation and Switch Configuration

Four VLANs were created:

- VLAN 10 - Employees
- VLAN 20 - Servers
- VLAN 30 - Guests
- VLAN 99 - Management

Switch access ports were configured and assigned to the correct VLANs based on their purpose.

A trunk port was also configured using 802.1Q tagging to allow multiple VLANs to communicate between the switch and router through a single physical connection.

### Router Configuration

Router-on-a-stick was used to configure inter-VLAN routing.

This involved creating router subinterfaces that allowed communication between different VLANs while maintaining network segmentation.

The router subinterfaces were configured as follows:

| Interface | IPv4 Address | Purpose |
|---|---|---|
| GigabitEthernet0/1.10 | 192.168.10.1/24 | Employee VLAN |
| GigabitEthernet0/1.20 | 192.168.20.1/24 | Server VLAN |
| GigabitEthernet0/1.30 | 192.168.30.1/24 | Guest VLAN |
| GigabitEthernet0/1.99 | 192.168.99.1/24 | Management VLAN |

## Testing

The completed network was tested using the ping utility to verify connectivity between different network segments.

Testing confirmed:

- Employee devices could communicate with the router gateway.
- Devices could communicate between different VLANs.
- Router subinterfaces were functioning correctly.
- VLAN segmentation was working as intended.

Testing was performed using Cisco Packet Tracer tools and the command line interface.

Successful communication was verified between:

- Employee VLAN
- Server VLAN
- Guest VLAN

## Troubleshooting

A deliberate configuration fault was introduced to simulate a real-world network troubleshooting scenario.

The issue was caused by an incorrect IPv4 address being assigned to the Employee-PC.

The problem was identified by using:

- Ping testing
- The `ipconfig` command

The incorrect IPv4 configuration prevented the Employee-PC from communicating correctly with other network segments.

After investigating the configuration, the incorrect IP address was corrected and connectivity tests were repeated.

The successful ping results confirmed that the issue had been resolved.

This exercise demonstrated the importance of structured troubleshooting by using evidence to identify problems rather than making random changes.

## Security Considerations

Network segmentation can improve the security of a computer network by separating different categories of users and services.

Benefits of VLAN segmentation include:

- Increased isolation between network segments.
- Reduced unnecessary broadcast traffic.
- Improved troubleshooting and network management.
- Reduced potential attack surface.

The use of separate employee, server, guest, and management VLANs provides a foundation for more advanced security concepts such as firewall rules, access control, and secure network infrastructure.

## Reflection

This project improved my understanding of how enterprise networks are designed and configured.

It extended the networking fundamentals learned in Week 1 by introducing practical enterprise concepts including VLANs, trunking, and inter-VLAN routing.

Building the network in Cisco Packet Tracer helped reinforce the connection between networking theory and real-world implementation.

The troubleshooting exercise also improved my ability to diagnose network problems systematically by analysing evidence and verifying solutions.

This project provides a strong foundation for future topics including secure network infrastructure, Linux administration, and cybersecurity concepts covered later in the portfolio.