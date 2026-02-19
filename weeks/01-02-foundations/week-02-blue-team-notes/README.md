# Week 02 — Blue Team Foundations (SOC workflow + defender frameworks)

## Objective
Understand the day-to-day workflow of a SOC analyst and the core defender frameworks used to prevent, detect, investigate, and respond to threats. This week prepares the mindset and methodology that will be applied to the lab in upcoming weeks.

## What I covered
### 1) Blue Team vs Red Team (practical view)
- Red Team: simulate attacks to test controls and exposure.
- Blue Team: continuous operations — monitoring, detection, triage, investigation, response, and improvement.
- Key takeaway: defenders optimize for **visibility + resilience + repeatable processes**.

### 2) What SOC analysts do daily
- Monitor alerts (SIEM/EDR/IDS), validate signals, reduce noise.
- Triage: quickly decide false positive vs suspicious vs incident.
- Investigate with host + network logs (timeline building).
- Escalate and document: clear notes, evidence, and recommended actions.
- Improve detections and hardening (continuous improvement loop).

### 3) CIA Triad + Defense-in-Depth
- Confidentiality / Integrity / Availability as a decision framework.
- Defense-in-depth: multiple layers (prevent, detect, respond, recover).
- Mapping: each control should have an associated detection and an IR action when it fails.

### 4) Cyber Kill Chain (defender perspective)
- Goal: break the chain early (prevent) and detect later stages if prevention fails.
- Defender mindset: “What evidence would exist at each stage?” and “Which telemetry do I need?”

## Deliverables (portfolio artifacts)
- `notes.md`: summary of concepts + definitions used in later weeks
- `runbooks/`: first triage checklist (basic)
- `docs/architecture.md`: how the lab supports visibility and detection goals

## Next steps
Week 03–04: start generating and observing network telemetry (Suricata/Zeek/Wireshark) and enforce network defenses (pfSense).
