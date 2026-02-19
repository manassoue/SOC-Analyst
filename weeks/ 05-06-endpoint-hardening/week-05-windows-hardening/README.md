# Week 05 — Windows 10 Endpoint Hardening (CIS + Group Policy + Sysmon)

## Objective
Harden a Windows 10 endpoint using CIS Benchmark standards and enterprise-style policies, then improve visibility with Sysmon and advanced audit logging for SOC operations.

---

## Part A — Hardening fundamentals (why endpoints matter)
This step focuses on why attacks succeed when endpoints are soft targets and what to fix first:
- Attack surface reduction
- CIS Benchmarks as a professional hardening baseline
- Least privilege and limiting lateral movement
- Practical patching strategy to stop mass compromise

---

## Part B — Windows 10 hardening lab (CIS + GPO + Sysmon)

### 1) Endpoint hardening basics
- Attack surface reduction principles
- CIS Benchmark security standards
- Sysmon as advanced logging for investigations

### 2) CIS Benchmarks
- Used Center for Internet Security resources
- CIS Portal registration and Windows 10 Enterprise Benchmark download

### 3) Lab environment
- pfSense dependency for internet access
- Proper VM startup sequence
- Windows 10 baseline configuration

### 4) Password policy configuration (Group Policy)
- Tool: Group Policy Editor (`gpedit.msc`)
- Password complexity requirements enabled
- Minimum length: **14 characters**

### 5) Account lockout policies
- Brute-force prevention
- Lockout threshold: **5 attempts**
- Lockout duration: **15 minutes**

### 6) UAC hardening
- Privilege escalation prevention
- Secure desktop elevation prompts

### 7) Group Policy updates
- Applied changes using `gpupdate /force`
- Verified policies were active

### 8) Services hardening
- Reduced attack surface by reviewing unnecessary services
- Managed via `services.msc`
- Print Spooler noted as a relevant service in hardening context

### 9) Sysmon deployment
- Installed Sysmon (Sysinternals)
- Deployed SwiftOnSecurity configuration
- Goal: detailed forensic logging for SOC triage

### 10) Sysmon event testing
- Verified in Event Viewer (`eventvwr.msc`)
- Reviewed Sysmon Operational logs
- Focus: process creation and network logging visibility

### 11) Advanced audit policies
- Tool: Local Security Policy (`secpol.msc`)
- Enabled credential validation auditing
- Enabled logon/logoff event tracking

### 12) Policy testing (validation)
- Password policy testing: weak password rejection verified
- Account lockout testing:
  - Failed login attempt simulation
  - Detected locked account via **Event ID 4740**
  - Observed 15-minute automatic unlock behavior

---

## Evidence (for portfolio)
Store proof in `evidence/`:
- [ ] Password policy settings (14 chars + complexity)
- [ ] Account lockout settings (5 attempts + 15 min)
- [ ] UAC settings (secure desktop prompts)
- [ ] Services hardening (Print Spooler state)
- [ ] `gpupdate /force` applied + verification
- [ ] Sysmon installed + Sysmon Operational log view
- [ ] Advanced audit policy settings (logon/logoff, credential validation)
- [ ] Event ID **4740** screenshot (locked account)

---

## Next step
Linux hardening (auditd, UFW, fail2ban).
