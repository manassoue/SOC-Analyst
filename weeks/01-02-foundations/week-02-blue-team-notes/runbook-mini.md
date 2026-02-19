# Mini Runbook — Suspected Scanning / Port Probing

## Signals
- Multiple connection attempts to many ports in short time
- Many destinations or many failures from one source
- IDS alerts (later: Suricata) or unusual Zeek conn patterns

## Quick triage questions
- Is the source internal or external?
- Are the destination ports/services expected to be exposed?
- Is it a known scanner (inventory tool) or unknown?

## Evidence to collect
- Time window (+/- 10 min)
- Source IP, destination IP, list of targeted ports
- Any successful connections vs only failures
- If internal: which host/user owns the source?

## Actions
- If external scan: confirm firewall blocks + consider rate-limit/denylist
- If internal scan: investigate host for tool usage, malware, or misconfig
- Document outcome and tuning ideas for future detections
