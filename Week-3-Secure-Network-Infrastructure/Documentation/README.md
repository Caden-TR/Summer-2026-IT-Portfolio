# Secure Network Infrastructure

## Overview

In this project I built upon the enterprise network created in Week 2 by introducing basic network security controls using Cisco Packet Tracer.

The main purpose of this project was to understand how network security can be improved by controlling communication between different network segments.

The network uses VLANs to separate employees, servers, guests and management devices. Access Control Lists (ACLs) were then configured on the router to restrict traffic between selected VLANs.

The project also focused on the principle of least privilege, where devices and users should only have the access they require.

## Goals

The main goals of this project were:

- Understand the purpose of network security controls
- Understand the principle of least privilege
- Configure Extended Access Control Lists (ACLs)
- Restrict communication between selected VLANs
- Protect the management network from unnecessary access
- Isolate guest devices from internal network resources
- Test both permitted and denied network traffic
- Verify that security controls were working correctly
- Document the implementation and testing process

## Technologies

- Cisco Packet Tracer
- Cisco IOS command-line interface
- VLANs
- Extended Access Control Lists (ACLs)
- Router-on-a-stick
- IPv4 addressing
- Ethernet
- Visual Studio Code (VS Code)
- Markdown
- Git and GitHub

## Network Security Design

The network was based on the VLAN structure created during Week 2.

The network contains four main VLANs:

| VLAN ID | Name | Network | Purpose |
|---|---|---|---|
| 10 | Employees | 192.168.10.0/24 | Employee devices |
| 20 | Servers | 192.168.20.0/24 | Internal business servers |
| 30 | Guests | 192.168.30.0/24 | Guest devices |
| 99 | Management | 192.168.99.0/24 | Network management |

Network segmentation provides separate broadcast domains and allows security controls to be applied between different groups of devices.

This is particularly important for the guest network because guest devices should not have unrestricted access to internal business systems.

## Access Control Lists

Extended ACLs were used to control traffic between network segments.

### Guest Restrictions

The first ACL was called:

`GUEST-RESTRICTIONS`

This ACL was applied inbound to the Guest VLAN router sub-interface.

The following traffic was denied:

- Guest → Server network
- Guest → Employee network
- Guest → Management network

Other traffic was permitted so that the ACL did not unnecessarily block unrelated communication.

The configuration used the following networks:

- Guest: 192.168.30.0/24
- Servers: 192.168.20.0/24
- Employees: 192.168.10.0/24
- Management: 192.168.99.0/24

### Employee Management Restrictions

A second ACL was created called:

`EMPLOYEE-MGMT-RESTRICTIONS`

This ACL was applied inbound to the Employee VLAN router sub-interface.

The ACL specifically denied Employee devices from accessing the router management address:

`192.168.99.1`

Other traffic was permitted.

This demonstrated how an ACL can restrict access to a sensitive management resource without unnecessarily blocking legitimate business communication.

## Implementation

The network security controls were implemented on the router using Cisco IOS.

The Guest VLAN ACL was applied to:

`GigabitEthernet0/1.30`

The Employee management ACL was applied to:

`GigabitEthernet0/1.10`

The configuration was then checked using Cisco IOS commands to confirm that the ACLs existed and were applied to the correct interfaces.

The configuration was also saved to the router's startup configuration so that the changes would remain after a restart.

## Testing

Testing was performed using the Packet Tracer PC command prompt and router CLI.

### Guest VLAN Testing

The Guest PC was used to test communication with different network segments.

The following traffic was successfully blocked:

- Guest → 192.168.20.10 (Server)
- Guest → 192.168.10.10 (Employee)
- Guest → 192.168.99.1 (Management)

The Guest PC was still able to communicate with its own default gateway:

`192.168.30.1`

This demonstrated that the Guest VLAN remained functional while access to the selected internal networks was restricted.

### Employee VLAN Testing

The Employee PC was tested against both permitted and restricted destinations.

The Employee PC was able to communicate with its default gateway:

`192.168.10.1`

Access to the management address:

`192.168.99.1`

was blocked by the ACL.

The Employee PC was still able to communicate with the Server network:

`192.168.20.10`

This demonstrated that the ACL was restricting the intended management traffic without preventing legitimate business communication.

## ACL Verification

The ACL configurations were checked using:

`show access-lists`

This showed that the ACL rules were present and also displayed match counters after the network traffic tests were performed.

The Employee management ACL recorded matches against the denied management traffic, providing evidence that the rule was actively being enforced.

The router interfaces were also checked using:

`show ip interface`

This confirmed that:

- `GUEST-RESTRICTIONS` was applied inbound to `GigabitEthernet0/1.30`
- `EMPLOYEE-MGMT-RESTRICTIONS` was applied inbound to `GigabitEthernet0/1.10`

## Security Principles

This project demonstrated several important network security principles.

### Network Segmentation

Separating users and services into different VLANs makes it easier to control communication between different parts of the network.

### Principle of Least Privilege

Users and devices should only receive the access they require.

For example, guest devices do not require access to internal business servers or network management interfaces.

### Access Control

ACLs provide a method of controlling traffic between networks based on defined security requirements.

### Management Protection

Network management interfaces should not be freely accessible to ordinary user devices.

Restricting Employee access to the router's management address demonstrated this principle in practice.

## Evidence

Evidence for this project is stored alongside the Packet Tracer project.

The evidence includes:

- Baseline connectivity testing
- IP configuration
- ACL configuration
- Guest VLAN isolation testing
- Guest gateway connectivity
- ACL hit counters
- Employee management ACL configuration
- Employee management ACL application
- Employee management access being blocked
- Employee ACL hit counters
- Employee to Server connectivity
- Final ACL configuration verification

## Reflection

This project helped me understand how network security controls can be applied to an existing network rather than simply designing the network itself.

I gained practical experience configuring Extended ACLs and applying them to router sub-interfaces.

The testing also helped me understand the importance of checking both denied and permitted traffic. A security control should restrict the traffic it is intended to restrict without unnecessarily preventing legitimate communication.

The project also reinforced the principle of least privilege and showed how VLAN segmentation and ACLs can work together to improve network security.

This provides a foundation for more advanced infrastructure security topics, including Linux hardening and further cybersecurity work later in the portfolio.