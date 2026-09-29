---
type: note
module: "05"
lo: "01"
tags: [concept, mod/05]
topic: "Windows OS and Security Concerns"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows OS and Security Concerns (§5.1)

Windows = most widely used OS (PCs, private + government); support for servers + mobile. Windows Server versions released under **LTSC**.

## OS family
- **MS-DOS-based / 9x**: MS-DOS 1.0–6.x · Windows 1.0–2.0 (1985–92, point-and-click) · 3.0–3.1 (PM/FM/print manager) · 95 · 98/98 SE (FAT32, AGP, Active Desktop = IE integrated) · ME (Movie Maker, WIA; removed "boot in DOS")
- **NT kernel (PC)**: NT 3.1 (32-bit, 16-bit arch) · 3.5 (NT Workstation/Server) · 3.51 (PCMCIA, NTFS compression, GINA, OpenGL) · NT 4.0 (system policies, System Policy Editor, Crypto API, MSMQ) · 2000/NT 5.0 (PnP, NTFS 3.0, EFS, dynamic disks) · XP (Home/Pro; IEEE 802.11x) · Vista (Home/Pro/Business/Enterprise/Ultimate) · 7 (multi-touch, VHD support) · 8 (touch, x86+ARM) · 10 (fast start, Edge, Home/Pro/Pro-WS/Enterprise/OEM/Education/LTSC/IoT) · 11 (Snap Layouts/Groups, Desktops, Teams chat, Edge)
- **NT kernel (Server)**: Server 2003 (IIS v6, AD, group policy) · 2003 R2 (.NET 2.0, ADFS) · Home Server 2007 · 2008 (Server Core, failover clustering, SRM) · 2008 R2 (Hyper-V) · 2012 (Task Manager, IPAM, AD, IIS 8) · 2016 (Windows Defender, RDS, failover clustering) · **2019** (Kubernetes v1.14, Tigera Calico, storage migration/replica/Spaces Direct, shielded VMs, Windows Defender ATP)

## Architecture — two modes
- **Layered design**: HAL → microkernel → executive services → environment + integral subsystems
- **User mode** (Fig 5.1): private virtual address space + private handle table per app → apps can't touch each other's memory; no direct hardware access; switches to kernel mode via system call (mode bit 1 → 0, back to 1 on return)
- **Kernel mode**: most components = OS (device drivers); unrestricted access to memory + devices; exceptions can crash the whole OS
- **Ring model** (Fig 5.2): Ring **0** (kernel = most privileged) … Ring **3** (user/apps = least privileged); drivers at rings 1/2

## Layer model (Fig 5.3)
- **Environment subsystems** (user mode): **Win32** (32-bit Windows apps) · **OS/2** (16-bit OS/2, not 32-bit/graphical) · **POSIX** (POSIX.1/ISO-IEC) · **WSL** replaced POSIX (compatibility layer for Linux binaries on Win10/Server 2019)
- **Integral subsystems** (user mode): **Security subsystem** (tokens, login auth, auditing, Active Directory) · **Workstation service** (network redirector = client side of file/print sharing) · **Server service** (lets others access local file/print shares)
- **Kernel mode / executive**: **Object Manager** (manages Windows resources) · **I/O Manager** (devices ↔ user-mode subsystems) · **Cache Manager** (I/O caching) · **LPC** (inter-process comm ports) · **Security Reference Monitor (SRM)** (primary authority for Windows security rules; decides ACL-based object access) · **VMM** (memory protection + paging) · **Process Manager** (thread/process + job concept) · **PnP Manager** · **Power Manager** (IRPs) · **Windows Configuration Manager** (registry) · **GDI** (drawing/fonts/palettes)
- **Kernel**: multiprocessor sync, thread/interrupt scheduling, trap + exception dispatch
- **HAL**: hardware-specific code (I/O interfaces, interrupt controllers, multiprocessors) hiding device differences

## Security concerns (§5.1 close)
- Built-in features exist, but attackers exploit Windows vulnerabilities **daily** (e.g., CVE-2023-21757 — Windows L2TP DoS, CVSS 7.5)
- Root causes: **unpatched OS · improper configurations · unused services/processes enabled · weak passwords · lack of anti-malware**

## Cards
Q:: Windows ring model?
A:: Ring 0 = kernel (most privileged) → rings 1/2 = drivers → ring 3 = user mode/apps (least privileged).
#flashcard
Q:: User mode vs kernel mode?
A:: User = private virtual address space, no direct HW access, isolates apps; kernel = unrestricted access, crashes can take the OS down.
#flashcard
Q:: Environment subsystems?
A:: Win32 · OS/2 · POSIX (replaced by WSL on Win10/Server 2019).
#flashcard
Q:: Integral subsystems?
A:: Security subsystem · Workstation service (redirector/client) · Server service (serves shares).
#flashcard
Q:: Security Reference Monitor?
A:: Primary authority implementing Windows security rules; decides object/resource access via ACLs.
#flashcard
Q:: Windows security concern root causes?
A:: Unpatched OS, improper configurations, unnecessary services/processes enabled, weak passwords, missing anti-malware.
#flashcard
Q:: WSL?
A:: Windows Subsystem for Linux — compatibility layer running Linux binaries on Windows 10 / Server 2019; replaced POSIX subsystem.
#flashcard