---

type: moc
module: "09"
tags: [concept, mod/09]
topic: "Module 09 — Administrative Application Security"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights not stated in courseware (Exam 312-38: 4 h, 100 questions)."
  - "Some slide-figure text OCR-garbled at 200 dpi (software license screens); kept to verified text statements."
---
# Module 09 — Administrative Application Security

> [!abstract] Scope
> 4 LOs · 4 sections · courseware pp. 1215–1299. Procuring control of installed applications: application whitelisting + blacklisting (incl. Software Restriction Policies, AppLocker, Endpoint Central, PUA protection, Group Policy + registry blocking), application sandboxing (isolated execution, Windows Sandbox, Firejail, Sandboxie, WDAG), application patch management, and web application firewalls (WAFs — types, deployment options, URLScan, tools).

## Sections
| LO   | §   | Section                                              | Course pp. |
| ---- | --- | ---------------------------------------------------- | ---------- |
| LO01 | 9.1 | Implement Application Whitelisting and Blacklisting  | 1217       |
| LO02 | 9.2 | Implement Application Sandboxing                     | 1260       |
| LO03 | 9.3 | Implement Application Patch Management               | 1281       |
| LO04 | 9.4 | Implement Web Application Firewalls (WAFs)           | 1288       |

## Technical focus
- **Application security administration** (intro): protect users from harmful installs, no unauth `create/modify exe`, no unnecessary OS-resource access, prevent process spawning, regular patching, secure configuration (misconfiguration risk) — the 5 response practices = whitelisting, blacklisting, sandboxing, patch mgmt, application-level firewall (WAF).
- **LO01 whitelisting:** trust-centric allow-by-default-deny; entities (process, host, app+components, email, port) · 8 advantages (malware, zero-day, efficiency, visibility/attack-surface, bandwidth, lawsuits/licenses, no constant update, detection noise) + BYOD risk reduction · **blacklisting:** threat-centric allow-by-default; AV/spam/IDS-IPS; simple/low-maintenance; cons = not comprehensive, no zero-day, evadable · **SRP** (AD/Group Policy): 4 rules Path/Hash/Cert/Internet-Zone (only .msi; env-vars `%temp% %windir% %programfiles% %appdata% %systemroot% %userprofile%`; wildcards `?`/`*`; Disallowed ca be copied elsewhere; certificate not enabled by default; precedence) · AppLocker: exes, MSIs, DLLs; folder-path default; editions-limited; rule collections.
- **LO01 tools/implementation:** ManageEngine Endpoint Central (Block Executable = path/hash, two policies per exe; Prohibit Software = auto uninstall/net-install, pre-requisites: Local GPO enable + Unrestricted default + Enforcement All Users; exemptions, approvals, e-mail alerts, reports) · **Windows PUA protection** (`Set-MpPreference -PUAProtection 1`; Group Policy: WD AV → Configure detection → Block; audit mode) · **Group Policy blocking installs** (Turn off Windows Installer: Never / For non-managed only / Always; Don't run specified Windows applications) · **Registry DisallowRun** (HKCU Policies → Explorer DWORD + DisallowRun strings 1,2,3 = exe names; restart; Restrictions popup) · extra whitelist tools (Airlock Digital, Digital Guardian, Ivanti App Control, Delinea/PAM, Gatekeeper/macOS code-signing, Kaspersky Whitelist, PolicyPak, PowerBroker, Faronics Anti-Executable, McAfee App Control Deny modes).
- **LO02 sandboxing:** sealed-container isolation of untrusted/untested third-party code; limitation = not robust vs kernel-targeting malware; dedicated sandbox directory; **isolation-based vs rule-based** · examples: browsers (JS sandboxed), PDF/Office (macro), mobile apps (per-resource permission), **UAC** (low/medium/high integrity) · Chrome Strict-Origin-Isolation (`chrome://flags/#enable-site-per-process`, `--site-per-process`) · Firefox (`about:support` Sandbox; `about:config → security.sandbox.content.level`) · Acrobat Reader (Enhanced Security, Protected Mode, AppContainer, Protected View) · **Windows Sandbox** (needs virtualization; Windows Features) · **Firejail** (SUID + namespaces + seccomp-bpf; `firejail firefox/vlc/transmission-gtk/nginx start`; profiles) · **Sandboxie Plus** (Sophos) · tools table (BufferZone, Thinfinity, SHADE, Cameyo, Shadow Defender, Docker, Cuckoo, DeepArmor, Turbo.net) · **WDAG** for Edge (hardware RX: 4 cores VT-x/AMD-V + SLAT, 8GB, 5GB SSD, IOMMU, W10 Ent 1709+; enable Control Panel / `Enable-WindowsOptionalFeature -FeatureName Windows-Defender-ApplicationGuard`; standalone vs enterprise-managed: Network Isolation `*.microsoft.com` + neutral `bing.com`).
- **LO03 patch mgmt:** monitor+deploy new/missing patches; hackers exploit patch-disclosed vulns; flow `scan → central download → select → test → deploy`; features: third-party patching, network scan (VMs/cloud), patch-status dashboard (patched+malicious, unrecognized, unknown, compliance), test-before-deploy, groups to avoid congestion · **SolarWinds Patch Manager** (WSUS, SCCM, vuln mgmt, pre-tested packages, compliance; Adobe/Java/Firefox/Opera...) · tools: PDQ Deploy, LANDESK, Shavlik Protect, Kaseya, Flexera SVM, HP Touchpoint, Ivanti Patch/Endpoint Manager, Syxsense, Itarian.
- **LO04 WAF:** layer-7 protection where firewall/IDS-IPS fail; rule-based filter proxy ahead of web app · **3 types** (network/hardware, host/software, cloud-hosted) with pros/cons · **5 deployments** (reverse proxy, L2 bridge, out-of-band, server resident, internet-hosted/cloud CDN) · benefits (cookie encryption/signature, CSRF, URL-encryption anti-tampering, data-validation depth, PCI/HIPAA/GDPR) · limitations (not app-security replacement, can't read DB commands, partial session-fixation/anti-automation, false positives, not NGFW) · **URLScan** (IIS; SQLi/XSS; reject: verb/ext/suspicious encoding/non-ASCII/sequences/headers; HTTP 404) · WAF solutions: NGINX App Protect, **NAXSI positive-model**, WebKnight (ISAPI), Cloudflare, Shadow Daemon, Wallarm (API Top 10), NetScaler/Citrix, AppWall (Slowloris/brute-force), Barracuda, Qualys, FortiWeb.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**; blueprint weights not in courseware → `exam_weight: unknown`.
- Strong question sources: whitelist vs blacklist philosophy (trust/threat-centric; deny-by-default vs allow-by-default) · whitelisting advantage that beats AV (no constant updates; zero-day) · SRP 4 rules + points (Internet zone = .msi only; certificate = not by default; hash rule by file content; path = moves break rule) · AppLocker file types + editions · Endpoint Central path/hash + two policies + prerequisites · PUA command `Set-MpPreference` · Windows Installer options (Never/For non-managed only/Always) · DisallowRun registry steps · sandbox isolation vs rule-based + kernel-malware limitation · browser sandbox (Chrome Strict-Origin / Firefox `security.sandbox.content.level`) · Windows Sandbox virtualization prerequisite · Firejail (SUID, namespaces, seccomp-bpf) · WDAG (Edge, SLAT, `Enable-WindowsOptionalFeature`, standalone vs enterprise Trusted/Neutral domains *.microsoft.com / bing.com) · patch flow + dashboard items · SolarWinds Patch Manager (WSUS, SCCM) · WAF 3 types + 5 deployments · WAF benefits/limits (CSRF, cookie protection, can't read DB commands) · URLScan reject criteria · NAXSI positive-model.
- Answers: Q042 (LO01) · Q043 (LO02) · Q044 (LO03) · Q045 (LO04) as drafted below.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-09")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/09-application-security-map.canvas|Application Security Map]]
- Flows to visualize: app sec admin responsibilities → whitelist vs blacklist → implementation (SRP/AppLocker/Endpoint Central → PUA → GP/registry) → sandbox (isolation vs rule) to tools (Windows Sandbox/Firejail/Sandboxie) → WDAG (managed modes) → patch mgmt flow + tools → WAF types → deployment options → URLScan.

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-05]] (Windows: patch mgmt wuauserv, UAC) · [[MOC-Module-02]] (policies + compliance: PCI/HIPAA/GDPR) · [[MOC-Module-03]] (IPS/IDS + UTM; WAF vs NGFW contrast) · [[MOC-Module-06]] (Linux file/SELinux — Firejail namespace overlay) · [[MOC-Module-01]] (malware/zero-day/trojans).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- A few in-slide vendor screens had OCR noise (license/SolarWinds tables); content kept to legible terms, no invented numbers.

## Quick review
Courseware's 5 application-security admin practices?
?
Application whitelisting · blacklisting · sandboxing · patch management · application-level firewall (WAF).

Whitelisting vs blacklisting philosophy?
?
Whitelist = trust-centric allow-only-approved/deny-by-default; blacklist = threat-centric allow-by-default-denies-known-bad.

Best whitelisting exam facts?
?
SRP = 4 rules (path/hash/cert/internet-zone .msi); AppLocker = exe/msi/dll; PUA = Set-MpPreference -PUAProtection 1; DisallowRun registry; Endpoint Central path+hash.

Sandbox top exam items?
?
Isolation vs rule-based; fails vs kernel malware; UAC integrity levels (low/med/high); Firefox security.sandbox.content.level; Windows Sandbox needs virtualization; Firejail SUID+seccomp-bpf; WDAG Edge SLAT + Enable-WindowsOptionalFeature.

WAF top exam items?
?
Layer 7; 3 types (network/host/cloud); 5 deployments (reverse proxy/L2 bridge/out-of-band/server-resident/cloud); URLScan reject criteria; NAXSI positive-model; can't read DB commands; WS need managed session for anti-automation.
