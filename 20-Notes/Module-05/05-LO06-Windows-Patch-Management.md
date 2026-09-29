---
type: note
module: "05"
lo: "06"
tags: [concept, command, tool, mod/05]
topic: "Windows Patch Management"
exam_weight: unknown
status: done
unresolved: ["Registry auto-update method: NoAutoUpdate value semantics ambiguous in OCR — screenshot shows 0x00000001"]
---
[[MOC-Module-05]]

# Windows Patch Management (§5.6)

Effective patch management is essential for **eradicating security weaknesses**; keeps appropriate and updated patches installed on the system.

- **Patch** = small program applying a **fix to a specific type of vulnerability**
- **Service pack** = fixes vulnerabilities **+ functionality improvements**
- **Version upgrade** = fixes vulnerabilities **+ improved security features**
- Patch-management activities:
  - Choosing, **verifying, testing, and applying** patches
  - Updating previous patch versions → current ones
  - Recording **repositories/depots** of patches for easy selection
  - Assigning and **deploying** applied patches
- Use patch-management tools to **identify missing patches** and install them

## Enable Automatic Updates
Protects against latest known vulnerabilities/bugs; automatic updates check for important updates and install automatically. Third-party Windows-update tools exist for remote-desktop patch management.

- **Method 1 — Service Manager**: `Services.msc` → **Windows Update** → Startup type = **Automatic**
- **Method 2 — Registry**: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU` → DWORD **`NoAutoUpdate`** (create `Au` key under `...\WindowsUpdate` if absent)
- **Method 3 — Command**: `sc config wuauserv start= auto` (CMD / `sc.exe` in PowerShell)

## Disable Force System Restarts
System notifies user of an update; if the user repeatedly ignores/snoozes notifications, Windows **force-restarts** to complete installation → unsaved work can be **lost**.

- **Method 1 — GPO**: Computer Configuration → Administrative Templates → **Windows Component → Windows Update → Legacy Policies** → **"No auto-restart with logged on users for scheduled automatic updates installations"** → **Enabled**
  - Enabled → Auto Update **waits for a logged-on user** to restart (notifies user); computer won't auto-restart during scheduled install
  - Disabled/Not Configured → notifies user the computer will **auto-restart in 5 minutes**
- **Method 2 — Registry**: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Windows Update\AU` → DWORD **`NoAutoRebootWithLoggedOnUser`** = 1 (hex)
- **Method 3 — CMD**: run `gpupdate` (applies policy updates)

## Remote Patch Management Using Third-Party Tools
Remote patch management = **planning, deciding, prioritizing updates** to OS, software, devices across the network; a single platform can update many systems.

| Tool | Notable features |
|---|---|
| BatchPatch (batchpatch.com) | No install; offline Windows updates, update-history retrieval, remote script execution, job queues, multi-host sequencing, task scheduler |
| LANDesk Patch Manager (landesk.com) | Subscription service; single-console; quick per-vulnerability patch ID/download, remediation, email alerts |
| SolarWinds Patch Manager (solarwinds.com) | 3rd-party patching across thousands of servers/workstations; **extends Microsoft WSUS or SCCM**; web UI, patch-compliance reports |
| PRTG Network Monitor (paessler.com) | Records patching, **notifies about flawed patches**; real-time patch status, Windows-update sensor |
| ManageEngine Patch Manager Plus (manageengine.com) | Endpoint scan for missing patches, test-before-deploy, automated deployment; cross-platform + 3rd-party apps; feature-update deployment |
| GFI LanGuard (gfi.com) | Multi-OS + 3rd-party app/browser patching; tracks latest vulnerabilities/missing updates; **detects vulnerabilities before an attacker does** |
| SysAid Patch Management (sysaid.com) | Keeps systems/servers up to date; automated, scalable; integrates with SysAid Help Desk + ITSM |

Also listed: Itarian Patch Management · Automox · Atera · Kaseya VSA · HEAT PatchLink · Ivanti Windows Patch · Comodo ONE · Quest KACE · Symantec Patch Management Solution.

## Cards
Q:: Patch vs service pack vs version upgrade?
A:: Patch = fix for one vulnerability; SP = fixes + functionality; upgrade = fixes + improved security features.
#flashcard
Q:: Enable automatic updates (command)?
A:: `sc config wuauserv start= auto`; or Services.msc → Windows Update → Automatic.
#flashcard
Q:: Auto-update registry key?
A:: `HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU` → DWORD NoAutoUpdate.
#flashcard
Q:: Prevent force restarts after updates (registry)?
A:: `HKLM\SOFTWARE\Microsoft\Windows\Windows Update\AU` → NoAutoRebootWithLoggedOnUser = 1; GPO: 'No auto-restart with logged on users…'.
#flashcard
Q:: Which tool extends WSUS/SCCM?
A:: SolarWinds Patch Manager.
#flashcard
Q:: Tool that detects vulnerabilities before an attacker does?
A:: GFI LanGuard.
#flashcard