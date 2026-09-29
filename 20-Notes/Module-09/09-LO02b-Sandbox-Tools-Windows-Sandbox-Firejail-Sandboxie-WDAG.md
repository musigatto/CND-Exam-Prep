---
type: note
module: "09"
lo: "02"
tags: [tool, command, process, mod/09]
topic: "Sandbox Tools — Windows Sandbox, Firejail, Sandboxie, WDAG, Others"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Application Sandbox Tools (§9.2b)

## Windows Sandbox
- Isolated, temporary desktop environment to run software without affecting host; safely download + install + test risky executables
- **PC needs virtualization enabled** (Task Manager → Performance → Virtualization: Enabled); enable feature via **Windows Features → Windows Sandbox**; restart; run as admin
- Built-in apps only (OneDrive, Mail, Edge, Microsoft Store, Photos); bring other programs via Edge download or drag-and-drop; **close (not shutdown) sandbox to apply changes**

## Linux: Firejail
- **SUID program** restricting untrusted app environment using **Linux namespaces + seccomp-bpf**; process + descendants get private view of network stack, process table, mount table
- Sandboxes servers, graphical apps, login sessions; includes security profiles (Firefox, Chromium, VLC, Transmission)
- Usage: `$ firejail firefox` · `$ firejail transmission-gtk` · `$ firejail vlc` · `$ sudo firejail /etc/init.d/nginx start`
- Works with SELinux/AppArmor; integrated with Linux Control Groups (in 7.1x Supplemental)

## Sandboxie Plus (Sophos)
- Keeps browser isolated; blocks malware, viruses, ransomware, zero-day; prevents websites modifying system files/folders
- Usage: Sandbox → Default Box → **Run Sandboxed → Run Web Browser** (or Run Any Program)

## Additional Sandbox Tools
| Tool | Role |
|---|---|
| BufferZone | virtual zone; everything passing through becomes read-only (blocks web malware) |
| Thinfinity Workspace | remote desktop access + app delivery with role-based permissions |
| SHADE Sandbox | beginner-friendly drag-drop sandbox; isolates history, temp files, cookies, registry, system files; downloads → Virtual Downloads folder |
| Cameyo | app streaming from browser; eliminates VPN/firewall/server-port needs |
| Shadow Defender | virtualizes system + other drives; **reboot discards changes**; Commit Now saves |
| Docker | containerization; isolates apps from underlying infrastructure |
| Cuckoo Sandbox | open-source automated malware analysis; behavior analysis |
| DeepArmor | AI/ML threat mitigation (ransomware, malware, fileless, in-memory attacks) |
| Turbo.net | instant access to web + native Windows apps; custom workspaces |

## Windows Defender Application Guard (WDAG) — Edge
- Isolates **Microsoft Edge**; blocks websites from local storage, memory, installed apps, corporate network endpoints
- **Prerequisites (Table 9.1):** 64-bit, ≥4 cores, CPU virtualization extensions (VT-x / AMD-V) + **SLAT**, ≥8 GB RAM, 5 GB free SSD, IOMMU support; Win10 Ent v1709+; Win10 Pro v1803+ (non-managed only); Edge + IE
- **Enable:** Control Panel → Windows Features → Windows Defender Application Guard; or PowerShell (enterprise-managed): `Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard` → restart
- **Standalone mode:** desktop user manages; New Edge window → **New Application Guard window**; untrusted sites show WDAG visual cues
- **Enterprise-managed mode** (Group Policy, Intune/SCCM/MDM): Network Isolation policy — Enterprise resource domains hosted in the cloud → `*.microsoft.com` (enterprise cloud resources); Domains categorized as both work and personal → neutral resources `bing.com`; enable **Turn on Windows Defender Application Guard in Enterprise Mode** (Option: Edge ONLY / Edge AND Office / isolated Windows environments); trusted URLs open on host, untrusted auto-redirect to hardware-isolated environment

## Cards
Q:: Windows Sandbox prerequisite?
A:: Virtualization enabled (Task Manager → Virtualization: Enabled); Windows Sandbox feature via Windows Features.
#flashcard
Q:: Firejail mechanism + examples?
A:: SUID + Linux namespaces + seccomp-bpf; private network stack/process table/mount table; `firejail firefox`, `firejail vlc`.
#flashcard
Q:: Sandboxie (Sophos) isolation?
A:: Blocks malware, viruses, ransomware, zero-day; stops websites from modifying system files/folders.
#flashcard
Q:: Shadow Defender behavior?
A:: Virtualizes drives; rebooting discards changes; Commit Now persists.
#flashcard
Q:: WDAG isolates?
A:: Microsoft Edge — blocks access to local storage, memory, installed apps, corporate network endpoints.
#flashcard
Q:: WDAG enable command?
A:: Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard.
#flashcard
Q:: WDAG enterprise-mode trusted/neutral config?
A:: *.microsoft.com (enterprise cloud), bing.com (neutral), then enable Application Guard in Enterprise Mode.
#flashcard