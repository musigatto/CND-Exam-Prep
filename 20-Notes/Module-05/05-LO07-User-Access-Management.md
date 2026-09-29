---
type: note
module: "05"
lo: "07"
tags: [concept, policy, command, mod/05]
topic: "User Access Management"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# User Access Management (§5.7)

Controls how Windows restricts users/groups → resources: file/folder access · system changes · Control Panel · Command Prompt · admin accounts.

## Restricting Access to Files and Folders
- Assign appropriate permission to individual users/groups on a specific file/folder
- **NTFS permissions** govern access to files locally **and** files in shared folders over the network (shared-folder perms apply per NTFS rules)

### NTFS file permissions
| Level | Grants |
|---|---|
| **Full Control** | All permissions; complete access to any file even if permission denied |
| **Modify** | Read, write, execute, traverse |
| **Read & Execute** | Move through each directory, read all files |
| **Read** | List folders, read files, attributes, permissions |
| **Write** | Create files, write data, create folders, set attributes |

### NTFS folder permissions
| Level | Grants |
|---|---|
| **Full Control** | Complete access to folders |
| **Modify** | Read, write, execute, traverse |
| **Read & Execute** | List folders, read files, attributes, permissions |
| **List Folder Contents** | Access folders + subfolders (only when **inherited by folders, not files**; Read & Execute appears for files + folders) |
| **Read** | List folders, read files, attributes, permissions |
| **Write** | Create files, write data, create folders, set attributes |

- **NTFS** supports backup/restore and per-file/folder permissions; **FAT** — cannot set permissions on individual files/folders
- Special permissions: Properties → Security tab → **Advanced → Add** → Permission Entry
- PowerShell: `$acl = Get-Acl C:\Demo; $r = New-Object System.Security.AccessControl.FileSystemAccessRule("Bob","ReadPermissions","Allow"); $acl.SetAccessRule($r); $acl | Set-Acl C:\Demo`

## Prevent Unauthorized System Changes (UAC)
- **UAC** = key access-control enforcement; keeps applications at **standard user privileges until an administrator authorizes elevation** — an admin-holding account still does not grant its apps admin rights automatically
- **Admin account**: ensures changes accepted by the administrator · blocks malware from modifying security settings or **disabling antivirus** · users cannot access/modify other users' sensitive info on shared computers
- **Non-admin account**: restricts running any application without administrator permission; **Yes/No prompt**; prevents unauthorized app/program execution
- Adjust: `Control Panel → User Accounts → Change User Account Control Settings` (slider): **Always notify** (dims screen, prompts for software install/system changes) … **Never notify** (for all practical purposes **turns UAC off**)
- PowerShell enable: DWORD **`EnableUA` = 1** @ `HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System`

## Disable Anonymous Security Identifier (SID) Enumeration
- Every SID ends in a **relative identifier (RID)**; RID is **predetermined for some accounts** → attacker who reads the SID list swaps in an administrative RID and gains **administrator privileges**
- Sleep well: GPO Local Policies → Security Options → **`Network access: Do not allow anonymous enumeration of SAM accounts and shares`** → **Enabled** (if left disabled, insiders identify users/groups by searching SIDs)

## Moderating Access to Control Panel
- Control Panel exposes disk manager, credential manager, devices/printers, network+sharing, programs, **Administrative Tools** → alteration compromises the system
- GPO: **User Configuration → Administrative Templates → Control Panel → `Prohibit access to Control Panel and PC settings`** → Enabled
- Blocks **Control.exe** + **SystemSettings.exe**; strips Control Panel from Start screen + File Explorer; strips PC settings from Start screen, Settings charm, Account picture, Search results

## Control Access to Command Prompt
- CMD exposes drive info, paths, ASCII codes, Windows version, **registry files**; inadvertent modification → full OS breakdown → reinstall
- GPO: **User Configuration → Administrative Templates → System → `Prevent access to the command prompt`** → Enabled
- Stops interactive **Cmd.exe** and also governs whether **batch files (.cmd/.bat)** can run
- Caution: don't block batch files on machines relying on logon/logoff/startup/shutdown scripts or on **Remote Desktop Services** users

## Administrative Access Management — Just Enough Administration (JEA)
- Limits the **set of cmdlets / admin privileges** granted to administrator, user, or service accounts (e.g., a DNS needs only cache-clearing cmdlets, not every PS cmdlet — trimming kills a big attack vector)
- Two configuration files:
  - **PS role capability file** — determines **privileges of specific accounts**; create `New-PsRoleCapabilityFile -Path MyFirstJEARole.psrc`; list `VisibleCmdlets` (e.g., `'Restart-Computer'`, `'Get-NetIPAddress'`) → user can only see/use those
  - **PS session configuration file** — determines **who may perform** the tasks in the role capability file; create `New-PsSessionConfigurationFile -SessionType RestrictedRemoteServer -Path MyJEAEndpoint.pssc`
- `RestrictedRemoteServer` mode default cmdlets: `Select-Object` (select) · `Get-Command` (gcm) · `Get-Help` · `Get-FormatData` · `Measure-Object` (measure) · `Exit-PsSession` (exsn/exit) · `Out-Default` · `Clear-Host` (cls/clear)
- JEA sessions run under a **virtual account created per session** and removed when the session ends → credentials never saved on the machine → reduced attack vectors

## Cards
Q:: NTFS permission unique to folders (not files)?
A:: List Folder Contents (only when inherited by folders; Read & Execute applies to files too).
#flashcard
Q:: FAT vs NTFS file permissions?
A:: NTFS = per-file/folder permissions + backup/restore; FAT = no per-file/folder permissions.
#flashcard
Q:: UAC core behavior?
A:: Apps run at standard-user privileges until an administrator authorizes elevation; prevents malware from changing security settings/AV.
#flashcard
Q:: What does a SID's RID enable for attackers?
A:: RIDs are predetermined for some accounts — attacker replaces RID with an administrative account's to get admin privileges (block via 'Network access: Do not allow anonymous enumeration of SAM accounts and shares').
#flashcard
Q:: Policy to block Control Panel?
A:: User Configuration → Admin Templates → Control Panel → 'Prohibit access to Control Panel and PC settings' (blocks Control.exe/SystemSettings.exe).
#flashcard
Q:: Policy to block Command Prompt?
A:: User Configuration → Admin Templates → System → 'Prevent access to the command prompt'; also governs .cmd/.bat batch files.
#flashcard
Q:: JEA — what does it limit?
A:: The cmdlets/admin privileges of an account; needs a PS role capability file (visible cmdlets) + PS session configuration file (who may run them); uses per-session virtual account.
#flashcard