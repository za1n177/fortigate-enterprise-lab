🔐 FortiGate Enterprise Lab (Virtualized)
📌 Overview

This project demonstrates a full FortiGate enterprise firewall deployment in a virtualized lab environment using FortiGate-VM + Ubuntu Server + VirtualBox.

The lab focuses on real-world firewall fundamentals:

Interface design (WAN / LAN separation)

Routing and NAT

Secure management access (SSH)

Linux client integration

Troubleshooting and validation

The goal is not just to “make it work”, but to implement secure, production-aligned firewall practices.

🏗️ Lab Architecture
High-Level Design
Windows Host
│
├── VirtualBox NAT (Internet)
│       │
│   Ubuntu Server
│   - enp0s3 (NAT / 10.0.2.0/24)
│   - enp0s8 (LAN / 192.168.56.0/24)
│       │
│   FortiGate-VM
│   - port1 (WAN / DHCP)
│   - port2 (LAN / 192.168.56.1)


📷 Diagram: architecture/network-diagram.png

⚙️ Lab Components

Firewall: FortiGate-VM64 (Free / Evaluation Mode)

Client: Ubuntu Server (Netplan-based networking)

Host: Windows 10/11

Hypervisor: Oracle VirtualBox

Access: Console, SSH, NAT Port Forwarding

🧪 Phase Breakdown
🔹 Phase 1 – Initial Setup
Objectives

Import FortiGate OVA

Resolve console display issues

Perform first login and baseline checks

Key Tasks

FortiGate-VM imported into VirtualBox

Display adapter adjusted to VMSVGA to restore console visibility

Initial admin login and password setup

Verified system status and resources

📁 Evidence:

phase-1-setup/
├── P1-01-fgt-import.png
├── P1-02-console-login.png
└── notes.md

🔹 Phase 2 – Networking & Connectivity
Objectives

Configure WAN and LAN interfaces

Establish routing and NAT

Enable end-to-end internet connectivity

Validate Linux client access through firewall

FortiGate Configuration

Interfaces

port1 (WAN): DHCP

port2 (LAN): 192.168.56.1/24

Routing

Default route via WAN gateway

Directly connected LAN route

Firewall Policy

Source: LAN → Destination: WAN

Service: ALL

NAT: Enabled

Ubuntu Server Configuration

enp0s3: DHCP (NAT)

enp0s8: Static LAN IP 192.168.56.10/24

Default route via FortiGate LAN IP

DNS configured explicitly

Validation Tests

Ping FortiGate LAN

Ping public IP (8.8.8.8)

DNS resolution (google.com)

HTTP/HTTPS connectivity

📁 Evidence:

phase-2-networking/
├── P2-01-fgt-interfaces.png
├── P2-02-fgt-routing-table.png
├── P2-03-fgt-dns-ping.png
├── P2-04-fgt-firewall-policy-nat.png
├── P2-05-ubuntu-lan-ip-route.png
├── P2-06-ubuntu-connectivity-tests.png
└── notes.md

🔹 Phase 3 – Secure Management Access
Objectives

Enable secure SSH management

Restrict management plane exposure

Validate access paths from different hosts

Access Scenarios
Source	Method	Result
Ubuntu Server (LAN)	SSH to 192.168.56.1	✅ Allowed
Windows Host (Direct)	SSH to 192.168.56.1	❌ Blocked
Windows Host	SSH via NAT Port Forwarding	✅ Allowed
Security Design Decisions

SSH enabled only on LAN interface

No direct SSH exposure on WAN

Windows access allowed only via controlled port forwarding

Mirrors real enterprise firewall hardening practices

📁 Evidence:

phase-3-management-access/
├── P3-01-ssh-from-ubuntu.png
├── P3-02-ssh-from-windows.png
└── notes.md

🛠️ Troubleshooting

Common issues and resolutions are documented, including:

Console display not showing login

FortiGate license warnings

Netplan routing conflicts

DNS resolution failures

SSH access restrictions

📁 Reference:

troubleshooting/
└── common-issues.md

🔐 Security Highlights

Segmented WAN / LAN architecture

NAT-only outbound internet access

Restricted management plane

No direct WAN administrative exposure

Bastion-style access pattern implemented

📈 Skills Demonstrated

FortiGate firewall deployment

Interface, routing & NAT configuration

Linux networking (Netplan)

SSH hardening & access control

Virtualized enterprise lab design

Real-world troubleshooting methodology

🚀 Next Enhancements (Planned)

Local-in policies hardening

Admin profiles & RBAC

Logging & monitoring (Syslog / SIEM)

IPS / Security Profiles

High Availability (HA) simulation

👤 Author

Muamad Zaini Bin Rani
Senior IT Executive | Network & Security Enthusiast
Singapore 🇸🇬
