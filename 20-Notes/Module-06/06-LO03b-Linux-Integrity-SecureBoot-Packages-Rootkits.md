---

type: note
module: "06"
lo: "03"
tags: [concept, process, tool, command, crypto, mod/06]
topic: "Linux System Integrity Checking — Secure Boot, Package, Rootkits, IMA/EVM"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux System Integrity Checking — Secure Boot, Package Verification, Rootkit Detection (§6.3 cont.)

Verifies authenticity/integrity of bootloader, packages, kernel modules, files.

## Secure Boot
- Ensures integrity/authenticity of the **bootloader and essential system files** during boot; protects against unauthorized/malicious code loaded before the OS kernel
- Requires **UEFI firmware with Secure Boot support**; enable/disable in BIOS/UEFI
- Bootstrap must use a **signed bootloader (e.g., GRUB2)** and **signed kernel** with valid signatures from a **trusted certificate authority (CA)**
- Steps: access bootloader config (BIOS/UEFI) → check config file → **verify file integrity** (checksums/digital signatures) → configure bootloader options from trusted sources and disable unnecessary ones → verify bootloader signature (UEFI Secure Boot) on subsequent partition tables/app images before boot

## Package Integrity Verification
- Package managers validate packages before install/update; always use **official/trusted repositories** (untrusted sources may ship compromised/malicious packages)
- **APT** (Debian/Ubuntu): Advanced Package Tool — install/update list index/upgrade; uses **GPG (GNU Privacy Guard)** keys to verify signatures; ensure GPG keys correctly configured
  - `sudo apt install nmap` · `sudo apt remove nmap` · `sudo apt update` · `sudo apt upgrade`
- **YUM/DNF** (Red Hat/Fedora): YellowDog Updater Modified / Dandified YUM; config files in `/etc/yum.repos.d` specify GPG key URL; ensure keys imported
- **zypper** (SUSE): manages repos; relies on GPG keys; keep keys up to date
- Manual signature checks: `rpm --checksig package.rpm` · `dpkg-sig --verify package.deb`

## Rootkit Detection
- Rootkits intercerpt system calls / replace system binaries to stay undetectable; among the **most dangerous** attacks (hard to find, can persist very long)
- Update rootkit tool DB first: `sudo apt update && sudo apt upgrade`
- **chkrootkit**: command-line; searches **malicious code, trojans, malware** in the machine's binary system and executable binary modifications; default install absent
  - Install: `sudo apt-get install chkrootkit` or clone git repo
  - Run: `./chkrootkit`
- **rkhunter**: detects **backdoors and remote exploits**; performs additional network tests and kernel module checks (useful for forensic analysis)
  - Install (RHEL): `dnf install epel-release` then `dnf install rkhunter`
  - Configure `/etc/rkhunter.conf` (set `MAIL-ON-WARNING`)
  - Test email + generate warnings: `rkhunter --check`
  - Baseline: `rkhunter --propupd`

## Linux Integrity Subsystem
- Security framework to enhance security/integrity; enables monitoring, verifying, protecting critical files/processes/configurations; strong **cryptographic techniques + key management** are fundamental
- Two key components:
  - **Integrity Measurement Architecture (IMA)**: measures, records, evaluates hashes to preserve content; logs for monitoring/verification
  - **Extended Verification Module (EVM)**: extended IMA; monitors changes in file's **extended attributes**; uses **public keys** to verify and sign hashes (digital signatures + cryptographic verification)
- Other aspects: **IMA policies** (which file/part of system is monitored & prioritized), **Secure Boot** (trusted signed components), **Audit and forensic** (monitors activity, generates logs for breach tracing), **Remote attestation** (demonstrate system integrity to remote entities for trust decisions)

## Kernel and Module Integrity Monitoring
- **Kernel integrity monitoring**: continuously monitors kernel + loadable kernel modules for unauthorized changes/tampering (critical for stability/security)
  - Techniques: **checksums and hashing** (compare with known-good values), **File Integrity Monitoring** (alerts via file integrity tools), **Secure Boot**
- **Module integrity monitoring**: only authorized/signed kernel modules load; unsigned rejected
  - Techniques: **module signing** (sign modules, allow only trusted in bootloader), **security policies** (restrict access, improve compliance), **kernel module whitelisting** (maintain/allow list of signed/authorized modules)
  - Commonly part of solutions such as **SELinux (Security-Enhanced Linux)** or **AppArmor**






