# FortiGate Enterprise Firewall Lab (VirtualBox)

## Overview
This project demonstrates the deployment and configuration of a FortiGate VM firewall
in a simulated enterprise environment using VirtualBox.

The lab covers WAN/LAN routing, NAT, firewall policies, SSH management access,
and troubleshooting of real-world networking issues.

---

## Lab Architecture

- **FortiGate VM**
  - port1 (WAN): DHCP via NAT
  - port2 (LAN): 192.168.56.1/24

- **Ubuntu Server (Jump Host)**
  - enp0s3 (WAN/NAT): DHCP
  - enp0s8 (LAN): 192.168.56.10/24

- **Windows Host**
  - SSH access via port forwarding

---

## Phase 1 – FortiGate Deployment
- Imported FortiGate VM into VirtualBox
- Console login and password initialization
- Resource tuning for evaluation license compliance

---

## Phase 2 – Network Configuration
- WAN interface configured via DHCP
- LAN interface configured with static IP
- Default route via WAN
- LAN → WAN firewall policy with NAT enabled
- Ubuntu netplan configured for dual-homed routing
- Internet connectivity validated (ICMP, DNS, HTTPS)

---

## Phase 3 – Management Access
- SSH access from Ubuntu jump host
- SSH access from Windows via port forwarding
- Verified secure administrative access paths

---

## Troubleshooting Highlights
- Resolved console display issue by switching to VMSVGA
- Fixed Ubuntu routing conflicts using netplan overrides
- Diagnosed DNS resolution vs ICMP behavior
- Validated FortiGate routing and policy order

---

## Skills Demonstrated
- FortiGate firewall configuration (CLI)
- Network routing & NAT
- Linux networking (netplan, routing, DNS)
- VirtualBox networking (NAT, Host-only, port forwarding)
- Troubleshooting enterprise network issues
- Secure remote administration (SSH)

---

## Future Enhancements
- GUI access hardening
- Local-in policy restrictions
- IPS / Web Filtering
- Logging & monitoring
