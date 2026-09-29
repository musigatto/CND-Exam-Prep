---

type: note
module: "05"
lo: "02"
tags: [concept, tool, mod/05, flashcard/05]
topic: "Windows Security Components"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows Security Components (§5.2)

Windows security model = collection of **user-mode + kernel-mode processes** that monitor/manage/coordinate OS security components. Security blocks: **SRM · LSASS · SAM · WinLogon+NetLogon · Windows Registry · Access control · Active Directory**.

## Security Reference Monitor (SRM)
- Enforces an **access control policy (ACL)** over subjects' ability to operate on objects — validates that subject has rights, protects objects from unauthorized access/modification, isolates objects
- Kernel component in the Windows executive: `%SystemRoot%\system32\Ntoskrnl.exe`; **unrestricted access**; logs activity for auditing (Fig 5.4: Alice=full, David=read, Bob=write, John/Smith=no access)
- The security kernel enforces the rules the reference monitor sets; admins = privileged mode, users = restricted

## Local Security Authority Subsystem (LSASS)
- User-mode process: `%WINDIR%\System32\lsass.exe`; ensures a user is **authenticated at local logon**
- Implements local security policies: privileges per user/group, security-auditing settings, user authentication, sends audit messages to Event Log; **issues security tokens**; key logon-process component
- On local logon: LSASS transfers credentials to **SAM**; SAM matches against local DB → creates logon session → returns **SID + group SIDs** → LSASS grants an **access token** (user SID + group SIDs + rights)
- If LSASS is force-stopped, the screen loses accounts and the system restarts
- **LSASS policy database**: local system-security-policy settings, ACL-protected, under `HKLM\SECURITY`. Contents: trusted domains for logon auth, who may access the system, assigned privileges, auditing types, "secrets" (cached-domain + service-account logon info)

## Security Account Manager (SAM)
- Database storing **hashed logon credentials** of local users/groups; user-mode component; passwords hashed so even DB theft doesn't reveal plaintext
- SAM service: `%SystemRoot%\System32\samsrv.dll`; SAM database in registry at `C:\Windows\System32\config\`
- **Workgroup vs domain**: workgroup logon = only local-SAM match accepted; domain-joined = local logon (local SAM) + domain-user logon (Active Directory via WinLogon)
- Local-user logon **can't access network resources**; a DC uses the **AD database** instead of SAM, SAM only for **DSRM** (Directory Services Restore Mode) boot — DSRM admin password lives in SAM, not AD, so local logon always possible via SAM
- Flow (Fig 5.6): logon → run auth package → verify in database → return SID → create access token → create subject

## Active Directory (AD)
- Microsoft directory service for **domain networks**; centralized security management (set up computers, VPN access, per-computer security policy, UI restrictions)
- Data stored as **objects** in a tree, accessed via **LDAP**: containers (site = by IP, domain, OU = logical structure) vs **leaf objects** (users, computers, printers — cannot contain objects)
- Benefits: central shared storage, departmental shares, personal storage on secure server, regular backups, searchable service access, centralized server support, **remote software install/patches**

## Authentication packages
- **DLLs running in context of LSASS** + client processes; enforce Windows authentication policy; verify logon credentials, return user **security identity** to LSASS (token generation)

## Interactive Logon Manager (Winlogon)
- User-mode process: `%SystemRoot%\System32\winlogon.exe`; runs in background since boot; **manages user authorization sessions**; creates user's first process at logon
- Functions: window station + desktop protection · **Ctrl-Alt-Del (SAS)** recognition · dispatch SAS routine · load user profile · assign security to user shell · screen saver control

## Logon UI + Credential Providers (CPs)
- **LogonUI** (`LogonUI.exe`): user-mode process presenting the auth UI; queries credentials via CPs; appears in Task Manager as "Windows Logon User Interface Host"; **trojans reuse this filename to hide**
- **CPs**: in-process **COM objects** running in LogonUI; collect username/password, smartcard PIN, biometrics. Standard: `authui.dll`, `SmartcardCredentialProvider.dll`. Functions: describe needed credentials, communicate with external auth authorities, **package credentials for interactive + network logon**

## Network Logon Service (NetLogon)
- `%SystemRoot%\System32\netlogon.dll` — a **service/DLL running continuously**; used for domain logons (AD); once Workstation service starts, NetLogon picks the target domain
- Functions: **identify the domain controller** for auth · set up a **secure channel** between itself + target system · send the auth request to the DC and return results

## Kernel Security Device Driver (KSecDD)
- Kernel-mode library: `%SystemRoot%\System32\Drivers\Ksecdd.sys`; kernel-mode security components implement **ALPC** (advanced LPC) and communicate with **LSASS in user mode**
- Table 5.1 — kernel security support functions/macros (for file-system filter drivers): `SecLookupAccountName` (name→SID+domain) · `SecLookupAccountSid` (SID→name+domain) · `SecLookupWellKnownSid` (well-known type→local SID) · `SecMakeSPN`/`SecMakeSPNEx`/`SecMakeSPNEx2` (SPN strings for security service providers)

## Cards
Windows security blocks/components?
?
SRM · LSASS · SAM · WinLogon/NetLogon · Registry · Access control · Active Directory.

SRM function + location?
?
Enforces ACL-based access control over subjects→objects, logs for auditing; kernel component `system32\Ntoskrnl.exe`.

LSASS role/location?
?
`lsass.exe`; local-logon authentication, local security policies, issues access tokens, audit messages to Event Log.

SAM store + location?
?
Hashed local logon credentials; `samsrv.dll`, DB in `C:\Windows\System32\config\`.

DC logon-database usage?
?
DC uses AD database; SAM only for DSRM boot / local logon (DSRM password stored in SAM).

Credential providers?
?
COM objects in LogonUI collecting password/PIN/biometrics (authui.dll, SmartcardCredentialProvider.dll).

NetLogon functions?
?
Identify DC, set up secure channel, send auth request to DC, return result; used for AD logons.

KSecDD?
?
Kernel-mode library `ksecdd.sys` for ALPC; kernel-mode security ↔ LSASS in user mode; SecLookup*/SecMakeSPN* functions.


## Cards (verified set 617277655)

> Matched word-for-word to the module PDF. See [[External-Flashcards-Verification]].

Security Reference Monitor (SRM)
?
enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.  _(Mod 05 p17)_


Local Security Authority Subsystem (LSASS)
?
implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.  _(Mod 05 p19)_


Security Accounts Manager (SAM)
?
is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.  _(Mod 05 p21)_


Network logon service (NetLogon)
?
a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.  _(Mod 05 p30)_


Windows logon application (WinLogon)
?
used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background  _(Mod 05 p27)_


CPs
?
a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.  _(Mod 05 p29)_
