---

type: note
module: "06"
lo: "05"
tags: [concept, tool, command, bestpractice, process, mod/06, flashcard/06]
topic: "SSH Hardening and Chroot SFTP"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Secure SSH Login and Chroot SFTP (§6.5 cont.)

## Secure SSH Login / Disable Root Login
- Default Linux allows remote root login via SSH → brute-force risk
- Before disabling root: create a normal account (`adduser`) + add to sudoers so it behaves like root via `sudo`

### Steps to disable root SSH login
1. Open `/etc/ssh/sshd_config` (`# gedit /etc/ssh/sshd_config`)
2. Find `#PermitRootLogin no` → remove `#` → set `PermitRootLogin no`
3. Restart SSH: `# /etc/init.d/sshd restart` | `# systemctl restart sshd` | `# service sshd restart`
4. Root login now returns "Permission Denied"

### Secure /etc/ssh/sshd_config settings
| Setting | Value |
|---|---|
| `PermitRootLogin` | no |
| `AllowUsers` | [username] |
| `IgnoreRhosts` | yes |
| `HostbasedAuthentication` | no |
| `PermitEmptyPasswords` | no |
| `X11Forwarding` | no |
| `MaxAuthTries` | 5 |
| `Ciphers` | aes128-ctr, aes192-ctr, aes256-ctr |
| `UsePAM` | yes |
| `ClientAliveInterval` | 900 |
| `ClientAliveCountMax` | (keep default) |

### Detailed logging
- Edit `/etc/ssh/sshd_config` → `LogLevel VERBOSE` → detailed login logging (generating authentication failures, combat brute-force)

## Setup Chroot SFTP
- Default: SSH/SFTP/SCP users can browse the entire file system incl. other users' directories → chroot jail limits access to own dir
- Workflow (any modern Linux distro):
  1. Create chroot dir + root ownership:
     - `$ sudo mkdir /sftp`
     - `$ sudo chown root:root /sftp/`
  2. Per-user dirs: `$ sudo mkdir /sftp/ostechnix` (`/sftp/user1`, `/sftp/user2`…)
  3. Create SFTP group: `$ sudo groupadd sftponly`
  4. Add user: `$ sudo useradd -g sftponly -d /sftp/ostechnix -s /sbin/nologin Alex` (home = chrooted dir, shell = `/sbin/nologin`)
  5. Password: `$ sudo passwd Alex`
  6. Restrict rights: `$ sudo chown alex:sftponly /sftp/ostechnix` · `sudo chmod 700 /sftp/ostechnix/`
  7. Configure `/etc/ssh/sshd_config` (`$ sudo vi /etc/ssh/sshd_config`):
     - Comment out `#Subsystem sftp /usr/libexec/openssh/sftp-server` (or `/usr/lib/openssh/sftp-server` on Ubuntu 19.04)
  8. Append at end of file:
     ```
     Subsystem sftp internal-sftp
     Match group sftponly
       ChrootDirectory /sftp/
       X11Forwarding no
       AllowTcpForwarding no
       ForceCommand internal-sftp
     ```
  9. Restart: `$ sudo systemctl restart sshd`
- Verify: `$ sftp alex@192.168.55.1` → `sftp>` prompt; `sftp> pwd` returns `/` (jail working). SSH attempt → "This service allows sftp connections only."

## Cards
Set PermitRootLogin safely?
?
Edit /etc/ssh/sshd_config → `PermitRootLogin no` → restart sshd (systemctl/service/init.d). Create sudo-capable user first.

Hardening keys in sshd_config?
?
PermitRootLogin no, IgnoreRhosts yes, HostbasedAuthentication no, PermitEmptyPasswords no, X11Forwarding no, MaxAuthTries 5, Ciphers aes128/192/256-ctr, ClientAliveInterval 900.

What is chrooted SFTP and why?
?
Locks SFTP users inside their home dir (can't browse others'); steps: mkdir /sftp (root owned), dirs per user, group sftponly, useradd -s /sbin/nologin, chmod 700, sshd_config internal-sftp + Match block.

sshd_config settings for chroot SFTP?
?
Comment out Subsystem sftp (path per distro), then add: `Subsystem sftp internal-sftp`, `Match group sftponly`, `ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, `ForceCommand internal-sftp`.

Verify SFTP jail?
?
`sftp alex@<server>` → `sftp>` and `pwd` = `/`. SSH attempt shows "This service allows sftp connections only." Restart `systemctl restart sshd`.
