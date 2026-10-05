---

type: note
module: "06"
lo: "06"
tags: [concept, tool, command, crypto, mod/06]
topic: "Linux Security Tools and Frameworks"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux Security Tools and Frameworks (§6.6)

## Lynis — Security Auditing and System Hardening
- Open-source (GPL) security tool; extensive health scan of systems; used for **security auditing, compliance testing (PCI, HIPAA, SOX), penetration testing, vulnerability detection, system hardening**
- Modular/opportunistic scanning: only uses/tested components found on system (no other installs) → keeps system clean
- Source: www.cisofy.com
- Scan sections: Users/Groups/Authentication (grpck, unique UID/GID/names, password-file consistency, sudoers, PAM, password aging, umask), Shells, etc.

## AppArmor
- Linux kernel security module; **Mandatory Access Control (MAC)** implemented on **Linux Security Modules (LSM)**; restricts programs' capabilities via **per-program profiles**
- Fine-grained permissions; safeguards OS/apps against internal + external threats; blocks access to vulnerable critical paths
- Profiles: text files in `/etc/apparmor.d/` (rest from `apparmor-profiles` package)
- Enable profiles: `# aa-enforce /usr/bin/ping` (→ enforce mode)
- Check: `# apparmor_status` (loaded profiles / enforce mode / complain mode)
- Install extra profiles: `sudo apt install apparmor-profiles`
- Enable module: `security=apparmor` (if not enabled)

## SELinux (Security-Enhanced Linux)
- Open-source; kernel-level **MAC** implementation for Linux; decides which **process can access which files, directories, ports**; extra layer of security
- Uses **LSM framework** (MAC without kernel source changes)
- Policy implementation:
  - **Type Enforcement (TE)**: assigns every object a type; policies define allowed access between type pairs → fine-grained permissions on files/processes
  - **RBAC (role-based access control)**: roles applied to users to allow/restrict actions (e.g., grant web-app interaction without full root)
  - **MLS (multi-level security)**: users share classified info at different clearance levels (government use)
- **Modes** (in `/etc/selinux/config`, `SELINUX=`):
  - `enforcing` — SELinux security policy enforced (blocks requests; default)
  - `permissive` — prints warnings instead of enforcing (logs violated rules)
  - `disabled` — no SELinux policy loaded
- `SELINUXTYPE=targeted` (targeted processes protected) / `mls` (MLS protection) / `default` (old strict+targeted policies)
- Status: `sestatus` (enabled/disabled, mode, policy version, loaded policy name)
- Ubuntu caution: Ubuntu uses AppArmor → stop/disable first to avoid conflicts: `sudo /etc/init.d/apparmor stop`, `apt-get update && upgrade -yuf`, `apt-get install selinux`
- Install: `apt-get install selinux`; configure `nano /etc/selinux/config`; **misconfiguration before reboot makes the entire OS unbootable**
- Permissive mode permits logging violated rules; logs in `/var/log/audit/audit.log`

## OpenSCAP — Audit for Security Compliance
- **SCAP** (security content automation protocol): NIST standard specification; supports automated **configuration, vulnerability and patch checking, technical control compliance, security measurement**; NIST recommends for security automation/policy compliance
- **OpenSCAP project** (www.open-scap.org): open-source tools implementing SCAP
- SCAP components: **CVE, CCE, CPE, CVSS, XCCDF, OVAL, OCIL v2.0, Asset Identification (AID), Asset Reporting Format (ARF), Common Configuration Scoring System (CCSS), Trust Model for Security Automation Data (TMSAD)** — XML-based, own namespaces
- Functions: lists software flaws/config issues/product names; measures systems for vulnerability existence; ranks measurement results by impact
- Advantages: automatic vulnerability checking · customizes policies · easy implementation · prevents host attacks
- Features: security compliance · vulnerability assessment (classifies + scans) · defines new vulnerabilities
- OpenSCAP tools: **OpenSCAP Base** (CLI: show info, vuln/config scanning, format conversion) · **SCAP Workbench** (GUI: tailor content, local/remote scans, export results) · **SCAPTimony** · **OSCAP Anaconda add-on**

### Install + run (Ubuntu)
1. `sudo apt-get install libopenscap8`
2. Get OVAL file: `wget https://people.canonical.com/~ubuntu-security/oval/com.ubuntu.xenial.cve.oval.xml`
3. Run: `oscap oval eval --results /tmp/results-xenial.xml --report /tmp/report-xenial.html com.ubuntu.xenial.cve.oval.xml`
4. View results: browse `/tmp/report-xenial.html`
- Fedora: `dnf install openscap-scanner` · RHEL6/7, CentOS6/7: `yum install openscap-scanner`
- XCCDF eval example: `oscap xccdf eval -profile xccdf_org.ssgproject.content_profile_rht-ccp --results-arf arf.xml --report report.html /usr/share/xml/scap/ssg/content/ssg-rhel6-ds.xml`

## Additional Linux Hardening Tools
| Tool | Source | Purpose |
|---|---|---|
| **Bastille Linux** | sourceforge.net | Hardens via default mode; interactive policy + report of tightened settings |
| **JShielder** | github.com | Automates installing required packages to harden a Linux server after user interaction |
| **nixarmor** | github.com | Automates system hardening |
| **bane** | github.com | Imposes restrictions; security monitoring, system hardening, application security |
| **Comodo Antivirus** | comodo.com | Antivirus |
| **Grsecurity** | grsecurity.net | Hardened kernel: intelligent access control, memory-corruption exploit prevention, host of hardening (no config needed) |






