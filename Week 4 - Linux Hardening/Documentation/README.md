# Week 4 — Linux Security Hardening & Service Reduction

## Objective

The objective of this project was to assess and improve the security posture of a Linux Mint workstation.

The system was reviewed from a security perspective, including:

- Firewall configuration
- User accounts and privileges
- Root account security
- Remote access services
- Running services
- Listening network ports
- Unnecessary network-facing services

The practical work followed a security workflow of:

**Assess → Identify → Justify → Harden → Verify**

---

## 1. Initial Security Assessment

The Linux workstation was assessed before making security changes.

The assessment included:

- Host and operating system identification
- Current user account
- Firewall configuration
- Listening network ports
- Running system services
- Local users and groups
- `sudo` privileges
- Root account status
- SSH availability
- Network-related services

### Firewall Baseline

UFW was already enabled with the following default policy:

- Incoming traffic: **Denied**
- Outgoing traffic: **Allowed**
- Routed traffic: **Disabled**
- Logging: **Enabled**

This provided a strong baseline for host-based network security.

### User and Privilege Assessment

The main user account was a member of the `sudo` group and therefore had administrative privileges.

The `sudo -l` command confirmed that the account could execute commands with root privileges.

The root account itself was locked, reducing the ability to directly authenticate as root.

### SSH Assessment

The SSH service was not installed or active on the workstation.

This reduced the attack surface associated with unnecessary remote administration services.

---

## 2. Service and Network Exposure Assessment

Running services and listening network ports were reviewed to identify services that could increase the system's attack surface.

The initial assessment identified services including:

- Avahi
- Bluetooth
- CUPS
- CUPS Browsed
- NetworkManager
- systemd-resolved
- Other required Linux system services

Listening ports were also reviewed using:

```bash
ss -tuln