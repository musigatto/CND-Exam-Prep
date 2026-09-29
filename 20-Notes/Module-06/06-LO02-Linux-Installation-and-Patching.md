---

type: note
module: "06"
lo: "02"
tags: [concept, process, tool, command, bestpractice, mod/06, flashcard/06]
topic: "Linux Installation and Patching"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux Installation and Patching (§6.2)

Hardening starts at install; patch management keeps kernel + software current.

## Enable Minimal Installation Option
- Ubuntu installer "Minimal installation" checkbox (from **Ubuntu 18.04/Bionic Beaver** onward)
- Minimizes packages installed during OS install; keeps **desktop, web browser, core system tools** only
- Removes ≈ **80 packages** vs default; restricts codecs/third-party software
- **Prevents** downloading third-party/untrusted applications that may be **vulnerable to new exploits**
- Admin installs required apps after OS installation completes (Linux Software Center centralizes)

## Password Protect BIOS and Bootloader
- **BIOS**: firmware for hardware initialization; BIOS password blocks:
  - Changing BIOS settings (attacker booting from diskette/CD via rescue/single-user mode → run processes / copy sensitive info)
  - Booting the system (password forced before boot loader starts)
  - Forgotten BIOS password: reset via motherboard **jumpers** or **disconnecting CMOS battery** → lock the system case
- **Boot loader**: loads the kernel; first software after BIOS; two common Linux boot loaders = **GRUB** and **LILO**
- Boot loader password blocks:
  - **Single-user mode** access (automatic root login without root password)
  - **GRUB console** (edit config / `cat` to extract info)
  - Selecting a **non-secure OS** at boot on dual-boot systems (e.g., DOS ignores access controls)
- Anyone can override the existing OS by booting through **removable devices** → protect the boot loader

### Steps: protect Ubuntu GRUB
1. Generate password hash: `grub-mkpasswd-pbkdf2` (PBKDF2 hash `grub.pbkdf2.sha512...`); optional — plain text works but hashing **obfuscates**
2. Edit `/etc/grub.d/40_custom` (custom settings must be saved here or overwritten by newer GRUB)
3. Add `set superusers="name"` + `password_pbkdf2 name <hash>`; save `Ctrl+O`, exit `Ctrl+X`

### Steps: protect LILO
- Restrict config to root: `chmod 600 /etc/lilo.conf`
- Global section: `password=""` + `restricted`
- Re-run `/sbin/lilo`; creates `/etc/lilo.conf.shs` (password hash, root-only)

## Linux Patch Management
- Process: **scan endpoints** for missing patches → **download** from vendor sites → **deploy** to clients
- Benefits: productive + secure environment; improved system performance

### Manual patch deployment commands
| Distro family | Check updates | Install |
|---|---|---|
| Debian/Ubuntu/Mint | `sudo apt-get update` (fetch list) | `sudo apt-get upgrade` (strictly upgrade current) · `sudo apt-get dist-upgrade` (install new) |
| Red Hat/CentOS/Oracle | `yum check-update` | `yum update` |
| SUSE/OpenSUSE | `zypper check-update` | `zypper update` |
| Slackware | — | `swaret` |
| Other RPM-based | — | `autoupdate` |

### Automated patching (patch management software)
- Performs automatically: scan missing patches · download · **test in non-production** · approve for production if no issues · schedule reports
- Examples: **SapphireIMS, GFI LanGuard**

## Linux Hardening Checklist — System Installation and Patching
- Secure a newly installed system from **hostile network traffic** until installation + hardening finished
- Use the **latest OS version**; consider vendor support lifecycle + service packs
- **Separate volume** for `/tmp` with **`nodev,nosuid,noexec`** options (avoid resource exhaustion): nodev = no block/special char devices; noexec = no binaries from /tmp; nosuid = no setuid files in /tmp
- **Separate volumes** for `/var`, `/var/log`, `/home` (restrict impact of non-admin write fills)
- Set **sticky bit** on all world-writable directories (stop users deleting other users' files)
- Configure **automatic software updates** (simple config change on all distributions)

## Cards
Ubuntu minimal installation effect?
?
Fewer packages (~80 removed): desktop + browser + core tools; prevents installing third-party/untrusted apps that may be vulnerable to new exploits.

What do BIOS + boot loader passwords block?
?
BIOS: changing settings, booting system. Boot loader (GRUB/LILO): single-user mode, GRUB console, non-secure OS on dual-boot.

GRUB password hash command?
?
`grub-mkpasswd-pbkdf2` → paste hash via `password_pbkdf2 name <hash>` + `set superusers=` in `/etc/grub.d/40_custom`.

Debian manual patch commands?
?
`apt-get update` (fetch list), `apt-get upgrade` (upgrade current), `apt-get dist-upgrade` (install new). Red Hat: `yum check-update` / `yum update`. SUSE: `zypper`.

Discouraged when hardening installation?
?
Install more than needed; leave OS unprotected on hostile network pre-hardening; no update mechanism; single / volume for everything.

Why separate `/tmp` with nodev,noexec,nosuid?
?
Prevents resource exhaustion, device creation, binary execution, and setuid files in /tmp; sticky bit stops cross-user file deletion.
