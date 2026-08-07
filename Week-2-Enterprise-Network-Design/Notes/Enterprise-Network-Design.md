# Enterprise Network Design

## Overview

Enterprise networks are large-scale communication systems designed to allow organisations to securely connect users, devices, applications, and services across multiple locations.

Unlike simple home networks, enterprise networks require scalability, reliability, security, and structured management.

A well-designed enterprise network separates different types of traffic to improve security, performance, and troubleshooting.

## Network Devices

### Router

A router connects different networks together and forwards data packets between networks based on IP addresses.

Common uses:
- Connecting a business network to the internet
- Routing traffic between different networks
- Providing communication between separate subnets
- Some routers include built-in security features such as firewall functionality
- Assigning local IP addresses using DHCP


### Switch

A switch connects devices within the same local network using Ethernet connections. It uses MAC addresses to forward Ethernet frames to the correct destination.

Common uses:
- Connecting computers, servers, and printers
- Creating local area networks (LANs)
- Supporting VLAN segmentation


### Firewall

A firewall monitors, filters, and controls incoming and outgoing network traffic based on predefined security rules.

Common uses:
- Blocking unauthorised access
- Filtering network traffic
- Protecting internal systems
- Packet filtering


### Access Point

An access point provides wireless access to a network by allowing devices to connect through Wi-Fi.

Common uses:
- Business Wi-Fi networks
- Connecting laptops and mobile devices


### Server

A server provides services, resources, and data to other computers or users across a network.

Examples:
- File storage
- Authentication services
- Applications
- Databases
- Resource sharing

## Network Segmentation

Network segmentation is the process of dividing a larger network into smaller sections. This allows organisations to separate different types of devices, users, and resources.

Businesses use network segmentation to improve security, performance, and management. For example, employee devices, servers, guest users, and network equipment can be placed into separate network segments.

Benefits of network segmentation:

- Improves security by restricting access between different areas of the network.
- Protects sensitive resources by limiting who can access them.
- Reduces unnecessary network traffic.
- Makes troubleshooting easier by isolating problems to specific areas.
- Allows departments or services to have their own network resources.

Without segmentation, all devices would exist on the same network, creating a larger attack surface and making the network more difficult to manage.

## VLANs (Virtual Local Area Networks)

A Virtual Local Area Network (VLAN) is a logical method of separating devices on the same physical network into different virtual networks.

VLANs allow organisations to separate users, devices, and resources while using the same physical switch infrastructure.

For example, a business switch could contain:

- VLAN 10 - Employees
- VLAN 20 - Servers
- VLAN 30 - Guest Users
- VLAN 99 - Network Management

Although these devices may connect to the same physical switch, VLANs separate their network traffic and prevent unnecessary communication between groups.

## Benefits of VLANs

- Improves security by separating users and resources.
- Reduces broadcast traffic by creating smaller broadcast domains.
- Makes networks easier to manage.
- Allows departments to have separate network configurations.
- Improves troubleshooting by isolating network problems.

## VLAN Example

Without VLANs:

All devices are connected to one large network.

Employees, servers, and guests can potentially communicate with each other.

With VLANs:

Employee devices are separated from servers and guest devices, allowing administrators to control communication between different groups.

## IP Address Planning

IP address planning is the process of designing how IP addresses will be assigned across a network.

In an enterprise environment, different departments, services, and devices are usually placed into separate networks. Each network requires its own IP range and subnet.

Good IP address planning improves:
- Network organisation
- Troubleshooting
- Security
- Future expansion

Example:

| Department | Network |
|---|---|
| Employees | 192.168.10.0/24 |
| Servers | 192.168.20.0/24 |
| Guests | 192.168.30.0/24 |
| Management | 192.168.99.0/24 |

Each network has its own address range, allowing traffic to be managed and controlled.

## Subnetting in Enterprise Networks

Subnetting is the process of dividing a larger network into smaller networks.

Organisations use subnetting to:
- Separate departments
- Reduce broadcast traffic
- Improve security
- Use IP addresses efficiently

For example:

Instead of placing all devices in:

192.168.1.0/24

A company could divide devices into separate networks:

Employees:
192.168.10.0/24

Servers:
192.168.20.0/24

Guests:
192.168.30.0/24