---
type: note
module: "05"
lo: "08"
tags: [concept, command, tool, mod/05]
topic: "Windows OS Security Hardening Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows OS Security Hardening Techniques (§5.8)

Configure OS security parameters correctly and ensure policies reduce system exposure to attacks.

## Setup BIOS Password
- First protection layer of the computer; maintains OS security at a low level
- **Boot-level BIOS password** required at every start — until entered, the system stays disabled
- Separate **Supervisor password** gates the **setup utility** (blocks unauthorized BIOS changes)
- Steps: BIOS Setup Utility → **Security** → Set Supervisor Password → New + Confirm → *"Changes have been saved"* → **Set User Password** (controls **access to the system at boot**) → enable **Password on boot** → confirm save

## Prevent Windows from Storing LAN Manager Hash
- Windows stores passwords as hashes; **<15 characters → LM hash**, otherwise **NT hash**; both brute-forceable; **LM hashes are weak** (stored in SAM)
- GPO: Computer Configuration → Security Settings → Local Policies → Security Options → **`Network security: Do not store LAN Manager hash value on next password change`** → **Enabled** (forces the stronger NT hash)

## Restrict Software Installations
- Apps from untrusted sources install **malicious background files** that spread malware through the network → restrict installs
- GPO: Computer Configuration → Admin Templates → **Windows Components → Windows Installer → `Prohibit User Install`** → Enabled (User Install Behavior dropdown)
  - **Hide User Installs**: installer ignores per-user apps; per-computer install visible to everyone
  - **Allow User Installs** (or not configured): both per-user and per-computer products used; a per-user install **hides** the per-computer install of the same product

## Disable Unwanted Services
- Attackers exploit security holes in services to break in; disable unused/vulnerable ones
- Candidates: **IIS · FTP · SQL Server · Proxy services · Telnet · Universal Plug and Play**
- GUI: Control Panel → Administrative Tools → Services
- PowerShell: `Get-WmiObject -class Win32_Service -ComputerName <host> | Select Name, State, StartName`; disable with `Set-Service <service> -StartupType Disabled`

## Disable Remote Desktop on Windows
- RDP grants access from anywhere; with leaked username/password an attacker misuses remote access to files/apps → disable when unused
- **Method 1 — Settings**: Settings → System → Remote Desktop → toggle **Off** → Confirm
- **Method 2 — Control Panel**: System and Security → System → **Allow remote access** → Remote Desktop → **Don't allow remote connections to this computer** → Apply/OK
- **Method 3 — Command**: `net stop termservice` (Y), then `sc config termservice start= disabled`

## Install Antivirus Software
- Protects against viruses, Trojans, worms, spyware, spam, hackers + unknown threats; acts as a **two-way firewall** (monitors in/out traffic, blocks suspicious transfers); some versions restore corrupted data and lengthen device life
- Windows 11 built-in: **Windows Defender Antivirus** — real-time protection over email, apps, Internet, cloud; **quick scan** = areas where malware usually hides; **full scan** = all files + applications

| Third-party AV | Distinct features (per PDF) |
|---|---|
| NortonLifeLock (nortonlifelock.com) | Multi-layered; virus detection without false flagging; blocks hacker infiltration; prevent/recover from identity theft |
| Bitdefender (bitdefender.com) | Multi-layer ransomware protection, webcam protection, auto upgrades; shields mobile devices from physical theft; extends laptop/tablet battery life |
| BullGuard (bullguard.com) | Triple-layered anti-malware + machine learning; fast/accurate scans; identity-theft protection |
| McAfee (mcafee.com) | Encrypted document folder; remote fix of PC security issues |
| Kaspersky (kaspersky.co.in) | Blocks viruses/ransomware/spyware/**cryptolockers**; stops **cryptocurrency-mining** malware; undoes virus damage |

## Enable Windows Defender Firewall
- Monitors in/out traffic; controls data packets per ruleset; built into Windows
- Enable: Settings → **Virus & Threat Protection → Manage Settings → Real-time protection**; **Firewall and Network Protection → turn on Defender Firewall** for the network
- PowerShell: `Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled true`; `New-NetFirewallRule -RemoteAddress 10.10.10.12/24 -DisplayName "Local subnet" -Direction Inbound -Profile Any -Action Allow`; `Get-NetFirewallRule`
- Advanced Security: configure **Inbound / Outbound Rules**; default = inbound blocked unless an allow rule matches, outbound allowed unless blocked
- **Monitoring** view: active firewall rules, active connection-security rules, security associations

## Monitor Windows Registry
- Central Windows **configuration database** (settings for software, hardware, user preferences, OS config; tracks user actions — logs, autorun locations, MRU lists, UserAssist); access via `regedit`
- Registry **key** ≈ folder (holds values + subkeys); **hive** = group of keys at the top of the hierarchy
- Hives: **HKLM** (machine config — `Software\Microsoft` under it) · **HKCU** (current user details — desktop, network connections, printers, app preferences; new subkey **each login**) · **HKCC** (currently used hardware profile) · **HKCR** (file extensions + COM registration)
- Monitor in real time with **Process Monitor** (Sysinternals, `www.sysinternals.com`) — regular monitoring/auditing exposes traces of malicious registry activity
- PowerShell: `Get-PSDrive -PSProvider Registry`; `Set-Location HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion; Get-ChildItem`

## Cards
Q:: LM vs NT hash?
A:: <15-char passwords → LM hash, else NT hash; both brute-forceable — block LM storage via 'Network security: Do not store LAN Manager hash value on next password change'.
#flashcard
Q:: Example Windows services to disable when unused?
A:: IIS, FTP, SQL Server, proxy services, Telnet, Universal Plug and Play.
#flashcard
Q:: Disable Remote Desktop (commands)?
A:: `net stop termservice`, then `sc config termservice start= disabled`.
#flashcard
Q:: Windows Defender quick scan vs full scan?
A:: Quick = areas where malware usually hides; full = all files and applications.
#flashcard
Q:: Registry hives (key names)?
A:: HKLM (machine) · HKCU (current user; new subkey each logon) · HKCC (hardware profile) · HKCR (file extensions + COM registration).
#flashcard
Q:: Registry monitoring tool?
A:: Process Monitor (Sysinternals) — real-time registry (and file/system) activity.
#flashcard
Q:: Firewall default rule behavior?
A:: Inbound connections blocked unless an allow rule matches; outbound connections allowed unless a block rule matches.
#flashcard