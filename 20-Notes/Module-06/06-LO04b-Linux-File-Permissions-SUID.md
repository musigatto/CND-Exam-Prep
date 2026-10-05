---

type: note
module: "06"
lo: "04"
tags: [process, tool, command, policy, concept, mod/06]
topic: "Linux File Permissions, Ownership, SUID/SGID"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux File Permissions and Ownership (§6.4 cont.)

Linux categorizes file authorization into **ownership** and **permission**; protects multi-user data.

## Understanding File Permissions (`ls -l`)
- `ls -l` lists files with permissions: first char = type (`d` directory, `-` file), next 9 chars = 3 sets of 3 (owner/group/others)
- `r` read · `w` write · `x` execute · `-` = no permission
- Ownership: **User** (owner, name after digit) · **Group** (name after owner) · **Others** (all other users)

## Changing File Permissions — `chmod`
- `chmod [permission value] [File Name]`

### Absolute (numeric) mode (Table 6.2)
| Number | Symbol | Meaning |
|---|---|---|
| 0 | — | No permission |
| 1 | --x | Execute |
| 2 | -w- | Write |
| 3 | -wx | Execute and write |
| 4 | r-- | Read |
| 5 | r-x | Read and execute |
| 6 | rw- | Read and write |
| 7 | rwx | Read, write, and execute |

### Common directory settings (Table 6.3)
| Value | Meaning |
|---|---|
| 777 | (rwxrwxrwx) No restrictions — list/create/delete files |
| 755 | (rwxr-xr-x) Owner full; others list but cannot read/delete — share with users |
| 700 | (rwx------) Owner full; private |

### Common file settings (Table 6.4)
| Value | Meaning |
|---|---|
| 777 | (rwxrwxrwx) No restrictions — not desirable |
| 755 | (rwxr-xr-x) Owner rwx; others rx — programs used by all users |
| 700 | (rwx------) Owner-only program (private) |
| 666 | (rw-rw-rw) All can read and write |
| 644 | (rw-r--r--) Owner rw; others read only — very common |
| 600 | (rw-------) Owner rw; private |

### Symbolic mode
- Arguments: `u` user, `g` group, `o` others, `a` all (combos `ug`, `ugo`...)
- Operators: `+` add, `-` remove, `=` assign; permissions `r,w,x`; commas for multiple changes
- Examples: `chmod o+x abc.txt` · `chmod ugo-rwx abc.txt` · `chmod ug+rw,o-x xyz.mp4` · `chmod ug=rx,o+r abc.txt`

## Changing Ownership
- `chown user filename` — change owner
- `chown user:group filename` — change user + group
- `chgrp groupName filename` — change group only

## Check and Verify Permissions for Sensitive Files
Typical numeric permission settings for important system files:
| Path | Perm |
|---|---|
| `/boot/grub/menu.lst` (GRUB menu) | 600 |
| `/etc/cron.allow` / `/etc/cron.deny` | 400 |
| `/etc/crontab` (system-wide jobs) | 644 |
| `/etc/hosts.allow` / `/etc/hosts.deny` (TCP wrappers) | 644 |
| `/etc/logrotate.conf` | 644 |
| `/etc/xinetd.conf` | 644 |
| `/etc/xinetd.d` | 755 |
| `/var/log` · `/etc/rc.d` · `/etc/security` | 755 |
| `/var/log/lastlog` · `/etc/passwd` · `/etc/sysctl.conf` · `/etc/syslog.conf` · `/etc/udev/udev.conf` | 644 |
| `/var/log/messages` (main log) | 644 |
| `/var/log/wtmp` (current logins) | 664 |
| `/etc/pam.d` | 755 |
| `/etc/securetty` (root TTYs) · `/etc/shutdown.allow` · `/etc/vsftpd` · `/etc/vsftpd.ftpusers` | 600 |
| `/etc/shadow` (encrypted passwords/expiration) | 400 |
| `/etc/ssh` · `/etc/sysconfig` | 755 |

## Disable Unwanted SUID/SGID Binaries
- SUID executes with **file owner's privileges**; SGID with **file's group owner privileges**; exploitable to gain root
- List all SUID files: `find / -perm +4000` (see all set-user-id)
- List all SGID files: `find / -perm +2000` (see all set-group-id)
- Both: `find / \( -perm -4000 -o -perm -2000 \) -print`
- Remove setuid bit: `chmod a-s /usr/bin/chfn`

## Remove or Rectify Permissions for World-Writable Files
- World-writable = editable by any user → security risk; regularly monitor (may be symptom of misconfigured app/account)
- Locate world-writable files/dirs (except dirs w/ sticky bit & symlinks): `find /dir -xdev -perm +o=w ! \( -type d -perm +o=t \) ! -type l -print`
- Fix each reported dir: `chmod +t /path/to/dir`
- Disable world write: `chmod o-w file`
- Prevent newly created files from being world writable: `umask 002` (note: `umask 022` typical; text shows 002)
- Find no-owner files: `find / -xdev \( -nouser -o -nogroup \) -print`






