---

type: note
module: "06"
lo: "01"
tags: [concept, threat, mod/06, flashcard/06]
topic: "Linux OS and Security Concerns"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux OS and Security Concerns (§6.1)

Open-source OS widely used across enterprises and governments; a popular UNIX version, around since mid-1990s.

## Linux System Architecture
- **Hardware**: physical devices — monitor, RAM, HDD, CPU
- **Kernel**: core component; complete control over system resources; interacts directly with hardware
- **Shell**: interface to kernel, hides kernel-function complexity; takes commands, returns output
- **Applications/utilities**: launched via shell; specialized/individual tasks
- **System libraries**: special functions/programs; used without access rights to reach kernel modules
- **Daemons**: background services (printing, scheduling, sound); start at boot or after desktop login
- **Graphical server**: subsystem showing graphics on the monitor; referred to as **X server / X**

## Linux Advantages
- Freely available to the public
- Applications installed **without rebooting the OS**
- Open source → customization to **fix bugs rapidly**

## Timeline (Table 6.1)
| Year | Event |
|------|-------|
| 1991 | First Linux code released |
| 1992 | Licensed under **GPL** |
| 1993 | **Slackware** first widely adopted distribution |
| 1996 | Penguin chosen as Linux **mascot** |
| 1998 | Tech giants announce platform support |
| 1999 | **Red Hat** goes public |
| 2003 | IBM Linux Super Bowl ad |
| 2005 | Linux on Business Week cover |
| 2007 | **Linux Foundation** formed |
| 2010 | Linux-based **Android** outships other smartphone OSes |
| 2011 | Linux powers supercomputers, ATMs, phones |

## Linux Features
- **Portability**: same behavior on different hardware
- **Open-source**: free, community-based development
- **Multiuser**: multiple users access resources at once
- **Multiprogramming**: multiple programs run at once
- **Hierarchical file system**: standard tree-like structure
- **Shell**: special interpreter to execute OS commands
- **Security**: authentication (password protection), controlled access to files, data encryption

## Linux Security Concerns
- Historically seen as inherently secure (inspectable code), but attackers have exploited vulnerabilities in the recent past
- CVE data (cvedetails.com): example **CVE-2023-42755** — flaw in IPv4 Resource Reservation Protocol (RSVP) classifier; `xprt` pointer goes beyond the linear part of `skb` → out-of-bounds read in `rsvp_classify`; allows **local user to crash the system (DoS)**, CVSS **6.5**
- Example **CVE-2023-39198**, CVSS **7.5**
- Linux OS is free/open-source → modifiable and distributable by anyone → **unexpected vulnerabilities can be introduced**
- Some vulnerabilities arise from **defender oversight and poor configuration settings**
- Recent attacks show Linux is being **targeted for various malware attacks**

## Cards
Core parts of the Linux system architecture?
?
Hardware → kernel (core, full resource control) → shell (interface to kernel) → applications/utilities, system libraries, daemons (background services), graphical server (X server/X).

Key Linux features (security relevant)?
?
Portability, open-source, multiuser, multiprogramming, hierarchical FS, shell, security (authentication/password protection, controlled file access, data encryption).

Why is Linux considered risky despite open code?
?
Open-source → anyone can modify/distribute → unexpected vulnerabilities; poor configuration and defender oversight; increasingly targeted by malware.

CVE-2023-42755 example?
?
IPv4 RSVP classifier flaw — out-of-bounds read in rsvp_classify; local user can crash system → DoS (CVSS 6.5).
