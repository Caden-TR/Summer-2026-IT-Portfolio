# Secure Network Infrastructure

## Network Security Fundamentals

### Access Control Lists (ACLs)

An Access Control List (ACL) is a set of rules used to control network traffic by allowing or denying specific traffic based on defined criteria.

ACLs can be used to control communication between different network segments.

For example, guest devices should not normally have unrestricted access to internal business servers. If guests were able to access the server network, they could potentially reach sensitive business information or services.

An ACL can therefore be used to restrict traffic between VLANs while still allowing legitimate communication where required.

Example security policy:

- Employee VLAN → Server VLAN: Allowed
- Guest VLAN → Server VLAN: Denied
- Guest VLAN → Management VLAN: Denied
- Employee VLAN → Management VLAN: Restricted

### Principle of Least Privilege

The principle of least privilege means giving users, devices, and systems only the access they require to perform their intended tasks.

Giving every device access to every part of a network can create security risks because users may gain access to departments, systems, or information that they do not need.

This could expose sensitive information belonging to the business, its employees, or its suppliers.

For example:

- Employees should only access business systems required for their role.
- Guest devices should have limited access to internal resources.
- Network management interfaces should only be accessible to authorised administrators.
- Servers should only accept connections from systems that require their services.

Using least privilege reduces unnecessary access and limits the potential impact of a compromised device or account.

## Network Security Policy

The network will use access controls based on the principle of least privilege.

The security policy is designed to allow legitimate business communication while restricting unnecessary access between network segments.

| Source VLAN | Destination | Access |
|---|---|---|
| Employees | Servers | Allowed |
| Employees | Management | Restricted |
| Employees | Guests | Denied |
| Guests | Employees | Denied |
| Guests | Servers | Denied |
| Guests | Management | Denied |
| Management | Employees | Allowed |
| Management | Servers | Allowed |
| Management | Guests | Allowed |
| Management | Management | Allowed |

The guest network will be isolated from internal business and management networks.

The management VLAN will be used by authorised administrators to manage network devices and access required network resources.

Access controls will be implemented using ACLs to enforce the security policy.