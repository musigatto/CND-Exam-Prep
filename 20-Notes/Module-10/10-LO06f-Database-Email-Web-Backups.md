---
type: note
module: "10"
lo: "06"
tags: [process, command, tool, mod/10]
topic: "Database, Email, and Website Backups"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Database & Website Backups (§10.6.6)

## Oracle backups
**Cold (offline) backup**:
```
SQL> SHUTDOWN IMMEDIATE;
SQL> STARTUP MOUNT;
SQL> BACKUP DATABASE;     -- files copied while mounted
SQL> ALTER DATABASE OPEN;
```

**Hot (online) backup** — **RMAN** in **ARCHIVELOG** mode:
```
RMAN> BACKUP DATABASE PLUS ARCHIVELOG;
```
- Requires archive logging; enables restore up to the last archived log (point-in-time)

## Website backups (hosting provider)
- 3 ways to backup: through **hosting service provider** · through **control panel** · **copying data manually using FTP client**
- **A2 Hosting** provides two tools: **backup wizard** and **server rewind** tools
- **cPanel** full backup = **all files, emails, and databases**:
  1. Log into cPanel → Files section → **Backups** icon
  2. Under Full Backup → **Generate/Download a Full Website Backup**
  3. Select **Home Directory** destination (optionally get email notification) → **Generate Backup**
- Partial backups: restore parts of cPanel — Home Directory, **MySQL databases**, email forwarder/filter configuration
- **WordPress**: backup `wp-content` directory + `wp-config.php` (contain themes, plugins, config)

## Email server backups
- Backup mailbox stores (Exchange DB / mail spool) consistently with services stopped or via VSS snaps.

## Cards
Q:: Cold (offline) Oracle backup procedure order.
A:: SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN.
#flashcard
Q:: What is required for a hot backup of Oracle via RMAN?
A:: ARCHIVELOG mode enabled; use `BACKUP DATABASE PLUS ARCHIVELOG`.
#flashcard
Q:: What does a full cPanel backup include besides files?
A:: MySQL databases, email configuration, and related config; plus website files.
#flashcard