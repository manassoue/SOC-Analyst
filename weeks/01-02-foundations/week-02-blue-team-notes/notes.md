# Notes — Network Security Cheat Sheet (Week 02)

## Ports & services (examples)
- 22/SSH: remote admin — risk: brute-force, weak keys/passwords
- 80/HTTP & 443/HTTPS: web — risk: vuln apps, misconfig TLS
- 445/SMB: file sharing — risk: lateral movement, worms (WannaCry-type outbreaks)
- 3389/RDP: remote desktop — risk: brute-force, exposed admin access
- 53/DNS: name resolution — risk: tunneling, suspicious domains

## Defender mindset
- Reduce exposure: close ports, restrict sources, segment networks
- Monitor behavior: scanning patterns, repeated failures, unusual connections
- Patch fast: especially internet-facing services and wormable vulns
- Assume breach: design controls for containment (segmentation) + visibility (logs)

## Segmentation concepts
- Management zone: admin tools only (restricted)
- User zone: endpoints, least privilege
- Server zone: critical services, tight ACLs
- DMZ: public-facing services
- Monitoring zone: sensors/collectors (protect and isolate)

## Zero Trust (quick principles)
- Verify explicitly (identity, device, context)
- Least privilege access (just-enough, just-in-time)
- Assume breach (containment + monitoring)
