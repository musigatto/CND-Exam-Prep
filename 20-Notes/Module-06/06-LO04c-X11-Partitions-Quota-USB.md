---
type: note
module: "06"
lo: "04"
tags: [process, tool, command, policy, concept, mod/06]
topic: "Linux X11 Removal, Disk Partitions, Quota, USB Block"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Delete X Window System, Partitions, Disk Quota, USB (§6.4 cont.)

## Delete X Window Systems (X11)
- CentOS/RHEL 5.x/Fedora ship with X Window = graphical interface for Linux, **not required** for dedicated mail & Apache/Nginx web servers
- Vulnerabilities in X11 can help **non-root users escalate privilege**; disable/remove it
- Disable X Windows at boot: edit `/etc/inittab` → set **runlevel 3**
  1. `vi /etc/inittab`
  2. Find line `id:5:initdefault:`
  3. Replace with `id:3:initdefault:`
- Remove X Window System (Red Hat): `yum groupremove "X Window System"`

## Create Separate Disk Partitions for Linux System
- Separate OS from user files → easier recovery, better performance, higher data security
- Mount on separate partitions: **`/usr`** (binaries/kernel source), **`/home`** (home dirs), **`/var` and `/var/tmp`** (spool/mail/printing/error logs), **`/tmp`** (temp data); Apache/FTP roots on own partitions
- `/etc/fstab` mount options:
  - `noexec` — no binary execution on partition (scripts still allowed)
  - `nodev` — no character/special device files (zero, sda)
  - `nosuid` — no SUID/SGID access (prevent setuid bit)
- Example: `/dev/sda04 /ftpdata ext3 defaults,nosuid,nodev,noexec`

## Enable Disk Quota
- Restricts disk space, alerts admin before partition is full / user overconsumes; limits files a user can create; configurable per user or group
- **Step 1 — install**: `$ sudo apt install quota` (check: `quota --version`)
- **Step 2 — kernel module**: confirm `quota_v1`/`quota_v2` present: `$ find /lib/modules/`uname -r` -type f -name '*quota_v*.ko*'`; if missing: `$ sudo apt install linux-image-extra-virtual`
- **Step 3 — /etc/fstab**: add quota mount options, e.g. root fs line `LABEL=cloudimg-rootfs / ext4 usrquota,grpquota 0 0` → remount `$ sudo mount -o remount /`; verify via `$ sudo cat /proc/mounts | grep`
- **Step 4 — enable**: `$ sudo quotacheck -ugm /` (creates `aquota.user`/`aquota.group`) then `$ sudo quotaon -v /`
- **Step 5 — configure user**: `edquota -u james` (edit soft/hard block+inode limits, `uid`, FS, blocks, inodes); verify `$ sudo quota -vs james`

## Disable USB Storage
- Default: Linux mounts removable devices → attackers may copy files or run malicious scripts; disable for unprivileged users
- Methods (Red Hat family):
  - **Fake install**: create `/etc/modprobe.d/block_usb.conf` → line `install usb-storage /bin/true` → save + reboot
  - **Blacklist**: create `/etc/modprobe.d/blacklist.conf` → line `blacklist usb-storage` → save + reboot (note: privileged user can reload with `$ sudo modprobe usb-storage`)
- **Remove/move driver**: `cd /lib/modules/`uname -r`/kernel/drivers/usb/storage/` → Red Hat: `sudo mv usb-storage.ko usb-storage.ko.xz.blacklist` → Debian: `sudo mv usb-storage.ko usb-storage.ko.blacklist`
- **Block via firmware/OS**:
  - BIOS option: disable USB from BIOS config; protect BIOS with password so nobody boots from USB
  - GRUB option: open grub.conf / menu.lst, add `nousb` to the kernel line (e.g. `kernel /vmlinuz-2.6.18-128.1.1.el5 ro root=LABEL=/ console=tty0 console=ttyS1,19200n8 nousb`)

## Cards
Q:: Disable X Windows at boot?
A:: Edit /etc/inittab: `id:5:initdefault:` → `id:3:initdefault:`; remove via `yum groupremove "X Window System"`.
#flashcard
Q:: Separate which partition mounts + fstab options?
A:: /usr, /home, /var, /var/tmp, /tmp (+Apache/FTP roots). Options: noexec (no binaries), nodev (no device files), nosuid (no SUID/SGID).
#flashcard
Q:: Disk quota enable step sequence?
A:: `sudo apt install quota` → verify quota_v1/v2 module → edit /etc/fstab (usrquota,grpquota) + `mount -o remount /` → `quotacheck -ugm /` → `quotaon -v /` → `edquota -u <user>` → check `quota -vs <user>`.
#flashcard
Q:: Methods to block usb-storage?
A:: Fake install `install usb-storage /bin/true` in /etc/modprobe.d/block_usb.conf; blacklist in /etc/modprobe.d/blacklist.conf; rename usb-storage.ko → .blacklist; BIOS disable; GRUB `nousb` kernel arg.
#flashcard
Q:: Why remove X11?
A:: Not needed for dedicated mail/web servers; vulnerabilities can escalate non-root users to higher privilege.
#flashcard