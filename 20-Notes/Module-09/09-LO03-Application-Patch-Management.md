---
type: note
module: "09"
lo: "03"
tags: [tool, process, bestpractice, mod/09]
topic: "Application Patch Management"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Application Patch Management (§9.3)

## Concept
- **Application/software patch management** = process of **monitoring and deploying new or missing patches** to ensure security of applications on hosts
- Unpatched apps → serious breaches; automated with **patch management software** (manual = delays/missed patches)
- Hackers exploit the vulnerabilities announced with each patch → **apply patches as quickly as possible**

## Patch Management Software Flow
`Scan for new/missing patches → Download patches to central location → Select relevant patch for clients → Test the patch → Deploy if test succeeds`

## Key Features of Patch Management Solutions
- **Centralized patch management** — third-party app patching, central download
- **Whole-network scanning** — detect connected servers/end users; OS + software detection; some scan VMs + cloud machines
- **Patch status detection dashboard** shows: patched + malicious software · unrecognized app flags · unknown patch status · compliance reports
- **Test on few systems before org-wide deployment** (patch testing order by criticality)
- **Groups** — apply patches to different groups at different times (prevents network congestion)

## SolarWinds Patch Manager (third-party patching)
- Automated patch mgmt for MS servers/workstations + **third-party apps**
- Features: **WSUS** server patching · **SCCM** integration · vulnerability management · pre-built/pre-tested packages · compliance reports · status dashboard
- Supported third-party apps: Adobe, Yahoo! Messenger, Citrix Receiver, Google Earth, Skype, Mozilla Firefox, RealVNC, Notepad++, Opera, RealPlayer, Oracle/Sun Java Runtime, QuickTime

## Patch Management Solutions & Tools
| Tool | Key point |
|---|---|
| **PDQ Deploy** | update 3rd-party software, custom scripts, config changes in minutes |
| **LANDESK Patch Manager** | (Ivanti/LANDesk) |
| **Shavlik Protect** | SCCM, Mac OS, virtual infrastructure, third-party patching |
| **Kaseya Patch Management** | consistent timely security updates for servers/workstations/third-party apps |
| **Flexera Software Vulnerability Manager** | identify vulnerable apps + apply patches |
| **HP Touchpoint Manager** | track updates/patches across devices; 3rd-party (Acrobat, Java, iTunes) |
| **Ivanti Patch for Endpoint Manager** | adds patch mgmt to EPM; 3rd-party patching, distributed/remote patching, lifecycle mgmt, automated updates |
| **Syxsense** | visibility + control; patches + vulnerability detection; compliance reporting |
| **Itarian** | identify vulnerable endpoints; scheduled group updates; remote OS updates |

## Cards
Q:: Patch management definition?
A:: Process of monitoring + deploying new or missing patches to keep applications on hosts secure.
#flashcard
Q:: Patch management flow?
A:: Scan for new/missing → download centrally → select relevant client patch → test → deploy if pass.
#flashcard
Q:: Why apply patches urgently?
A:: Hackers build exploits from each patch's disclosed vulnerabilities; unpatched apps get compromised.
#flashcard
Q:: Dashboard (patch status detection) shows?
A:: Patched + malicious software · unrecognized-app flags · unknown patch status · compliance reports.
#flashcard
Q:: Why test before org-wide deploy?
A:: Ensure patches don't break apps; tests on a few systems → deploy if successful.
#flashcard
Q:: SolarWinds Patch Manager features?
A:: WSUS + SCCM integration, vulnerability mgmt, pre-tested packages, compliance reports, dashboard; patched 3rd-party apps (Adobe, Java, etc.).
#flashcard