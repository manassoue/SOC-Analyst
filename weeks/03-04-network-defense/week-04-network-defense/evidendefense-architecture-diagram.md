```mermaid
flowchart LR
  Internet((Internet)) --> FW[Firewall (pfSense)]
  FW --> LAN[(Internal Network)]
  LAN --> Endpoints[Endpoints]
  LAN --> IDS[IDS Sensor (Suricata/Zeek)]
  FW --> IPS[IPS Inline (Suricata IPS)]
  IDS --> SOC[SOC / SIEM (later: ELK)]
