---
type: note
module: "06"
lo: "03"
tags: [process, tool, command, concept, mod/06]
topic: "Linux File Integrity Checking Tools (FIM)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux File Integrity Checking — FIM Tools (§6.3 cont.)

File integrity monitoring (FIM) verifies file permissions and cryptographic checksums against a baseline; part of audit + privilege management.

## FIM Overview
- FIM policies set up in a **centralized repository**; schedule periodic integrity checks of software apps, customer data, OS
- Produces detailed reports for security alerts + vulnerability assessments (verifies **file permission, cryptographic checksums**)
- Organizations assigned to a policy; policy automatically retrieved and compared against a **system baseline**
- Policy violations documented in a report and sent to the central repository; admins informed of the breach
- Policy config stored as **JSON script**: names policy, specifies file systems/files to verify + which file aspects to check; **assigns a risk level** to violations

## Tripwire (File Integrity Monitoring)
- Real-time change intelligence + threat detection; **pairs with Security Configuration Management (SCM)**; regular scans, baseline creation, reporting, alerting; automation detects changes and remediates out-of-policy configs
- Features: reduces **signal-to-noise ratio**; captures **who** changed **what** and **when**; customizable severities/scoring by risk profile/business context
- Steps:
  1. Init DB (files to monitor): `sudo tripwire --init`
  2. Policy file (files/dirs + allowed changes): `sudo vi /etc/tripwire/twpol.txt`
  3. Config file from policy: `sudo twadmin --create-cfgfile -s site.key /etc/tripwire/twcfg.txt`
  4. Generate initial DB per policy + config
  5. Automate check + DB update via cron: `sudo crontab -e` → daily: `0 0 * * * /usr/sbin/tripwire --check`

## AIDE (Advanced Intrusion Detection Environment)
- Open-source intrusion detection tool using **predefined rules** to validate integrity of Linux files/directories; detects unauthorized activity; DB snapshot of the file system compared to live system
- Init: `sudo aide --init` · config: `/etc/aide/aide.conf` · update: `sudo aide --update` · cron: `sudo crontab -e` → `0 0 * * * /usr/sbin/aide --check`
- Manual structural check: `# aide --check`

## Samhain (HIDS)
- Open-source, multi-platform **host-based intrusion detection (HIDS)** with file integrity checking; performs integrity checks, log monitoring/analysis, rootkit detection, port monitoring, rogue SUID executable detection, hidden process detection; **PGP-signed DB + config, stealth mode**
- Install: `sudo apt-get update -y`, `sudo apt-get install samhain`
- Config `/etc/samhain/samhainrc` settings:
  - `FILE_CHECKS` — files/dirs to monitor
  - `HIDE_MODIFIED` — hide modified files from listings
  - `IGNORE_LIST` — files/dirs to ignore
  - `REPORT_LEVEL` — 1 minimal, 3 detailed
  - `SYSLOG_FACILITY` — log location (e.g., `LOG_LOCAL4`)
- Init: `samhain -t init` (`--set-checksum-test=init`) · logs at `/var/log/samhain.log` · check: `samhain --check` · signed-logfile verify: `samhain [-j/--just-list] -L logfile --verify-log=logfile`

## OSSEC (HIDS)
- Monitors integrity of files/directories; rules define monitoring + response actions
- Features: **Log-based IDS (LIDS)**, file integrity monitoring (forensic copy + change detection), **active response** (firewall integration w/ third parties; self-healing), **compliance auditing** (PCI-DSS, CIS Benchmarks), **rootkit/malware detection**, **system inventory** (software, network listeners, hardware)
- OSSEC rules: `/var/ossec/etc/rules/local_rules.xml` (custom, can be appended) and `/var/ossec/etc/rules/decoder.xml`
- Alerts: `sudo tail -f /var/ossec/logs/alerts/alerts.log`

## IMA (Integrity Measurement Architecture) — File Integrity
- Kernel feature; verifies integrity of files & executables using **digital signatures**; detects unauthorized changes
- Enable kernel config: `CONFIG_INTEGRITY=y`, `CONFIG_IMA=y`
- IMA policies in `/etc/ima/ima-policy`; example measure-all policy: `func=H` (measure all files/executables)
- Interacts with **TPM chip** to protect collected hashes from alteration
- Audited files stored `/var/log/audit/audit.log`; view with `grep "ima:" /var/log/messages`
- Two subsystems: **measure** and **appraise**

## inotifywait (Filesystem Monitoring)
- Command-line tool watching files/dirs via Linux inotify kernel subsystem; on change, outputs the **event** + **file/directory** to the console
- Watch a file: `# inotifywait /path/to/file`
- Continuous monitoring: `# inotifywait --monitor /path/to/file`
- Monitor modification events only: `# inotifywait --event modify /path/to/file`

## auditd (Linux Auditing System)
- Kernel auditing; monitor file changes with audit rules; generates detailed logs for review/analysis
- Enable/start: `sudo systemctl enable auditd`, `sudo systemctl start auditd`
- List rules: `sudo auditctl -l`
- Analyze/query: `ausearch` (`sudo ausearch -i -k user-modify`) and `aureport` (`sudo aureport -x`)
- Monitor `/etc/passwd`: `sudo auditctl -w /etc/passwd -p wa -k passwd_changes`
  - `-w` file/dir to monitor · `-p wa` permissions → **w** = write, **a** = attribute change (permissions/ownership) · `-k` unique key identifying rule-related events
  - Template: `auditctl -w path_to_file -p permissions -k key_name`

## Rootkit (rkhunter) as FIM tool
- Scans system files/dirs for changes, reports discrepancies, detects malware/rootkits/backdoors, unauthorized permissions on binaries, suspicious kernel strings
- Run: `sudo rkhunter --check` · config `/etc/rkhunter.conf` (scanning params, add files/dirs) · report default at `/var/log/rkhunter/`
- Schedule via cron: `sudo crontab -e`

## Cards
Q:: FIM working model?
A:: Centralized policy → auto-retrieved → compares local filesystem vs system baseline → violations logged in report + sent to central repo; policy = JSON script with risk levels.
#flashcard
Q:: Tripwire workflow commands?
A:: `tripwire --init` → policy `/etc/tripwire/twpol.txt` → `twadmin --create-cfgfile -s site.key /etc/tripwire/twcfg.txt` → cron `tripwire --check` daily.
#flashcard
Q:: AIDE commands?
A:: Init `sudo aide --init`; config `/etc/aide/aide.conf`; update `sudo aide --update`; check `sudo aide --check` (or `# aide --check`); cron daily.
#flashcard
Q:: Samhain config settings?
A:: FILE_CHECKS (monitor list), HIDE_MODIFIED, IGNORE_LIST, REPORT_LEVEL (1 min / 3 detailed), SYSLOG_FACILITY (e.g., LOG_LOCAL4); init `samhain -t init`; logs `/var/log/samhain.log`.
#flashcard
Q:: OSSEC key features?
A:: LIDS, file integrity monitoring (forensic copies), active response (firewall + self-healing), compliance auditing (PCI-DSS/CIS), rootkit/malware detection, system inventory; alerts via `tail -f /var/ossec/logs/alerts/alerts.log`.
#flashcard
Q:: IMA + TPM?
A:: IMA = measure + appraise subsystems; hashes data before load, sends hashes to TPM to protect from alteration; enable `CONFIG_INTEGRITY=y CONFIG_IMA=y`; policies `/etc/ima/ima-policy` (e.g., `func=H`).
#flashcard
Q:: auditd rule to monitor /etc/passwd?
A:: `sudo auditctl -w /etc/passwd -p wa -k passwd_changes` — -w path, -p permissions (w write, a attribute), -k key. Query with `ausearch -i -k <key>` and `aureport -x`.
#flashcard
Q:: inotifywait usage?
A:: `inotifywait /path` (once), `inotifywait --monitor /path` (continuous), `inotifywait --event modify /path` (modification events).
#flashcard