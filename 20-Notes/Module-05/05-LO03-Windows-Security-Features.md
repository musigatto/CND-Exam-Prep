---
type: note
module: "05"
lo: "03"
tags: [concept, tool, command, mod/05]
topic: "Windows Security Features"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows Security Features (§5.3)

Windows security features: object protection · access checks · integrity control · virtual service accounts · secure file sharing · security auditing · Smart App Control · Vulnerable Driver Blocklist · Credential Guard.

## Windows Object Protection
- Windows objects carry **security descriptors** to control access; managed by **Windows Kernel Object Manager**
- **Securable object** = object with a security descriptor (admin can apply access control); all **named** Windows objects are securable, plus **process/thread** (unnamed) objects
- Visualize/manage: **WinObj** (Sysinternals, `www.sysinternals.com`)
- Security descriptor = owner + two ACLs:
  - **DACL** (discretionary) — users/groups **allowed or denied** access
  - **SACL** (system) — how the system **audits** access attempts
- ACL = list of **ACEs**; each ACE = access-rights set + a **SID** identifying a trustee
- Common securable objects: NTFS files/dirs · named/anonymous pipes · processes/threads · file-mapping objects · access tokens · window-management objects · registry keys · Windows services · local/remote printers · network share · inter-process synchronization objects · job objects · directory service objects

## Interaction: Threads ↔ Securable Objects
- Access check compares **thread's access token** (SIDs of user + groups) against object's **security descriptor** (owner + DACL)
- ACEs **accumulate**: ACE allowing read to a group + ACE allowing write to the user = both granted
- **No DACL** → everyone gets full access; **DACL with no ACEs** → no access; DACL limited to some groups → implicit deny for all others
- ACE order matters: keep a user's **access-denied ACE before** the group's access-allowed ACE, else the group grant wins
- **NULL DACL** (pointer NULL) = grants full access to all, normal access checks skipped (dangerous) · **Empty DACL** = allocated, no ACEs = grants **nothing**

## Windows Access Checks
- Decision to allow/deny a subject (user/process) → securable object by matching user's access token vs DACL ACEs
- **Access token** = kernel object attached to a process describing its **security context**; created at successful logon; each process of the user holds a copy
- Token contents: user SID · group SIDs · logon SID · privileges (user/group) · owner SID · primary-group SID · default DACL for new objects · token source · primary vs impersonation flag · optional restricted SIDs · impersonation levels · other statistics

### Security Identifier (SID)
- Variable-length unique value identifying a **security principal or group**; view to troubleshoot access issues across a domain
- View SID: `psgetsid <Domain>\<User>` (Sysinternals) · Process Explorer → process → **Security** tab
- All users: `wmic useraccount get name,sid` (CMD) / `Get-WmiObject win32_useraccount | Select name, sid` (PS) / `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList` (**ProfileImagePath** = username for the SID key)

| Well-known SID | Name | Meaning |
|---|---|---|
| S-1-0-0 | Nobody | used when the SID is unknown |
| S-1-1-0 | Everyone | all users except anonymous |
| S-1-2-0 | Local | users logging to the terminal / locally connected |
| S-1-3-0 | Creator Owner | replaced by SID of user who created a new object |
| S-1-3-1 | Creator Group | replaced by primary-group SID of object creator |
| S-1-9-0 | Resource Manager | 3rd-party apps doing own security on internal data (e.g., Exchange) |

## Integrity Control (WIC / Mandatory Integrity Control, MIC)
- Access-control based on **integrity/trustworthiness**; levels assigned by the OS and **override discretionary (NTFS) permissions**
- A subject may only interact with objects of **equal or lower** integrity
- Six integrity levels: **Untrusted → Low → Medium → High → System → Installer**
  - **Low** — default when interacting with Internet (IE protected mode / PMIE)
  - **Medium** — standard users; default level for unspecified objects
  - **High** — launched via **Run As Administrator**
  - **Installer** — highest; can uninstall all other objects
- Level determined by presence of specific groups in the `TOKEN_GROUPS` structure

| Group | SID | Integrity |
|---|---|---|
| LocalSystem | S-1-5-18 | System |
| Local Service | S-1-5-19 | System |
| Network Service | S-1-5-20 | System |
| Administrators | (garbled in OCR) | High |
| Backup Operators | S-1-5-32-551 | High |
| Network Configuration Operators | S-1-5-32-556 | High |
| Cryptographic Operators | S-1-5-32-569 | High |
| Authenticated Users | S-1-5-11 | Medium |
| Everyone | S-1-1-0 | Medium |
| Anonymous (Anon Logon) | S-1-5-7 | Untrusted |

- View integrity in **Process Explorer**: right-click Process column → Select Columns → check **Integrity Level** (cmd.exe = Medium for normal user, High with admin)
- WIC benefits: automatic token integrity levels · automatic mandatory labels by security subsystem · simplicity (MAC framework) · flexibility/extensibility (resource managers) · legacy support · automatic integrity configuration

## Virtual Service Accounts
- Special account type enhancing security isolation + access control of Windows services; **each service runs under its own account with its own SID**
- Auto-managed: no creation needed; passwords set + **periodically changed by Windows** (simplifies auditing/tracking); not privileged locally (member of local users); on network behaves as system account `DOMAIN\computer_name$` if domain-joined, else anonymous
- Name: `NT SERVICE\<service name>`
- Create via **sc** (service control): `sc create Demo1 obj="NT SERVICE\demo1" binPath= D:\Demo\HelloWorld.exe`
- Per Windows version, service hardening uses **per-service SID**, a **virtual service account**, or both

## Secure File Sharing
- Restrict access to **users without privileges**; created by making file shares, setting permissions, accessing over LAN/VPN
- Enforce: password protection · right permissions · advanced sharing settings · shared-folder wizard
- **128-bit encryption** for file-sharing connections (some devices need 40-/56-bit); **password-protected sharing** = only accounts with user+password on the machine reach shared files/printers/Public folders (`Control Panel → Network and Sharing Center → Change advanced sharing settings → All Networks → Password protected sharing → Turn on`)
- Shared-folder rules: permissions apply to **folders, not files**; don't cascade into contained items; apply to every connecting user; FAT volumes rely on them; group permission = every member
- Best practices: assign to **group** accounts not users · least-privilege restrictions · consolidate resources in one place · **don't explicitly deny** (deny wins over group allow) · set NTFS permissions for local logon (shared-folder perms only cover network + FAT) · preserve permissions when copying/moving shares
- Commands: `net share sharedFolder=C:\SharedFiles /grant:Bob,READ` (CMD) · `Revoke-SmbShareAccess -Name "sharedFolder" -AccountName Everyone` (PS)
- **Server Manager** → System Tools → Shared Folders → Shares → New Shares → **Create A Shared Folder Wizard**; Server Manager can also create **NFS shares** compatible with Linux

## Security Auditing
- Identify **attacks (successful or not)** against the network / valuable resources; enable via **Group Policy** (AD) or **Local Security Policy** (single machine)
- Basic: Local Security Policy → Local Policies → **Audit Policy** → enable Success/Failure per category; advanced (Win7+/2008R2+): **Advanced Audit Policy Configuration → System Audit Policies**

| Audit category | Records |
|---|---|
| Account logon events | attempts to use an AD account to authenticate |
| Account management | create/delete/modify user-group-computer accounts, password resets |
| Directory service access | events in the system ACL (e.g., permissions) |
| Logon events | user logs on locally or via network |
| Object access | access to files, folders, registry keys, printers |
| Policy change | changes to user-rights assignment, audit, trust policies |
| Privilege use | attempts to use permissions/user rights |
| Process tracking | process creation/termination, handle duplication, indirect object access |
| System events | restarts, shutdowns, security-log-affecting changes |

- **Event ID 4625** = failed logon (`Get-WinEvent` to view); Logon Type 2 = interactive, 3 = network; failure reason e.g. unknown user name/bad password

## Smart App Control
- Blocks potentially malicious/untrusted apps + **PUA** (ads, slowdowns, extra software); complements Defender or third-party AV; combines Microsoft **app intelligence services** + **code integrity**
- Delays block if app has a **valid cert from a CA in the Trusted Root Program**; by default blocks PUA, malware, unsigned + unknown code
- Modes: **Evaluation** (background observation, decides fit) · **Enforcement** (only apps recognized by app-intelligence or signed with trusted cert run)
- Enable: `Settings → Windows Security → App and Browser Control`; verify mode: `citool.exe -lp` → FriendlyName `VerifiedAndReputableDesktopEvaluation` = Evaluation, `VerifiedAndReputableDesktop` = Enforcement
- Turning off SAC is **permanent** (requires Windows reinstall)

## Microsoft Vulnerable Driver Blocklist
- Blocks drivers with known security vulnerabilities; **enabled by default** (Windows 11 2022 update) on all devices; mandates prior third-party-driver validation
- Functions: block certs used to sign malware · block unnatural suspicious network behavior · block known vulnerabilities
- Advantages: privilege-escalation prevention · threat mitigation · system stability · improved UX · standards compliance · zero-day protection
- Enable: Windows Security → **Device security → Core isolation details** (Method 1); or Registry (Method 2): `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\CI\Config` → DWORD `VulnerableDriverBlocklistEnable` = **1**

## Windows Defender Credential Guard
- Virtualization-based protection of secrets → **only the right software** reaches them; thwarts **pass-the-hash (PtH)** and **pass-the-ticket (PtT)**; shields NTLM passwords, Kerberos **TGTs**, app-stored domain credentials
- Enable via **Group Policy, Registry, or Microsoft Intune**
- Features: **virtualization-based security** runs NTLM/Kerberos-derived credentials in a space isolated from the OS; blocks **admin-privileged malware** from accessing privileged secrets (APTs)
- GPO: Computer Config → Admin Templates → **System → Device Guard** → Turn On Virtualization Based Security → Enabled; Platform Security Level: Secure Boot / Secure Boot + DMA; Credential Guard Config: Enabled **with UEFI lock** (requires Win10 / Server 2016+)
- Intune: Devices → Configuration Profiles → Create Profile → Settings catalog (Device Guard category) or Account protection profile → Turn on Credential Guard
- Registry: `...\Control\DeviceGuard` → `EnableVirtualizationBasedSecurity`=1, `RequirePlatformSecurityFeatures`=1 (Secure Boot) or **3** (Secure Boot+DMA); `...\Control\Lsa` → `LsaCfgFlags`=1 (with UEFI lock) / **2** (without) / **0** (off)

## Cards
Q:: Windows object access control: DACL vs SACL?
A:: DACL = who is allowed/denied access; SACL = how the system audits access attempts. Part of the object's security descriptor.
#flashcard
Q:: NULL DACL vs empty DACL?
A:: NULL DACL grants full access to everyone, skips normal checks; empty DACL (0 ACEs) grants no access.
#flashcard
Q:: Access-check ACE accumulation?
A:: Access rights per ACE accumulate (read from one group + write for user = both); order matters — user deny-ACE must precede group allow-ACE.
#flashcard
Q:: View a user's SID?
A:: PsGetSid: `psgetsid <Domain>\<User>`; Process Explorer Security tab; `wmic useraccount get name,sid`; registry ProfileList.
#flashcard
Q:: Windows integrity levels (low→high)?
A:: Untrusted → Low → Medium → High → System → Installer.
#flashcard
Q:: Integrity level of a Run As Administrator process?
A:: High; standard-user processes run Medium; IE protected mode (PMIE) runs Low.
#flashcard
Q:: Virtual service account name + benefit?
A:: `NT SERVICE\<service name>`, own SID, password auto-managed by Windows; created via `sc create ... obj="NT SERVICE\..."`.
#flashcard
Q:: Audit category for password reset?
A:: Audit account management.
#flashcard
Q:: Event ID 4625?
A:: An account failed to log on; Logon Types: 2 = interactive, 3 = network.
#flashcard
Q:: Smart App Control enforcement rule?
A:: Apps run only when recognized by Microsoft app intelligence or signed with a trusted cert; verify mode via `citool.exe -lp`.
#flashcard
Q:: Credential Guard protections + attack types?
A:: Virtualization-isolated secrets (NTLM pwds, Kerberos TGTs, app credentials); blocks pass-the-hash (PtH) and pass-the-ticket (PtT).
#flashcard
Q:: Vulnerable Driver Blocklist registry key?
A:: `HKLM\SYSTEM\CurrentControlSet\Control\CI\Config` → `VulnerableDriverBlocklistEnable` = 1.
#flashcard