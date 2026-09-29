---
type: moc
module: "06"
tags: [concept, mod/06]
topic: "Module 06 — Endpoint Security - Linux Systems"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "LO04c: security=apparmor appears as bare boot-line token; exact bootloader parameter line not fully captured."
---
# Module 06 — Endpoint Security - Linux Systems

> [!abstract] Scope
> 6 LOs · 6 sections · courseware pp. 867–988. Endpoint security for **Linux systems**: OS architecture + security concerns, installation and patching, OS hardening (services, software, integrity checking), user access + password management, network + remote access security, and security tools + frameworks (Lynis, AppArmor, SELinux, OpenSCAP).

## Sections
| LO   | §    | Section                                        | Course pp. |
| ---- | ---- | ---------------------------------------------- | ---------- |
| LO01 | 6.1  | Linux OS and Security Concerns                 | 868        |
| LO02 | 6.2  | Linux Installation and Patching                | 874        |
| LO03 | 6.3  | Linux OS Hardening Techniques                  | 884        |
| LO04 | 6.4  | Linux User Access and Password Management      | 917        |
| LO05 | 6.5  | Linux Network and Remote Access Security       | 951        |
| LO06 | 6.6  | Linux Security Tools and Frameworks            | 977        |

## Technical focus
- **Architecture + install:** hardware → kernel → shell → applications/utilities + system libraries, daemons, X Server · Linux timeline 1991–2011 · portability/multiuser/multiprogramming/hierarchical FS · CVEs (CVE-2023-42755, CVE-2023-39198) · Minimal installation (Ubuntu, ~80 pkgs removed) · BIOS + GRUB/LILO passwords (grub-mkpasswd-pbkdf2) · patch mgmt (apt-get/yum/zypper/swaret/autoupdate; SapphireIMS, GFI LanGuard) · `/tmp` with nodev,noexec,nosuid.
- **Hardening:** systemctl service disable + remove legacy servers (telnet, rsh, ypserv, tftp, talk) · Deborphan/unused pkgs · Ubuntu repos (Main/Universe/Restricted/Multiverse) · ClamAV · Secure Boot (UEFI + signed bootloader) · package integrity (GPG: apt/yum/zypper, rpm --checksig, dpkg-sig) · rootkit detection (chkrootkit, rkhunter) · IMA/EVM + TPM · kernel/module integrity (signing, whitelisting, SELinux/AppArmor).
- **FIM tools:** Tripwire · AIDE · Samhain · OSSEC (LIDS, active response, PCI-DSS/CIS compliance) · IMA measure/appraise · inotifywait · auditd (auditctl -w -p wa -k) · rkhunter.
- **Users/passwords:** login.defs aging (PASS_MAX/MIN/WARN_DAYS) · PAM (pam_pwquality: minlen/maxrepeat/ucredit/lcredit/dcredit/ocredit) · pam_tally2 lockout (deny, unlock_time) · remember= (opasswd history) · nullok removal · lastlog -b 90 · usermod -L.
- **Permissions/FS:** chmod numeric+symbolic · sensitive-file permission table (/etc/shadow 400, /etc/passwd 644...) · SUID/SGID find + chmod a-s · world-writable hunts | umask 002 · X11 removal (runlevel 3, yum groupremove) · separate partitions (nodev/noexec/nosuid) · disk quota (quotacheck/edquota/quotaon) · USB block (blacklist, fake install, driver rename, BIOS/GRUB nousb).
- **Network/remote:** sysctl hardening (/etc/sysctl.conf: syncookies, rp_filter, log_martians, exec-shield) · iptables chains/rules · UFW · TCP Wrappers (hosts.allow/deny, ldd grep libwrap, L7 filtering) · port monitor (netstat/ss -tulpn, lsof, nmap -sT/-sU) · IPv6 disable (sysctl or GRUB ipv6.disable=1) · SSH (PermitRootLogin no, hardening keys, LogLevel VERBOSE) · chroot SFTP (internal-sftp, Match group sftponly, ChrootDirectory).
- **Tools/frameworks:** Lynis (audit/hardening/compliance) · AppArmor (aa-enforce, apparmor_status, /etc/apparmor.d) · SELinux (TE + RBAC + MLS; enforcing/permissive/disabled; sestatus) · OpenSCAP/SCAP (CVE/CCE/CPE/CVSS/XCCDF/OVAL/OCIL/AID/ARF/CCSS/TMSAD; libopenscap8, oscap xccdf eval) · Bastille, JShielder, nixarmor, bane, Grsecurity, Comodo AV.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: Ubuntu minimal installation effect (~80 pkgs) · GRUB vs LILO protection · patch commands per distro family · systemctl stop/disable · `yum groupremove "X Window System"` + runlevel 3 · sensitive-file permission table · SUID `find / -perm +4000` · world-writable fix (chmod o-w, chmod +t, umask 002) · USB storage block methods · login.defs triple · PAM complexity params (ucredit/lcredit/dcredit/ocredit) · pam_tally2 · remember=N · quota command sequence · sysctl defaults (ip_forward, rp_filter, syncookies) · iptables attack-blocking rules (XMAS `--tcp-flags ALL ALL`, NULL, fragments) · UFW default policies + delete · TCP Wrappers (hosts.allow/deny + first-match, libwrap check) · netstat/ss -tulpn flags · IPv6 disable paths · SSH hardening keys · chroot SFTP sshd_config block · Lynis + compliance · AppArmor aa-enforce/apparmor_status · SELinux modes + sestatus · OpenSCAP install commands per distro.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-06")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/06-linux-endpoint-map.canvas|Linux Endpoint Map]]
- Flows to visualize: install → patch (minimal install, BIOS/bootloader, patch mgmt) · hardening ladder (services off → software removal → repo hygiene → AV → Secure Boot → package checks → rootkit check → IMA/EVM) · FIM options (Tripwire/AIDE/Samhain/OSSEC/auditd) · user/password stack (login.defs → PAM → lockout → history → nullok → inactive accounts) · filesystem layers (perm table → SUID/SGID → world-writable → X11 → partitions → quota → USB) · network (sysctl → iptables/UFW → TCP Wrappers → port monitor → IPv6 off) · remote (SSH → chroot SFTP) · assurance tools (Lynis → AppArmor → SELinux → OpenSCAP).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-01]] (attack types mitigated by hardening) · [[MOC-Module-02]] (patch/change policy baselines) · [[MOC-Module-03]] (host security, IDS) · [[MOC-Module-05]] (Windows endpoint counterpart) · [[MOC-Module-19]] (security architecture) · [[MOC-Module-20]] (emerging-technology overlap).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- LO04c `security=apparmor` enablement — boot parameter placement not fully captured (OCR line).

## Cards
Q:: Module 06 subject scope?
A:: Linux endpoint security: OS + concerns, install/patching, hardening, user/password management, network + remote access, security tools/frameworks.
#flashcard
Q:: Approach to Linux hardening in one line?
A:: Minimal install + patch → disable services/uninstall software → repository + AV hygiene → integrity (Secure Boot, GPG packages, rootkits, IMA/EVM, FIM) → strong PAM passwords/permissions → kernel + firewall (sysctl/iptables/UFW) → secure remote (SSH/SFTP chroot) → audit (Lynis/AppArmor/SELinux/OpenSCAP).
#flashcard
Q:: Favorite Linux crackable exam items?
A:: Perm tables + SUID commands + PAM params + iptables rule pairs + distro patch commands + chroot SFTP sshd_config + SELinux modes + OpenSCAP install commands.
#flashcard