---

type: moc
module: "10"
tags: [concept, mod/10, flashcard/10]
topic: "Module 10 — Data Security"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights not stated in courseware (Exam 312-38: 4 h, 100 questions)."
  - "Oracle TDE procedure statement tokens clipped at 200 dpi OCR (wizard flow); kept to verified wallet + column/tablespace facts."
---
# Module 10 — Data Security

> [!abstract] Scope
> 9 LOs · 9 sections · courseware pp. 1300–1573. Full data-protection lifecycle: importance of data security + three states (at rest/in transit/in use), access controls (Windows/Linux ACLs, Group Policy, account restrictions), data-at-rest encryption (disk/file/removable/database: Windows Device Encryption + BitLocker + TPM, FileVault, dm-crypt/LUKS, Android/iOS, EFS, third-party, SQL TDE + Always Encrypted + Oracle TDE), secure communications (browser↔web TLS certs, IIS CSR/bind, DB↔web Force Encryption/Oracle SSL, S/MIME email), data masking (algorithms, techniques, SQL/Oracle implementations), backup + retention (strategy, media, RAID, SAN/NAS, types, File History/Time Machine, database/website backups, retention policy), data destruction (concepts, techniques, tools, standards, best practices), DLP, data integrity.

## Sections
| LO   | §   | Section                                | Course pp. |
| ---- | --- | -------------------------------------- | ---------- |
| LO01 | 10.1 | Understand Data Security and Its Importance | 1304 |
| LO02 | 10.2 | Implementation of Data Access Controls | 1311 |
| LO03 | 10.3 | Implement Data at Rest Encryption (ODE) | 1325 |
| LO04 | 10.4 | Secure Communication (SSL/TLS, certs, S/MIME) | 1378 |
| LO05 | 10.5 | Implement Data Masking | 1442 |
| LO06 | 10.6 | Discuss Data Backup and Retention | 1466 |
| LO07 | 10.7 | Discuss Data Destruction Concepts | 1532 |
| LO08 | 10.8 | Data Loss Prevention Concepts | 1547 |
| LO09 | 10.9 | Understand Data Integrity Concept | 1557 |

## Technical focus
- **LO01 importance:** critical data (identified via business impact analysis) · data-loss causes→effects (brand, fines, litigation, shareholder value) · data secured = prevent destruction/modification/disclosure + recover + retention/destruction policies · **3 states table** (at rest / in use / in transit) w/ controls (encryption, SSL/TLS, PGP/S-MIME, DLP, access control, memory encryption) · 7 data-security technologies (access control, encryption, masking, resilience/backup, destruction, retention, hardware security).
- **LO02 access controls:** models RBAC / rule-based (RB-RBAC) / MAC / DAC not mutually exclusive; logical via ACLs, Group Policy, account restrictions, passwords/tokens · **Win ACL**: access token vs ACE, 6 ACE types (3 generic: deny/allow in DACL, audit in SACL; 3 object-specific), explicit vs inherited, share vs NTFS perms (file: Full/Modify/R&X/Read/Write; folder adds List), FAT n/a, special perms path · **Linux ACL**: `yum install acl`, `mount -t ext3 -o acl`, fstab acl option, Access vs Default ACL, `setfacl -m/-x/-b`, `setfacl -m d:o:rx /Testdir`, `getfacl` (`user::rw-`, `user:alice:r-`, `group::r-`, `mask::r-`, `other:r--`) · Group Policy least-privilege/lockout · account restrictions (logon hours, expiration; `pam_time` `/etc/security/time.conf` `Login;*;!Martin;MoTuWeThFr0800-2000`) · third-party Folder Guard/Folder Lock/Protected Folder.
- **LO03 at-rest encryption:** 4 categories (disk, file-level, removable media, database) · disk vs file-level pros (simplicity/performance vs per-file/public-key) · **Windows Device Encryption** (TPM+UEFI prereq; msinfo32 "Device Encryption Support"; Settings→Update & Security→Device encryption) · **TPM 2.0** (Windows 11 req; Compatibility check "Compatible TPM not found"; Recovery→Troubleshoot→UEFI Firmware Settings; `tpm.msc`) · **BitLocker** (AES-CBC/XTS 128/256; full volume; Control Panel "Manage BitLocker"; BitLocker To Go USB) · **EFS** (Win 2000+, not Home; `cipher /e`, `cipher /w:dir`; Advanced Attributes "Encrypt content to secure data"; Encryption Warning file vs folder) · third-party file tools (AxCrypt 256-bit AES, idoo, AES Crypt, Cryptomator, Encrypto, Boxcryptor) · **FileVault 2** (startup disk; recovery key) · **dm-crypt** Plain vs LUKS (header/master key, change pwd w/o re-encrypt, multiple keys, brute-force protection; `cryptsetup`) · Android (dm-crypt AES-128-CBC; 4 states Default/PIN/Password/Pattern; pw ≥6 chars + ≥1 number; ≥1 hr charged) · iOS (default full encryption; passcode links keys; custom alphanumeric) · third-party disk tools (VeraCrypt IDRiX/TrueCrypt-based, Symantec Drive Encryption, GiliSoft, SecureDoc WinMagic, DriveCrypt, ShareCrypt, DCPP, Rohos, Cryptainer LE, PocketCrypt, east-tec) · **DB at rest**: SQL Server **TDE** (DB encryption key→certificate→master key; `ALTER DATABASE SET ENCRYPTION ON`), column/cell-level, **Always Encrypted** (client-side; randomized vs deterministic; at rest+in motion, on-site+cloud; admin can't read data), Oracle **TDE** (columns or tablespace; **wallet**; `ENCRYPTION WALLET OPEN`).
- **LO04 secure communication:** browser↔web; 6-step cert handshake; standard vs **EV SSL**; certificate Details fields (Issued To/By, validity, SHA-256 fingerprints, public key) · view in Chrome/Edge/Firefox · **IIS**: Server Certificates → Create Certificate Request (DN: common name = domain www.luxurytreats.com, Organization, OU, City Lehi, State UT, Country US; **Microsoft RSA SChannel CSP**, bit length) → Complete Certificate Request → Bindings https/443 · DB↔web: **SQL Server Force Encryption** (Configuration Manager → Protocols for MSSQLSERVER → Flags → Force Encryption Yes → restart; FQDN cert) · Oracle Advanced Security SSL (CA, wallet, cipher suites) · **email**: Outlook S/MIME (Trust Center → Email Security → encrypt outgoing; Signing cert + hash algorithm; encryption cert + algorithm; "Send these certs with signed messages"; Office 365 → Encrypt → Encrypt with S/MIME; 2019/2016 → Permissions → Do Not Forward) · O365 Message Encryption (IRM; E3) · Gmail S/MIME (Workspace).
- **LO05 masking:** def (obfuscation/anonymization; preserve format, change keys `2424 XXXX XXXX 3421`); protect non-prod data, insider threats, third parties, GDPR compliance · types SDM (at rest) / DDM (in transit, role-based, proxy alters SQL) / on-the-fly (environment-to-environment) · **algorithms** (character scrambling, lookup substitution, nulling out, shuffling, number/date variance, masking out `X`, date aging, pseudonymization, averaging) · **techniques** (nulling/nullify, substitution w/ valid card numbers, shuffling, data shifting, tokenization, **FPE**, hashing) · SQL Server DDM (`default()`, `email()` masks; partial/random) · Oracle **F.A.S.T.** = Find → Access → Secure → Test; EM discovery jobs (15/16-digit CC, 9-digit SSN patterns; Sensitive Column Type CREDITCARDNUMBER; masking definition job like HR_Employee_Mask).
- **LO06 backup/retention:** def + 2 purposes (reinstate system / recover after loss) · loss causes (human error, crimes, natural causes, disaster) · **8-step strategy** (identify data → media → tech → RAID → method → types → solution → recovery drill) · media factors (cost, reliability, speed, availability, usability) + devices (optical ~200GB, portable HDD/USB no limit, tape enterprise) · **RAID** 0/1/3/5/10/50 (striping/mirroring/parity; RAID 50 = stripe-of-mirrors, min 6) · **SAN vs NAS** (block vs file; CIFS/SMB+NFS; NAS tiers high-end/mid ~100TB/desktop ~8TB) · backup types (full/incremental/differential + pros/cons) · locations incl. off-site/cloud · **File History** (external drive; hourly default, 10 min–daily; keep forever; restore files search) · **Time Machine** (hourly 24h/daily 30d/weekly; encrypt backups) · **MS SQL** backup types (full, differential/incremental, transactional/log; SSMS encrypted backup) · **Oracle** cold (`SHUTDOWN IMMEDIATE`→`STARTUP MOUNT`→`BACKUP DATABASE`→`ALTER DATABASE OPEN`; no archive needed closed) vs hot (RMAN + ARCHIVELOG; `BACKUP DATABASE PLUS ARCHIVELOG`) · **website backup** (hosting provider/A2 backup wizard+server rewind; cPanel full backup all files/email/DB → Home Directory; partial = home dir, MySQL, email forwarders/filters; WordPress wp-content + wp-config.php) · **retention policy** (team; compliance HIPAA/SOX/IRS/COPPA/GDPR; data types; policy elements purpose/laws/schedule/litigation/review; best practices = simple, per-type, minimal-start, archive low-access, software).
- **LO07 destruction:** def + purpose (restrict unauthorized disclosure; delete ≠ gone) · policy per device (mobile hard/cold reset; optical/tape physical destroy; HDD/flash overwrite w/ DBAN/Wipe) · **techniques** = Clearing (overwrite/wiping/erasure; vs keyboard attack; not damaged media), Purging (degaussing + Secure Erase; vs laboratory attack), Destroying (disintegration/incineration/pulverize/melt/shred ≤2mm), Disposal (non-confidential only) · **DiskPart wipe** (`diskpart` → `list disk` → `select disk 1` → `clean` → `create partition primary` → `select partition 1` → `active` → `format FS=NTFS label=Data quick` → `assign letter=w` → `exit`) · tools (DBAN free OSS **HDD-only, no SSD, no audit cert**, Macrorit US-gov; KillDisk DoD 5220.22-M; Eraser; Disk Wipe; PC Shredder; Remo DriveWipe) · **standards** (NIST SP 800-88 Clear/Purge/Destroy; **DoD 5220.22-M 3-pass** zero/one/random; PCI DSS **Req 9.10** CHD unreadable; HIPAA PHI; ISO/IEC 27001) · **6 best practices** (policy, retention schedule, destruction process + shred-all/professional, monitor, compliance, e-waste recycle).
- **LO08 DLP:** def (software+processes blocking confidential data leaving org; aka data leak/information loss/extrusion prevention) · **3 types** (Endpoint DLP = data in use: clipboard/email/removable/print; Network DLP = data in transit at perimeter: email/SSL/IM; Storage DLP = data at rest: file servers, SharePoint, DB) · **WIP** (Windows Information Protection; endpoint DLP; Windows Defender ATP + Azure Information Protection; Intune/SCCM) · **MyDLP** (open source; web/email/IM/printers/removable/screenshots; quarantine) · **8 best practices** (objective, sensitive data, vendors, compatibility, roles, minimal-base→reduce false positives, enhance, eliminate false positives) · vendors (Symantec, McAfee ePO, Quantum/Check Point, Trustwave, Digital Guardian, Forcepoint, DriveStrike, Retrospect, **Safend DPS**).
- **LO09 integrity:** def (accuracy, consistency, reliability throughout lifecycle; unaltered creation→consumption/deletion; GDPR) · **7 characteristics** (Complete, Accurate, Safe, Compliance, Consistent, Reliable, Timeliness) · **2 types** = Physical (storage/retrieval; threats = disasters, deterioration, hardware, radiation/temp, power; counter = error-correcting memory, battery-protected write cache, RAID) + Logical (relational) with **4 subtypes** (entity no-dup/no-null, referential authorized changes, domain column-type range, user-defined org rules) · **checking methods** (checksums/hashes MD5/SHA-256/SHA-3, parity checks, CRC, data validation rules range/format/input/constraint, ECC, digital signatures) · **6-item checklist** (validate input, validate data, remove duplicates, regular backups, control access least-privilege, audit trail) · integrity vs quality vs security vs accuracy.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**; blueprint weights not in courseware → `exam_weight: unknown`.
- Strong question sources: 3 data states + matching controls (SSL/TLS + PGP/S-MIME = in transit) · 7 data-security technologies · 6 ACE types + share vs NTFS perms · Linux ACL commands (`setfacl -m`, `d:o:rx`, `getfacl`) + pam_time rule · at-rest 4 categories · device-encryption prereqs (TPM+UEFI) · BitLocker AES-CBC/XTS 128/256 · TPM 2.0 enable route · EFS (`cipher /e /w`; not Home) · LUKS vs plain dm-crypt benefits · Android 4 states + pw rules · SQL TDE hierarchy + `ALTER DATABASE SET ENCRYPTION ON`; Always Encrypted randomized vs deterministic (engine never sees keys) · Oracle TDE wallet · EV vs standard SSL · IIS CSR DN fields + SChannel CSP + bind 443 · SQL Force Encryption location · Outlook S/MIME Trust Center path + certs/algorithms · O365 Message Encryption E3 · masking algorithms vs techniques (FPE, tokenization, substitution, nulling) + SDM/DDM/on-the-fly + Oracle F.A.S.T. · backup 2 purposes + 8-step strategy + media factors · RAID 0/1/3/5/10/50 + RAID 50 min · SAN vs NAS protocols/tiers · full/incremental/differential pros/cons · File History freq (10 min–daily, hourly default) · Time Machine schedule · Oracle cold/hot command sequence · cPanel full backup contents · retention steps + HIPAA/SOX/IRS/COPPA/GDPR · destruction 4 techniques + attack matchup (keyboard vs laboratory) · DiskPart wipe sequence · DBAN limits (no SSD/cert) · NIST 800-88 Clear/Purge/Destroy · DoD 5220.22-M 3-pass · PCI 9.10 CHD · DLP 3 types + WIP/AIP + Safend · integrity characteristics + physical/logical + 4 logical subtypes + checking methods + 6 checklist.
- Answers: Q046 (LO01) · Q047 (LO03) · Q048 (LO05) · Q049 (LO06) · Q050 (LO07) as drafted below.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-10")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/10-data-security-map.canvas|Data Security Map]]
- Flows to visualize: data lifecycle (create→store→use→transit→backup→retain→destroy) → 3 states + controls → access control (ACL/logical) → at-rest encryption per category → secure comm (browser/IIS/DB/email certs) → masking (SDM/DDM/on-the-fly; F.A.S.T.) → backup strategy + RAID/SAN-NAS → retention → destruction (Clear/Purge/Destroy; DoD 5220.22-M 3-pass) → DLP (endpoint/network/storage) → integrity (physical/logical).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-05]] (Windows: BitLocker/EFS, Group Policy, AppLocker) · [[MOC-Module-02]] (compliance: GDPR, PCI, HIPAA, retention) · [[MOC-Module-03]] (network perimeter + DLP integration) · [[MOC-Module-09]] (application security/WAF; secure app comm) · [[MOC-Module-04]] (crypto foundations: AES/TLS/hashing) · [[MOC-Module-06]] (Linux ACL/user mgmt; pam).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- A few vendor-screenshot tables had 200-dpi OCR noise (Oracle TDE wizard, SSL vendor pages); content kept to legible terms, no invented numbers.

## Cards
Matching data state → control (SSL/TLS, PGP/S-MIME, memory encryption)?
?
at rest → encryption/password/tokenization; in transit → SSL/TLS + email encryption PGP/S-MIME + firewall/DLP; in use → authentication + full memory encryption + strong identity + patching.

4 data-at-rest encryption categories?
?
Disk · file-level · removable media · database.

SQL Server TDE key hierarchy + enable statement?
?
Database encryption key (DEK) → certificate → master key; `ALTER DATABASE <db> SET ENCRYPTION ON`.

Always Encrypted randomized vs deterministic?
?
Randomized = less predictable (no equality lookups); deterministic = same ciphertext for same plaintext (enables equality).

Oracle data masking F.A.S.T.?
?
Find (discovery) → Access → Secure (masking definition/job) → Test.

Oracle cold backup sequence?
?
SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN (no archive logs needed when closed).

NIST SP 800-88 sanitization methods vs DoD 5220.22-M passes?
?
NIST = Clear, Purge, Destroy; DoD = 3-pass overwrite (zeros → ones → random, final-pass verified).

3 DLP types by data phase?
?
Endpoint DLP (data in use) · Network DLP (data in transit) · Storage DLP (data at rest).

Data integrity checking methods listed in courseware?
?
Checksums/hashes (MD5, SHA-256, SHA-3) · parity checks · CRC · data validation rules · ECC · digital signatures.
