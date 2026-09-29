---
type: note
module: "05"
lo: "04"
tags: [concept, tool, command, mod/05]
topic: "Windows Security Baseline Configurations"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows Security Baseline Configurations (§5.4)

**Windows security baseline** = group of **Microsoft-recommended configuration settings** for securing Windows. Ensures user + device configuration settings are **compliant** with the baseline; defines steps for identifying needed security updates and configuration changes. Microsoft **re-evaluates older settings** against contemporary threats and adds settings for newly discovered vulnerabilities and misconfigurations.

## Security Compliance Toolkit (SCT)
- Set of tools to **download, analyze, test, edit, and store** Microsoft-recommended security configuration baselines; replaces **Security Compliance Manager (SCM)** (was hard to manage); tailored for Windows admins
- Ships baselines for: **Windows 11 · Windows 10 · Windows Server editions (2016, 2012 R2, 2019) · Office 365 ProPlus**
- Context: fresh Windows install is not secure until configured; **GPOs preset configs** so the OS is as secure as possible — tweakable per requirement, used to lock down computers or servers (file server, IIS, …)

### SCT tools
- **Policy Analyzer** — treats **GPOs as a single unit**; flags settings **duplicated** across a GPO or set to **conflicting values**; compares system baselines vs Windows recommended baselines; takes a **snapshot** of a security configuration → later compared to the recommended baseline to note changes made after implementation
- **LGPO.exe** (Local Group Policy Object) — command-line utility automating **local group policy** management; verify effects of GP settings; manages **nondomain-joined** systems. Functions:
  - Import/apply settings from `Registry.pol` files, security templates, advanced auditing backup files, formatted LGPO text files
  - Export local policy to a **GPO backup**
  - Export `Registry.pol` to editable LGPO text; build a `Registry.pol` from LGPO text
- **SetObjectSecurity.exe** — set the **security descriptor** for any Windows securable object: files, directories, registry keys, event logs, services, SMB shares
- **GPO2PolicyRules** — command-line, bundled with Policy Analyzer download; auto-converts **GPO backup files → Policy Analyzer/PolicyRules files**, skipping the GUI

### Baseline sheet / Policy Viewer (Excel)
- Policy Setting Name · Policy Path · Supported On (e.g., Control Panel restriction GPOs: enable/hide Control Panel items, `HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\DisallowCpl`, `...\NoControlPanel`, allow classic Control Panel)
- Security Template rows show privilege rights + **CONFLICT** markers where a setting diverges from the recommended baseline
  - Privilege Rights: `SeBackupPrivilege`, `SeDenyNetworkLogonRight`, `SeEnableDelegationPrivilege`, `SeInteractiveLogonRight`, `SeLoadDriverPrivilege`, `SeNetworkLogonRight`, `SeRemoteShutdownPrivilege`, `SeRestorePrivilege`
  - System Access: `EnableAdminAccount`, `LockoutBadCount`, `MaximumPasswordAge` (baseline 42 vs local 60 …), `MinimumPasswordLength`

## Cards
Q:: What is a Windows security baseline?
A:: Group of Microsoft-recommended configuration settings; ensures user+device config compliance, updated for new vulnerabilities/misconfigurations.
#flashcard
Q:: What replaced Security Compliance Manager (SCM)?
A:: Security Compliance Toolkit (SCT).
#flashcard
Q:: SCT core tools?
A:: Policy Analyzer · LGPO.exe · SetObjectSecurity.exe · GPO2PolicyRules.
#flashcard
Q:: Policy Analyzer function?
A:: Treats GPOs as one unit, finds duplicate/conflicting settings, compares system vs recommended baseline, takes config snapshots.
#flashcard
Q:: LGPO.exe use?
A:: Command-line local group policy automation; import/export Registry.pol, security templates, GPO backups; manages nondomain-joined systems.
#flashcard
Q:: SetObjectSecurity.exe use?
A:: Set security descriptors on securable objects (files, dirs, registry keys, event logs, services, SMB shares).
#flashcard