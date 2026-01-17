🔐 FortiGate Enterprise Firewall Lab (Virtual)
📌 Overview

This project demonstrates a full FortiGate enterprise firewall deployment in a virtualized lab using FortiGate-VM, Ubuntu Server, and VirtualBox.

The lab focuses on real-world firewall fundamentals, including:

WAN / LAN interface design

Routing and NAT

Linux client integration

Secure management access (SSH)

Troubleshooting connectivity issues

This lab was built and validated step-by-step, with evidence-based screenshots for every phase.

🏗️ Lab Architecture (Logical View)
[ Windows Host ]
        |
        |  (VirtualBox NAT / Port Forwarding)
        |
[ Ubuntu Server ]
- enp0s3 : NAT (10.0.2.0/24)
- enp0s8 : LAN (192.168.56.10/24)
        |
        |  (LAN Segment)
        |
[ FortiGate-VM ]
- port1 : WAN (DHCP)
- port2 : LAN (192.168.56.1/24)

⚙️ Environment

Firewall: FortiGate-VM64 (Free / Evaluation Mode)

Client: Ubuntu Server (Netplan)

Host OS: Windows

Hypervisor: Oracle VirtualBox

Management: Console & SSH

🧪 Phase 1 – Initial Setup & System Readiness
🎯 Objectives

Validate FortiGate VM import and system resources

Verify VirtualBox network adapter configuration

Perform first successful console login

Prepare system with updates and basic tools

Confirm internet and DNS functionality

🔧 Key Actions Performed

Verified FortiGate-VM hardware allocation and boot readiness

Reviewed and confirmed VirtualBox network adapters

Successfully logged in via FortiGate console

Updated system and verified firmware stability

Installed essential utilities for administration

Confirmed internet access and DNS resolution

📁 Evidence
phase-1-setup/
├── P1-01-vm-summary.png              # VM hardware & system overview
├── P1-02-network-adapters.png        # VirtualBox adapter configuration
├── P1-03-first-login-success.png     # Successful console login
├── P1-04-system-updated.png          # System update confirmation
├── P1-05-basic-tools-installed.png   # Essential tools ready
├── P1-06-internet-and-dns-working.png# Internet & DNS validation
└── notes.md

📝 Outcome

FortiGate VM is fully operational, reachable via console, correctly networked, and ready for advanced firewall and routing configuration in Phase 2.

🌐 Phase 2 – Networking & Connectivity
Objectives

Configure WAN and LAN interfaces

Enable routing and NAT

Establish internet access for LAN clients

Validate end-to-end connectivity

FortiGate Configuration Summary

Interfaces

port1 (WAN): DHCP (VirtualBox NAT)

port2 (LAN): 192.168.56.1/24

Routing

Default route via WAN gateway

LAN subnet directly connected

Firewall Policy

LAN → WAN

Service: ALL

NAT: Enabled

Ubuntu Server Configuration

enp0s3: DHCP (NAT)

enp0s8: Static IP 192.168.56.10/24

Default route via FortiGate LAN

DNS explicitly configured

Validation Performed

Ping FortiGate LAN interface

Ping public IP (8.8.8.8)

DNS resolution (google.com)

HTTP/HTTPS connectivity tests

📁 Evidence:

phase-2-networking/
├── P2-01-fgt-interfaces.png
├── P2-02-fgt-routing-table.png
├── P2-03-fgt-dns-ping.png
├── P2-04-fgt-firewall-policy-nat.png
├── P2-05-ubuntu-lan-ip-route.png
├── P2-06-ubuntu-connectivity-tests.png
└── notes.md

🔐 Phase 3 – Secure Management Access
Objectives

Enable secure SSH access

Validate access paths

Demonstrate controlled management exposure

Access Validation
Source	Method	Result
Ubuntu Server	SSH → FortiGate LAN IP	✅ Success
Windows Host	Direct SSH → LAN IP	❌ Blocked
Windows Host	SSH via NAT Port Forwarding	✅ Success
Security Design

SSH enabled only on LAN interface

No direct WAN management access

Windows access allowed only via controlled port forwarding

Follows enterprise firewall best practices

📁 Evidence:

phase-3-management-access/
├── P3-01-ssh-from-ubuntu.png
├── P3-02-ssh-from-windows.png
└── notes.md

🔎 Troubleshooting (Inline)

During the lab, several real-world issues were identified and resolved:

Console login not visible (display adapter fix)

License warnings in free mode

Netplan default route conflicts

DNS resolution inconsistencies

SSH access scope validation

All troubleshooting steps and decisions are documented within each phase’s notes.md.

🧠 Skills Demonstrated

FortiGate firewall deployment

Interface, routing & NAT configuration

Linux networking (Netplan)

Secure SSH management

Virtualized enterprise lab design

Practical troubleshooting methodology

👤 Author

Muamad Zaini Bin Rani
Senior IT Executive | Network & Security Enthusiast
Singapore 🇸🇬
