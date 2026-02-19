# Week 04 — Network Defense (Firewall vs IDS/IPS + pfSense + Suricata IPS Lab)

## Objective
Understand the differences between **firewalls**, **IDS**, and **IPS** (detection vs prevention), then implement an enterprise-style prevention layer using **pfSense** and **Suricata in IPS mode** to block threats in real time.

## Part A — Concepts (Enterprise Network Defense Architecture)

### Why firewalls alone fail
- Firewalls enforce **rule-based filtering**.
- They don’t automatically detect exploit patterns.
- Encrypted traffic limits what can be inspected.

### Stateless vs Stateful firewalls
- Stateless: decision per packet
- Stateful: tracks sessions, stronger enforcement

### IDS (Intrusion Detection System)
- Detects suspicious patterns and generates alerts
- Monitoring/visibility, but **does not block**

### IPS (Intrusion Prevention System)
- Inline blocking in real time
- Powerful but requires tuning (false positives can disrupt traffic)

### Defense-in-depth
Professional SOCs layer controls:
- Prevent (firewall rules, segmentation)
- Detect (IDS/telemetry)
- Block (IPS)
- Respond (triage + playbooks)

## Part B — Lab (pfSense + Suricata IPS Prevention)

### What I built
- pfSense firewall with segmented WAN/LAN interfaces
- Firewall rules blocking known malicious IPs
- Geo-blocking to drop traffic from entire countries (pfBlockerNG)
- Suricata IPS with inline blocking (60,000+ threat signatures)
- Centralized gateway routing through the firewall
- Complete network protection layer for all VMs

### Tools & technologies
- pfSense Community Edition
- Suricata IPS (Inline Mode)
- pfBlockerNG (Geo-blocking)
- MaxMind GeoLite2 Database
- VirtualBox
- Ubuntu Server/Desktop
- Windows 10

### Prerequisites
- Lab 1 completed: 3 VMs with networking configured
- Lab 2 completed: Watchtower monitoring deployed
- Basic understanding of firewalls and network security
- 2GB+ RAM and 20GB storage available for pfSense VM

### Lab architecture
pfSense VM:
- RAM: 2GB
- CPU: 2 cores
- Disk: 20GB

Interfaces:
- WAN: NAT (internet access)
- LAN: Host-only `192.168.56.0/24`
- Suricata IPS: inline mode on LAN interface
- All VMs route through pfSense gateway

### Validation & portfolio evidence
Store proof in `evidence/`:
- [ ] pfSense interfaces (WAN/LAN) configured
- [ ] LAN network showing `192.168.56.0/24`
- [ ] firewall rules (malicious IP blocking)
- [ ] pfBlockerNG geo-blocking enabled + MaxMind configured
- [ ] Suricata IPS inline mode enabled on LAN
- [ ] Suricata alert showing a blocked event
- [ ] proof all VMs route via pfSense gateway

## Next step
Windows Hardening with Group Policy, Sysmon deployment, and advanced security logging.
