---
type: note
module: "10"
lo: "07"
tags: [process, command, tool, policy, mod/10]
topic: "Data Destruction Tools, Standards, Best Practices"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Destruction Tools (§10.7.2)

## Windows DiskPart wipe (command)
1. Open **command prompt as Administrator** → `diskpart`
2. `list disk` → `select disk 1` → `clean`
3. (offline disk → `online` first) → `create partition primary` → `select partition 1` → `active`
4. `format FS=NTFS label=Data quick` → `assign letter=w` → `exit`

## Tools
| Tool | Notes |
|---|---|
| **DBAN** (Darik's Boot and Nuke) | Free, open-source; wipes HDDs in PCs/laptops/servers; may NOT fully sanitize entire drive; **cannot detect/erase SSDs**; **no audit certificate** for regulatory compliance |
| **Macrorit Data Wiper** | Storage-overwriting; complies with **US government requirements** for deleting sensitive data |
| **Active@ KillDisk** | Industrial Desktop disk sanitation; supports **US DoD 5220.22-M** + international standards |
| **Eraser** | Security tool for Windows, removes sensitive data from hard drives |
| **Disk Wipe** | Free portable Windows app; fills volume with binary data multiple times; freeware EULA |
| **PC Shredder** | Free file/folder shredder, irrecoverable |
| **Remo Drive Wipe** | Windows; overwrites several times w/ selected data patterns + international standards |

## Data destruction standards
| Standard | Details |
|---|---|
| **NIST SP 800-88** | Media sanitization guidelines (2006); **three ways: Clear, Purge, Destroy**; covers HDD, SSD, optical |
| → NIST Clear | Overwrite user-addressable memory via standard R/W commands (incl. factory reset) |
| → NIST Purge | Vendor-specific commands sanitize **SSDs** electronically (voltage up/down) |
| → NIST Destroy | Physical: shred, break, melt, burn |
| **DoD 5220.22-M** | **3-pass overwrite** for hard drives w/ verification each stage: Pass 1 = binary **zeros** · Pass 2 = binary **ones** · Pass 3 = **random bits** (final pass verified) |
| **PCI DSS Req 9.10** | Render **cardholder data (CHD)** unreadable/unrecoverable when no longer needed |
| **HIPAA** | Secure + documented disposal of **PHI** — shredding or securely wiping electronic media |
| **ISO/IEC 27001:2022** | ISMS controls for secure disposal of information assets when no longer needed |

## Best practices
1. **Define/document a policy** for destruction + retention (based on record retention schedule)
2. **Follow a data retention schedule** — destroy data when not in use
3. **Prepare/document a destruction process** — shred all + regularly, shred before recycling, shred via professional service
4. **Monitor destruction** (needs change as org grows)
5. **Follow compliance** (classified equipment destruction laws)
6. **Recycle the e-waste** (prevents reuse/recovery of sensitive info; environment-safe)

## Cards
Q:: Sequence for wiping a disk with Windows DiskPart.
A:: `diskpart` → `list disk` → `select disk 1` → `clean` → `create partition primary` → `select partition 1` → `active` → `format FS=NTFS label=Data quick` → `assign letter=w` → `exit`.
#flashcard
Q:: Why is DBAN unsuitable for full sanitization/audit?
A:: May not fully sanitize the entire drive, cannot detect/erase SSDs, and provides no certificate of data removal for audits/compliance.
#flashcard
Q:: What are the 3 NIST SP 800-88 sanitization methods?
A:: Clear (overwrite user-addressable memory) · Purge (including SSD-specific vendor commands) · Destroy (physical).
#flashcard
Q:: The three passes of DoD 5220.22-M?
A:: Pass 1 binary zeros → Pass 2 binary ones → Pass 3 random bit pattern (final pass verified).
#flashcard
Q:: PCI DSS requirement for disposed card data?
A:: Req 9.10 — render cardholder data (CHD) unreadable and unrecoverable once no longer needed.
#flashcard