# Week 04 — Active Threat Prevention (pfSense + Suricata IPS)

## Goal
Transform the lab network from detection-only to active prevention by deploying **pfSense** as an enterprise-grade firewall and configuring **Suricata in IPS mode** to block attacks in real time.

## What I built
- pfSense firewall with segmented **WAN/LAN** interfaces
- Firewall rules blocking known malicious IPs
- Geo-blocking to drop traffic from entire countries (pfBlockerNG)
- Suricata IPS with inline blocking (60,000+ threat signatures)
- Centralized gateway routing through the firewall
- A complete network protection layer for all VMs

## Tools & Technologies
- pfSense Community Edition
- Suricata IPS (Inline Mode)
- pfBlockerNG (Geo-blocking)
- MaxMind GeoLite2 Database
- VirtualBox
- Ubuntu Server / Ubuntu Desktop
- Windows 10

## Prerequisites
- Lab 1 completed: 3 VMs with networking configured
- Lab 2 completed: Watchtower monitoring deployed
- Basic understanding of firewalls and network security
- Resources for pfSense VM: 2GB+ RAM and 20GB storage available

## Lab Architecture
### pfSense VM specs
- RAM: 2GB
- CPU: 2 cores
- Disk: 20GB

### Interfaces
- WAN Interface: NAT (Internet access)
- LAN Interface: Host-only `192.168.56.0/24`
- Suricata IPS: inline mode on LAN interface
- All VMs route through the pfSense gateway

## Learning objectives
- Understand IDS vs IPS (Detection vs Prevention)
- Deploy and configure pfSense from scratch
- Implement geo-blocking with pfBlockerNG
- Configure Suricata in prevention mode
- Create intelligent firewall rules
- Route all VMs through the firewall gateway
- Test and validate IPS blocking

## Evidence to include (for portfolio)
Create an `evidence/` folder and add:
- [ ] Screenshot: pfSense interfaces (WAN/LAN) configured
- [ ] Screenshot: LAN network showing `192.168.56.0/24`
- [ ] Screenshot: firewall rules (malicious IP blocking)
- [ ] Screenshot: pfBlockerNG geo-blocking enabled + MaxMind configured
- [ ] Screenshot: Suricata IPS inline mode enabled on LAN
- [ ] Screenshot/log: Suricata alert showing a blocked event
- [ ] Screenshot: VM routing through pfSense gateway (proof all VMs use the firewall)

## Next step
Lab 4: Windows Hardening with Group Policy, Sysmon deployment, and advanced security logging.
