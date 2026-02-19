# Week 03 — Network Security Monitoring (TShark + Zeek + Suricata)

## Objective
Gain network visibility like a SOC: capture traffic, extract high-value telemetry, and detect suspicious activity using Zeek logs and Suricata IDS alerts.

## Lab environment
- Platform: VirtualBox
- Monitoring VM: Ubuntu Server 22.04
- Endpoints: Windows 10 + Ubuntu Desktop (from Week 01)
- Tools: TShark, Zeek, Suricata

## What I implemented

### 1) Visibility setup (promiscuous mode concept)
- Enabled traffic visibility for monitoring (SPAN/TAP concept in enterprise)
- Goal: observe traffic that normally passes between endpoints

### 2) Packet capture (TShark)
- Captured traffic and generated PCAP for analysis
- Extracted useful fields for quick triage (src/dst IP, ports, protocols)

### 3) Network telemetry (Zeek)
- Deployed Zeek to convert raw packets into structured logs:
  - `conn.log` (connections)
  - `dns.log` (DNS queries)
  - `http.log` (HTTP activity)
- Used Zeek logs to investigate behavior (baseline vs suspicious)

### 4) Detection (Suricata IDS)
- Installed and updated Suricata rules
- Validated alerting on suspicious patterns
- Created at least 1 custom rule (stored in `rules/`) and verified it triggers

### 5) Testing & workflow
- Generated controlled “suspicious” traffic in the lab (e.g., scanning behavior)
- Followed a SOC-style workflow:
  - Observe (PCAP)
  - Summarize (Zeek logs)
  - Detect (Suricata alert)
  - Document (evidence + notes)

## Evidence (stored in `evidence/`)
- [ ] Screenshot: Tshark capture command + output snippet
- [ ] Screenshot: Zeek logs generated (`conn.log`, `dns.log`, `http.log`)
- [ ] Screenshot: Suricata alert output (EVE JSON / fast.log)
- [ ] Screenshot: “test traffic” that triggered detection
- [ ] (Optional) short PCAP sample or filtered export

## Artifacts
- `commands.md`: key commands used (sanitized)
- `rules/`: custom Suricata rule(s)
- `artifacts/`: small sample logs / filtered pcap if included

## Lessons learned
- Why visibility fails in SOCs (no telemetry, wrong placement, too much noise)
- How Zeek helps investigation by turning packets into searchable evidence
- How Suricata rules translate detections into actionable alerts
- The importance of tuning to reduce false positives

## Next steps
Week 04: enforce network defense controls (pfSense + IPS) and improve alert quality and segmentation strategy.
