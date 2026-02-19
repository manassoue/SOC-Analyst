# Week 01 — Enterprise SOC Lab (VirtualBox + Network Segmentation)

## Objective
Build a reproducible SOC home lab using VirtualBox with 3 VMs and segmented networks to simulate an enterprise-like monitoring environment.

## What I built
### Virtual Machines
- **Ubuntu Server 22.04 (Defense Infrastructure)**
  - Role: central monitoring/analysis platform (future: Zeek, Suricata, ELK, Wazuh, MISP)
- **Windows 10 (Monitored Endpoint)**
  - Role: typical corporate workstation to harden + monitor
- **Ubuntu Desktop 22.04 (Monitored Endpoint)**
  - Role: Linux workstation + testing/analysis endpoint

## Network architecture (segmented)
I used multiple VirtualBox networks to separate management, monitored traffic, and internet access.

- **Management network:** `192.168.56.0/24` (Host-Only)
- **Monitored network:** `10.0.0.0/24` (Internal Network)
- **Internet access:** NAT

> Goal: keep lab management isolated while generating realistic monitored traffic and maintaining controlled internet access for updates.

## VM specifications (my setup)
> (Adjust to your host resources; course suggests min 8GB host RAM, better at 16GB+)
- Ubuntu Server: ___ GB RAM / ___ CPU / ___ GB disk
- Windows 10: ___ GB RAM / ___ CPU / ___ GB disk
- Ubuntu Desktop: ___ GB RAM / ___ CPU / ___ GB disk

## Build steps (high-level)
- Installed VirtualBox
- Downloaded ISOs: Ubuntu Server 22.04, Ubuntu Desktop 22.04, Windows 10
- Created the 3 VMs with defined CPU/RAM/disk allocations
- Configured network adapters (NAT + Host-Only + Internal)
- Installed OSes and validated connectivity between networks

## Validation & evidence
Evidence is stored in `evidence/`:
- [ ] Screenshot: VirtualBox VM list + VM specs
- [ ] Screenshot: Network adapter settings for each VM
- [ ] Output: `ip a` / `ipconfig` showing correct IP ranges
- [ ] Connectivity tests:
  - [ ] Ping between endpoints on monitored network (10.0.0.0/24)
  - [ ] Management reachability on 192.168.56.0/24
  - [ ] Controlled internet access via NAT (updates)

## Lessons learned
- How segmentation reduces risk and makes monitoring more realistic
- How to design a lab that scales into SIEM/EDR later without rebuilding everything

## Next steps
Week 02: Blue Team foundations (SOC workflow, CIA triad, kill chain) + prepare runbooks for later triage.
