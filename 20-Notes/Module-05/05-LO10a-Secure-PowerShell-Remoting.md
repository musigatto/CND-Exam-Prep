---

type: note
module: "05"
lo: "10"
tags: [concept, process, tool, command, protocol, mod/05]
topic: "Secure PowerShell Remoting"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Secure PowerShell Remoting (§5.10)

PS Remoting gives access to **almost everything** → prime attack target. Harden endpoints, logging, language mode, execution policy.

## PS Remoting Basics
- PS Remoting uses **WSMAN** protocol, managed by **Windows Remote Management (WinRM)**
- Ports: **5985** (HTTP) · **5986** (HTTPS)
- Traffic stays **encrypted even over HTTP** (WinRM listener on 5985)
- When enabled, PS configures **four endpoints** (session configurations): `microsoft.powershell`, `microsoft.powershell.workflow`, `microsoft.powershell32`, `microsoft.windows.servermanagerworkflows`
- `Get-PsSessionConfiguration` lists all; **Permission** property = users+rights per endpoint; default: **system administrators + remote management users**
- Reduce risk: create **custom (constrained) endpoints** with restricted permissions

## PS Remoting Security Per Environment
| Environment | Mechanism |
|---|---|
| Local domain | HTTP WinRM listener (5985); traffic encrypted (like HTTPS/5986) |
| AD domain | **Kerberos** provides authentication trust — device verify |
| Workgroups | Enable **SSL**; add workgroups to **trusted hosts**; HTTPS with certificates + asymmetric encryption → avoids **MITM** |

## Defensive Techniques
- **Module/pipeline logging**: records all running cmdlets + parameters used
- **System transcripts**: show attacker's commands + input/output on the system

## Security Scripts
| Script | Function |
|---|---|
| **POSH-Sysmon** | Deploy/configure Sysmon fleet-wide (PS 3.0+; deploy Sysmon first) |
| **Enable Client Rules Forwarding Block** | Hunt/block abused **Office 365** email forwarding rules |
| **MicroBurst** | PS toolkit defending **Azure** cloud services — e.g. `Invoke-EnumerateAzureSubDomains -Base test12345678` |
| **SecurityPolicyDsc** | Configures local security policies via DSC (per-system or whole environment) |
| **Device Guard / Application Guard** | `DG_Readiness.ps1 -[Capable/Ready/Enable/Disable/Clear] -[DG/CG/HVCI]` — readiness check + enable (Driver Verifier run for compatibility) |

## Enable PS Logging (PS 5.0)
| Logging type | Records | Enable via GPO | Registry path |
|---|---|---|---|
| **Module logging** | Pipeline execution details (variable init, command invocations) | `Turn on Module Logging` → Enabled, Module Names `*` = all modules | `HKLM\SOFTWARE\Wow6432Node\Policies\Microsoft\Windows\PowerShell\ModuleLogging` → `EnableModuleLogging`, `ModuleNames` |
| **Transcript logging** | Unique record of **every PS session** | `Turn on PowerShell Transcription` → Enabled | `HKLM:\Software\Policies\Microsoft\Windows\PowerShell\Transcription` |
| **Script block logging** | Blocks of code **as executed** (de-obfuscation) | `Turn on PowerShell Script Block Logging` → Enabled | `HKLM\SOFTWARE\Wow6432Node\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging` → `EnableScriptBlockLogging` = 1 |

## Disable PS 2.0
- PS 2.0 = **security risk**, used by attackers to execute malicious code
- Check: `Get-WindowsOptionalFeature -Online -FeatureName MicrosoftWindowsPowerShellv2Root`
- Disable: `Disable-WindowsOptionalFeature -Online -FeatureName MicrosoftWindowsPowerShellv2Root` (admin PS)

## Enforce Script Signing (Execution Policy)
- Windows **restricts script execution by default**; verify with `Get-ExecutionPolicy`
- Policies: **Restricted** (no scripts) · **AllSigned** (only signed by trusted publisher) · **RemoteSigned** (downloads must be signed) · **Unrestricted** (all)
- **Script execution policy can be bypassed** — enforce via **Group Policy** (`Turn on Script Execution`: Allow only signed / Allow local + remote signed / Allow all); **Computer Configuration takes precedence** over User Configuration

## Constrained Language Mode
- **FullLanguageMode**: loads all COM objects/libraries/classes into the session → attacker vector
- **ConstrainedLanguageMode**: limits/blocks **COM objects, unapproved .NET types, XAML workflows, PowerShell classes**
- Determine: `$ExecutionContext.SessionState.LanguageMode` (`FullLanguage` / `ConstrainedLanguage`)
- Enforce methods:
  1. **AppLocker script rules in Allow Mode** (best under least privilege) — **Script Rules: Default Rule All Scripts / Program Files / Windows folder**
  2. **Device Guard UMCI** — *most preferred*; cannot be easily disabled even by admins

### Deploy Device Guard (UMCI)
1. `New-CIPolicy -FilePath .\policywin.xml -Level Publisher -UserPEs -ScanPath 'C:\windows\system32'` (scan reference device, user-mode PEs)
2. `New-CIPolicy -FilePath .\policyprogs.xml -Level Publisher -UserPEs -ScanPath 'C:\program files' -NoScript`
3. `Merge-CIPolicy -PolicyPaths .\policywin.xml, .\policyprogs.xml -OutputFilePath .\policyfinal.xml`
4. `Set-RuleOption -Option 3 -FilePath .\policyfinal.xml -Delete` (kill audit-mode rule); `Set-RuleOption` options **9** (Advanced Boot Options) + **10** (Boot Audit on Failure) before production
5. `ConvertFrom-CIPolicy .\policyfinal.xml .\DeviceGuardPolicy.bin`
6. GPO: **Computer Configuration → Administrative Templates → System → Device Guard → "Deploy Code Integrity Policy"** → Enabled → point to `.bin` (UNC or local; LOCAL SYSTEM must access it) → reboot
7. Test: installing a non-whitelisted publisher's app (e.g. Google Chrome) is **blocked**

## PS Remoting Security Recommendations
- Turn on **transcription logging** → logs written to a **central file share**
- **Lock down accounts** with privileges to remove those logs
- **Script block logging** on → evaluate damage
- **Module logging** on (caution: **enormous event-log data**)
- Enable **certificate infrastructure** for the domain; install **SSL certificates** on all domain systems; **disable the HTTP port** after SSL certs deployed
- Updated PS versions on every system
- Firewall: open **only the two PS Remoting ports** (one only if SSL)
- **Remove local administrators** on PCs/servers aggressively








