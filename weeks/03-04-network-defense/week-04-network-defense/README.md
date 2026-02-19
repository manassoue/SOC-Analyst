# Week 04 — Network Defense Architecture (Firewall vs IDS vs IPS vs NGFW)

## Objective
Understand why a single security control (firewall) is not enough, and how enterprise SOCs combine **firewall + IDS + IPS** as layered defenses. This week focuses on detection vs prevention and the trade-offs (visibility, encrypted traffic, tuning, false positives).

## Key concepts (enterprise view)

### 1) Why firewalls alone fail
- Firewalls primarily enforce **rule-based filtering** (IP/port/protocol).
- They do not automatically “understand” intent or exploit patterns.
- Encrypted traffic (TLS) limits content inspection unless decryption is in place.

**Defender takeaway:** a firewall reduces attack surface, but does not replace detection and response.

### 2) Stateless vs Stateful firewalls
- Stateless: decisions per packet (simple, fast, less context).
- Stateful: tracks sessions (better context, stronger enforcement).

**Defender takeaway:** stateful rules are essential for realistic enterprise control.

### 3) IDS (Intrusion Detection System)
- IDS detects suspicious patterns and generates alerts.
- Typically deployed out-of-band (monitoring only).

**Strength:** visibility without breaking traffic  
**Limit:** does not block attacks by itself

### 4) IPS (Intrusion Prevention System)
- IPS runs **inline** and can block traffic in real time.
- More powerful, but riskier: false positives can disrupt business traffic.

**Defender takeaway:** IPS requires careful tuning + change control.

### 5) NGFW (Next-Generation Firewall) overview
- Adds application awareness, deep inspection features, and sometimes sandboxing/integration.
- Still benefits from complementary IDS/IPS and SOC monitoring.

### 6) Defense-in-Depth architecture
A practical layered model:
- **Prevent**: firewall policy, segmentation, least privilege connectivity
- **Detect**: IDS alerts + network telemetry (Zeek logs)
- **Block**: IPS (inline) with tuning + exceptions
- **Respond**: SOC triage + playbooks + evidence collection

## Portfolio deliverables
- A simple diagram of “Firewall + IDS + IPS” placement (in `evidence/`)
- A mini runbook: IPS tuning + false positive handling
- Notes: detection vs prevention decision matrix

## Next steps (lab)
Next video/lab will implement **pfSense + Suricata IPS** to block suspicious traffic in real time and document:
- baseline allowed traffic
- blocked events
- tuning decisions and false positive management
