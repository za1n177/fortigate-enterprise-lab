# Phase 1 – Environment Setup

## Objective
Establish a stable and secure lab environment prior to firewall and network configuration.

This phase focuses on:
- FortiGate VM deployment
- Base system validation
- Management host readiness

---

## FortiGate VM Setup
- Imported FortiGate VM64 into virtualization platform
- Verified console access and administrator login
- Confirmed FortiOS version and system status

Key validation command:
get system status

---

## Ubuntu Server Setup
- Installed Ubuntu Server as LAN and management host
- Verified system access and basic OS readiness
- Confirmed network interface availability

Validation commands:
ip a
lsb_release -a

---

## Secure Management Preparation
- SSH service enabled and running on Ubuntu
- Verified SSH socket is listening
- Prepared system for secure remote access in later phases

Validation command:
systemctl status ssh

---

## Outcome
The lab environment is fully prepared for network and firewall configuration.
All systems are reachable, stable, and ready for Phase 2 networking setup.
