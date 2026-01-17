# FortiGate Enterprise Networking Lab (FortiGate VM64)

## Overview
This lab demonstrates enterprise-style FortiGate firewall deployment using FortiGate VM64 with Ubuntu Server acting as a LAN host and management jump box.

Key objectives:
- WAN/LAN interface configuration
- Static routing and default gateway design
- Firewall policy with NAT
- Secure SSH management access
- Real-world troubleshooting (routing & DNS conflicts)

---

## Architecture
![Network Diagram](architecture/network-diagram.png)

---

## Phase 1 – Environment Setup
- Imported FortiGate VM64 into VirtualBox
- Deployed Ubuntu Server with hardened SSH
- Verified base connectivity and DNS

📁 Screenshots: `phase-1-setup/`

---

## Phase 2 – Networking & Firewall
- Configured WAN (DHCP) and LAN (static)
- Implemented default route
- Created LAN-to-WAN firewall policy with NAT
- Configured Ubuntu netplan with dual NIC routing
- Validated end-to-end connectivity

📁 Screenshots: `phase-2-networking/`

---

## Phase 3 – Management Access
- Enabled SSH on FortiGate
- Accessed FortiGate from Ubuntu (LAN)
- Accessed FortiGate from Windows host via port forwarding

📁 Screenshots: `phase-3-management-access/`

---

## Troubleshooting Highlights
- Resolved DNS failures caused by multiple default routes
- Fixed routing precedence using netplan overrides
- Validated traffic flow using ICMP, curl, and nslookup

📁 Details: `troubleshooting/common-issues.md`

---

## Skills Demonstrated
- FortiGate firewall administration
- Network routing and NAT
- Linux networking (netplan, routing tables)
- Secure remote management (SSH)
- Enterprise-style troubleshooting
