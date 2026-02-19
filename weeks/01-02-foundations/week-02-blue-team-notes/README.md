# Week 02 — Network Security Foundations (Scanning, Protocols, Segmentation, Zero Trust)

## Objective
Build a defender’s understanding of how attackers discover targets (automated scanning), why common protocols/ports create risk, and how network controls (segmentation, encryption, Zero Trust) reduce breach impact.

## Topics covered (defender view)

### 1) Automated scanning is constant
- Reality: bots continuously scan public IP ranges for exposed services.
- Defender takeaway: exposure management matters (firewall policy, segmentation, patching, and continuous monitoring).

### 2) Why protocols matter for security
- Most incidents exploit weaknesses in common protocols (misconfigurations, outdated versions, weak authentication).
- Defender takeaway: understand “normal” protocol behavior to spot anomalies in logs/traffic.

### 3) TCP/IP and protocol risk
- Protocols were not always designed with modern threat models in mind.
- Defender takeaway: reduce legacy protocol exposure + monitor what you cannot remove.

### 4) Ports as entry points
- Ports map to services; exposed services = attack surface.
- Defender takeaway: minimize exposed ports, enforce least-privilege connectivity, and alert on scanning patterns.

### 5) Case study: WannaCry (SMB)
- WannaCry highlighted how a vulnerable service (SMB) can enable rapid propagation.
- Defender takeaway: patch management + segmentation + monitoring lateral movement signals.

### 6) Network segmentation
- Segmentation limits blast radius and lateral movement.
- Defender takeaway: separate management, user endpoints, and monitoring infrastructure (aligns with my lab design).

### 7) Encryption basics (TLS/HTTPS, VPN)
- Encryption protects confidentiality and helps prevent MITM when correctly implemented.
- Defender takeaway: verify TLS hygiene and watch for downgrade/inspection blind spots.

### 8) Zero Trust principles
- “Never trust, always verify”: identity + device posture + least privilege + continuous evaluation.
- Defender takeaway: move from perimeter-only thinking to identity-driven controls.

## Portfolio deliverables
- `notes.md`: protocol/port cheat sheet + security implications
- `runbook-mini.md`: quick triage checklist for “possible scanning” events
- (Optional) `evidence/`: segmentation diagram aligned with my lab networks

## Next steps
Week 03–04: apply these concepts hands-on using Suricata/Zeek/Wireshark + firewall enforcement (pfSense).
