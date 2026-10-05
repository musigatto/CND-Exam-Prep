---

type: note
module: "05"
lo: "09"
tags: [concept, process, tool, command, bestpractice, mod/05]
topic: "Windows Active Directory Security Best Practices"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows Active Directory Security Best Practices (§5.9)

AD connects every domain system → compromise of AD = compromise of network. Protect accounts (LSASS, DA group, LAPS, NTLM), monitor events, harden via best practices.

## LSA Protection
- **LSA (Local Security Authority)** process hosts **SECURITY credential database**; protecting the LSA **memory and processes** prevents **malware and unauthorized access** to credentials
- Enable LSA protection via:
  - **Single PC** (local settings / Windows Security)
  - **Domain-level Group Policy** (deploy domain-wide)
  - **Registry**
- Protects against **credential theft** from LSASS memory before **Windows 8.1/Server 2012+** built them in

## Clean the Domain Admins (DA) Group
- Default: `Administrator` account in **Domain Admins** — tied to every system/laptop/server in domain → near-total network power
- Attackers escalate from a normal system to the DA admin via **pass-the-hash** (use the hash of the legitimate password, not the plaintext, to authenticate — often from an already-infiltrated **LM hash**)
- Removal: **Server Manager → Tools → Active Directory Users and Computers → double-click "Domain Admins" → Members tab → Remove** → confirm (repeat until only necessary members)

## Local Administrator Password Solution (LAPS)
- For **AD domain-joined** systems: periodically sets each computer's local Administrator password to a **new random, unique value** stored in **Active Directory**; retrieved at authentication
- Scope: local Administrator only; needs a **client-side extension (CSE)**; Windows only, no workflow/reporting/session-monitoring features
- Setup steps:
  1. **Download LAPS.x64.msi** and install
  2. **Extend AD schema**: `Import-module AdmPwd.PS; Update-AdmPwdADSchema` → adds 2 attributes (admin password + password expiration date/time)
  3. **Install LAPS GPO files**: `AdmPwd.admx` → `windows\policydefinitions`; `*.adml` → `windows\policydefinitions\<language>`; then LAPS appears under **Computer Configuration → Policies → Administrative Templates**
  4. **Assign permissions to groups**: `Set-AdmPwdResetPasswordPermission -OrgUnit "OU=servers,OU=computer accounts,DC=gdwnet,DC=com" -AllowedPrincipals "LAPS Admins"` (e.g. group whose users get a new password on logon)
  5. **Install the LAPS DLL** (`admpwd.dll` — select AdmPwd GPO extension on install); launch via **LAPS UI** (enter computer name → password filled automatically when permissions are set)

## Disable NTLM Protocol
- **NTLM** (NT LAN Manager) came with Windows NT; features: Unicode passwords, up to **127 chars**, stored as **128-bit MD4 hash** (stronger than LM)
- **NTLMv2** = most secure version, shipped with **Windows NT SP4** (new password response); **MD4** hashing for passwords (as NTLM), **MD5** for usernames + server names; over the network the info **differs each time**
- **Block NTLM v1** to force **NTLMv2**
- GPO: **Computer Configuration → Windows Settings → Security Settings → Local Policies → Security Options → `Network security: Restrict NTLM: NTLM authentication ...`**
  - Set to **Deny** options (e.g. *Deny all*) or **Disabled**; **Kerberos** is then preferred in the AD domain

## Monitor AD Events for Signs of Compromise
- Watch for:
  - **Changes to administrator groups**
  - **Wrong-password attempts**
  - **Usage of locked-out accounts**
  - **Account lockouts**
  - **Changes in antivirus software settings**
  - **Activities by privileged accounts**
- Better via third-party tools that emit reports: **Elk Stack, Lepide, Splunk, Windows Event Forwarding**
- Event Viewer: **Windows Logs** → right-click log type (Application/Security/System…) → **Filter Current Log** for custom reports

## PowerShell Cmdlets for Securing AD

| # | Task | Cmdlet |
|---|---|---|
| 1 | View default password policy | `Get-ADDefaultDomainPasswordPolicy` (ComplexityEnabled True; LockoutDuration **00:30:00**; LockoutObservationWindow **00:30:00**; MaxPasswordAge **10 days**; MinPasswordAge **1 day**; MinPasswordLength **11**; PasswordHistoryCount **24**; ReversibleEncryptionEnabled **False**) |
| 2 | Accounts with password never expires | `Get-ADUser -Filter * -Properties Name, PasswordNeverExpires \| Where-Object {$_.PasswordNeverExpires -eq $true}` |
| 3 | Force password change next logon | `Set-ADUser -Identity Alice -ChangePasswordAtLogon $true` |
| 4 | Disable account / list disabled | `Disable-ADAccount -Identity Alice` ; `Search-ADAccount -AccountDisabled` |
| 5 | Search locked-out users | `Search-ADAccount -LockedOut` |
| 6 | Unlock locked users | `Unlock-ADAccount` (after `Search-ADAccount -LockedOut`) |
| 7 | View user login details | `Get-ADDomainController -Filter` + `Get-EventLog -LogName Security -ComputerName <DC> -After <date>`, filter **Event ID 4624** (Type 2 = **local** logon, Type 10 = **remote** logon; inspect workstation + IP fields) |
| 8 | Disable inactive accounts | `(New-TimeSpan -Days 90)` + `Search-ADAccount -UsersOnly -AccountInactive -DateTime <d> \| Disable-ADAccount` |

## AD Security Best Practices
- **General**
  - Manage local admin passwords (**LAPS**); implement **RDP Restricted Admin mode**
  - Remove unsupported OSes; monitor scheduled tasks on sensitive systems (DCs)
  - Change default domain Administrator + **KRBTGT** password **every year** or when an AD admin leaves; store DSRM passwords securely + rotate
  - Use **SMB v2/v3+**; remove unnecessary trusts + enable **SID filtering**
  - Domain auth: **"Send NTLMv2 response only/refuse LM & NTLM"**; audit + restrict NTLM
  - **Block Internet access** for DCs, servers, admin systems; disable **NetBIOS over TCP/IP** + **LLMNR**
- **Protect Administrator Credentials**
  - No user/computer accounts in admin groups; admin accounts sensitive + **non-delegable**
  - Add admin accounts to **Protected Users** group; disable inactive admin accounts, remove from privileged groups
  - Restrict AD admin membership; custom delegation groups; **tiered administration** (mitigate credential-theft impact); logon only on approved admin workstations/servers; **time-based temporary group membership**
- **Protect Resources**
  - Segment network for admin/critical systems; deploy **IDS** inside the corporate network; network device + **OOB management** on a separate network
- **Protect Service Account Credentials**
  - Limit to same-security-level systems; implement **(Group) Managed Service Accounts**
  - **FGPP** (functional level ≥ 2008) for stronger service-account/admin passwords
  - Prevent interactive logon; disable inactive service accounts, remove from privileged groups
  - **WDigest** reg key `HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest` → **0**
- **Protect Workstations and Servers**
  - Patch quickly (esp. privilege-escalation vulns); deploy security back-port patches; workstation **whitelisting**; **EMET** application sandboxing
- **Protect Domain Controllers**
  - Run only AD-required software/services; restrict DC admin/logon rights; patch **before running DCPromo**; validate scheduled tasks & scripts
- **Logging**
  - Centralized logging (**SIEM**); user-behavioral analysis systems; **enhanced auditing**; **PowerShell module logging**; CMD process logging + forward logs to central log server










