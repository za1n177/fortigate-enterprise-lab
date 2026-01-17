# Phase 2 – Network Configuration & Connectivity

## Objective
Configure FortiGate VM with WAN (DHCP) and LAN (static) interfaces, enable NAT, and verify end-to-end connectivity from an internal Ubuntu server.

## Configuration Summary
- WAN (port1): DHCP via VirtualBox NAT (10.0.2.0/24)
- LAN (port2): Static IP 192.168.56.1/24
- Ubuntu LAN IP: 192.168.56.10/24
- Default gateway: FortiGate (192.168.56.1)
- NAT enabled for LAN-to-WAN traffic

## Key Steps
1. Configured FortiGate interfaces (WAN & LAN)
2. Verified routing table and default route
3. Created firewall policy with NAT enabled
4. Configured Ubuntu static LAN IP and routing
5. Validated DNS and internet connectivity

## Validation
- FortiGate can ping 8.8.8.8 and resolve domains
- Ubuntu server can reach LAN gateway, public IPs, and websites
- SSH access tested successfully from Ubuntu and Windows host

## Outcome
Successfully implemented a functional enterprise-style FortiGate lab with controlled LAN access and NAT-based internet connectivity.
