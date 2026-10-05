---

type: note
module: "09"
lo: "01"
tags: [tool, command, policy, process, mod/09]
topic: "Application Blacklisting Tools and Blocking Methods"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Blacklisting Implementation: Tools & Blocking Methods (§9.1b)

## ManageEngine Endpoint Central (Blacklisting)
- Restricts usage of **blacklisted applications + portable executables** (usable without install)
- Two features:
### Block Executable Feature
- Block apps/executables for all computers or specific users/computers
- Two block methods: **path rule** (block all versions by exe name + extension) · **hash value** (blocks even if renamed)
- Two policies allowed per executable (one path, one hash); **system restart** needed for effect
- **Prerequisites on target**: enable Local Group Policy (`gpedit.msc` → Turn Off Local GPO Processing → **Not Configured**); disable Computer Configuration settings; set default security level **Unrestricted**; apply SRP to **all users** (Enforcement → All Users)
### Prohibit Software Feature
- Automatic **detection and removal** of prohibited apps
- Add software to prohibited list (a Software Group blacklists the whole group) · **auto-uninstall** (max count per refresh, notify user, wait window) · exempt computers via Exclusions · approve user requests · e-mail alerts · dedicated reports (Prohibited Software links)
- Auto-uninstall available for `.msi` and `.exe` (needs silent switches); pre-fill or manual uninstall command

## Windows PUA Protection
- **PUPs/PUAs** = programs downloaded from trusted source but not used often → adware, downloaders, aggressive monetizing software (malware risk, perf hit)
- Two config approaches:
  - **Group Policy:** Local Group Policy Editor → Computer Configuration\Administrative Templates\Windows Components\Windows Defender Antivirus → **Configure detection for potentially unwanted applications** → **Enabled + Block** (Supported: Windows 10 v1607 / Server 2016+)
  - **PowerShell:** `Set-MpPreference -PUAProtection 1` (admin)

## Blocking Software Installation by Users (Group Policy)
- **Windows Installer (msiexec.exe)** = engine for install/maintenance/removal of programs
- **Turn off Windows Installer** policy (Computer Configuration → Administrative Templates → Windows Components → Windows Installer) → **Enabled** + Disable Windows Installer = **Always** (options: Never – users install/upgrade; For non-managed apps only – only admin-assigned/published apps; Always – disables)
- **Block specific app** via User Configuration → Administrative Templates → System → **Don't run specified Windows applications** (Enter exe path): only stops programs started from **Explorer**; task manager etc. unaffected

## Blocking Apps via Registry (DisallowRun)
1. `regedit` → `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies`
2. Create key **Explorer** → DWORD **DisallowRun** = 1
3. Create key **DisallowRun** under Explorer → **String values** `1`, `2`, `3`... each = exe name (e.g., notepad.exe)
4. Restart; blocked app shows "Restrictions" popup
- Note: blocks only Explorer-launched apps (same limitation as Don't run specified Windows applications)

## Additional Whitelisting / Application Control Tools
| Tool | Vendor / Role |
|---|---|
| Airlock Digital | paid, ASD-recognized whitelisting |
| Digital Guardian | easy deploy; ideal for POS + ICS |
| Ivanti Application Control | dynamic whitelisting + privilege mgmt (powered by AppSense) |
| Delinea | PAM; Server PAM, passwordless, JIT privilege elevation |
| Gatekeeper | Apple macOS code-signing whitelisting |
| Kaspersky Whitelist | local whitelist DB boosts AV performance |
| PolicyPak | lockdown of Firefox/Java/Flash/IE/Adobe; Group/Cloud/MDM editions |
| PowerBroker (BeyondTrust) | Win/Linux/Mac; default-deny + least privilege |
| Faronics Anti-Executable | AI/ML-assisted whitelisting for "dirty environments" |
| McAfee Application Control | **default-Deny, Detect-and-Deny, Verify-and-Deny**; well-known/unknown/known-bad classification |






