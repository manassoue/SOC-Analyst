# Week 06 — Linux Server Hardening (CIS + auditd + UFW + fail2ban + SSH keys)

## Objective
Harden a Linux server using CIS Benchmark guidance and production-grade controls: system auditing (auditd), host firewall (UFW), automated brute-force mitigation (fail2ban), and SSH key authentication.

## 1) Infrastructure hardening (servers vs endpoints)
- Infrastructure vs endpoint security
- Why monitoring servers are critical targets
- Enterprise server protection strategies

## 2) CIS Benchmark setup
- Ubuntu Linux benchmark download
- Focus on Level 2 security recommendations
- Alignment between server and desktop hardening

## 3) auditd configuration
- Installed and configured advanced system auditing
- Deployed comprehensive audit rules
- Goal: forensic logging capabilities

## 4) UFW deployment
- Host-based firewall configuration
- Default-deny security posture
- Implemented SSH access rule

## 5) fail2ban setup
- Automated intrusion prevention
- Jail configuration for SSH protection
- Brute-force attack mitigation

## 6) SSH hardening
- Cryptographic key generation
- Disabled password authentication
- Updated SSH daemon security configuration

## Evidence (for portfolio)
Store proof in `evidence/`:
- [ ] CIS Benchmark reference + chosen level (Level 2)
- [ ] auditd installed + proof audit rules deployed
- [ ] UFW enabled + default-deny + SSH allow rule
- [ ] fail2ban enabled + jail config for SSH
- [ ] SSH key authentication working + password auth disabled
- [ ] Snapshot creation (lab preservation)

## Conclusion
- Achieved production-grade Linux hardening controls for infrastructure security
- Preserved the lab state via snapshot for repeatable defensive testing

## Next steps
Continue building defensive security capabilities (next videos/steps in the series).
