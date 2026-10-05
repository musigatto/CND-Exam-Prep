---

type: note
module: "05"
lo: "09"
tags: [concept, process, tool, command, protocol, crypto, mod/05]
topic: "Windows System Integrity and Integrity Checking"
exam_weight: unknown
status: done
unresolved: ["System Management Mode: two defense methods listed, but OCR only captured the second (Supervisor SMI handler) in full"]
---
[[MOC-Module-05]]

# Windows System Integrity and Integrity Checking (§5.9)

Integrity = security + trustworthiness of the Windows OS. Harden by restricting apps/processes/ports, relying on hardware/software integrity features, and running integrity-checking tools to stop unauthorized access to systems and files.

## Avoid Unauthorized Program Access
- **Manage app permissions**: Settings → **Privacy & security → App permissions** — grant/deny per-app capabilities (app permissions per app; manage for multiple apps centrally)

## Close Unwanted Processes and Ports
- **Method 1 — Task Manager**: select process → **End Task**; also **Open File Location** / **Go to service(s)** / Create dump file / Set priority options
- **Method 2 — close an open port via Windows Defender Firewall**: Start → Control Panel → **Windows Defender Firewall → Advanced settings → Inbound Rules → New Rule → Port** → TCP or UDP → **Specific local ports** (e.g. `80`) → **Block the connection** → apply to Domain/Private/Public profiles → name the rule

## Windows System Integrity Key Features
| Feature | Function |
|---|---|
| **User Account Control (UAC)** | Prevents unintentional/unauthorized configuration changes; prompts before changes; approved → runs with highest available privilege, denied → app prevented from running |
| **Code Signing** | Microsoft digitally signs programs/apps/executables with a code-signing certificate; invalid/missing signature → **Windows prevents the file from running**; valid cert clears the **SmartScreen "Unknown Publisher"** warning |
| **Driver Signing** | Vendors certify drivers with Microsoft → signed by **Windows Hardware Quality Labs (WHQL)** → distributed via Windows Update; **unsigned drivers do not install** (blocks malicious kernel drivers) |
| **TPM** | Hardware security feature; verifies system integrity at startup; secures Windows boot |

## Trusted Platform Module (TPM)
- Checks: Start → Settings → **Update & Security → Windows Security → Device security → Security processor**
- **TPM + Secure Boot** ensure boot-process integrity; **BitLocker** (built-in encryption) uses TPM to protect the system drive; **Device Guard + Credential Guard** also use TPM
- Enable **Secure Boot**: BIOS/UEFI at boot (**F2 / Del / Esc** keys); confirm TPM chip via BIOS/UEFI or **Device Manager**
- Key features: **secure storage of keys** (hardware-based secure enclave, resistant to software attacks) · **secure boot and chain of trust** (PCRs measure boot components; tampering breaks the chain of trust) · **platform measurements** (PCRs record component measurements per boot stage) · **remote attestation** (cryptographic "quote" of PCR values sent to a remote verifier)

## Windows Resource Protection (WRP)
- Formerly **Windows File Protection (WFP)**; safeguards critical system files + registry settings from alteration/corruption/replacement by unauthorized software; **auto-repairs** by restoring original files; integrated with **Windows Update**
- Protected resources changeable only via **Supported Resource Replacement Mechanisms** with the **Windows Modules Installer service**
- Failure modes when an app hits WRP: access-denied error + install abort; protected reg-key add/remove/value change denied; apps writing into protected key/folder/file fail

## System Management Mode (SMM) Protection
- **SMM**: special-purpose CPU mode (x86/x86-64) for low-level tasks — hardware configuration, thermal monitoring, power management; triggered by runtime **non-maskable interrupt (SMI)**; runs at **highest privilege and is invisible to the OS** → prime attack target
- SMM protection restricts SMM entry to **trusted, controlled means** and isolates the SMM environment from OS/user apps (block unauthorized code execution); defense methods include memory **tampering prevention** and **Supervisor SMI handler** (hardware feature monitoring SMM so it cannot access unauthorized address space)

## Windows System Integrity Checking Tools
| Tool | Role | Key commands |
|---|---|---|
| **System File Checker (SFC)** | Scans + repairs protected system files | `sfc /scannow` |
| **DISM** | Services/repairs Windows images | `DISM /Online /Cleanup-Image /ScanHealth` → `/CheckHealth` → `/RestoreHealth` |
| **chkdsk** | Checks/repairs drive file-system errors, recovers bad sectors | `chkdsk c: /f`, `chkdsk c: /f /r` |
| **Third-party** | FIM/SCM + compliance | Tripwire Enterprise, OSSEC |

- SFC `%WinDir%\System32\dllcache` caches compressed copies for repair; logs: online → `windir\Logs\CBS\CBS.log`, offline → `/OFFLOGFILE`; run as **administrator**

### SFC options
| Option | Function |
|---|---|
| `/VERIFYONLY` | Scan all protected files; **no repair** |
| `/SCANNOW` | Scan all protected files instantly |
| `/VERIFYFILE` | Verify file at full path; no repair |
| `/SCANFILE` | Scan **and repair** file at full path |
| `/OFFBOOTDIR` | Offline repair — offline boot dir location |
| `/OFFWINDIR` | Offline repair — offline Windows dir |
| `/FILESONLY` | Verify/repair files only, **not** registry keys |

### DISM
- Built-in CLI (`DISM.exe`, `C:\Windows\System32`); services **.wim / .vhd / .vhdx** images, Windows PE, WinRE, Setup; also from PowerShell
- Use cases: (1) **manage image data** — inventory components/updates/drivers/apps, append/delete/capture/split/mount images; (2) **service the image** — add/remove driver packages, language settings, enable/disable Windows features, upgrades
- Flow for corruption: `/ScanHealth` (check) → `/CheckHealth` (repairable? "No component store corruption detected") → `/RestoreHealth` (repair online)

### chkdsk
- `chkdsk` alone = **read-only** scan (warns: `/F parameter not specified`); add `/f` (fix) and `/r` (find bad sectors + recover data); frees disk space
- Method 1 (GUI): **File Explorer → This PC → right-click drive → Properties → Tools → Check**; *"You don't need to scan this drive"* → **Scan drive**; **Show Details** after scan
- Method 2 (CLI): run cmd as **administrator** → `chkdsk`

## File System Integrity via PowerShell
- **Test-FileCatalog**: verifies catalog (.cat) hashes vs actual file hashes; `-Detailed` shows per-file hashes (SHA256) + `Signature` (same as `Get-AuthenticodeSignature`); `-FilesSkip` skips files; creation via `New-FileCatalog -Path <dir> -CatalogFilePath <path>` (CatalogVersion **2.0**)
- **Get-FileHash**: computes file hash; default **SHA256**; algorithms **SHA1, SHA256, SHA384, SHA512, MD5**; verify downloads: `Get-FileHash -InputStream ($wc.OpenRead($url))` then compare `$FileHash.Hash -eq $publishedHash`; changing **one character** changes the hash; even renaming the file does not change content hash

## Third-Party Integrity Monitors
**Tripwire Enterprise** — compliance + **FIM + SCM**; five features: **system integrity management** (heterogeneous scans, config-drift visibility) · **policy management** (agent-based/agent-less for 4,000+ platform combos) · **advanced use cases** (real-time asset change detection, vulnerability discovery, network-device monitoring) · **remediation management** (Policy Manager onboarding; role-driven approvals/signoffs) · **investigation + root-cause drill-down**

**OSSEC** — open-source **host-based IDS** (Free Software Foundation); features: **log-based intrusion detection (LID)**, rootkit/malware detection, file + **Windows registry** monitoring with forensic copy over time, **Syscheck** integrity checker (periodic, **MD5/SHA1** checksums), compliance auditing (PCI-DSS, CIS benchmarks), system inventory, real-time alerting
- Manual check: `# /var/ossec/bin/agent_control -r` (`-a` all agents, `-u <agent id>`)
- Config: edit **ossec.conf** (XML) — e.g. rule monitoring System32:
  ```xml
  <group name="windows">
    <rule id="100001" level="7">
      <decoded_as>json</decoded_as>
      <field name="win.system32">@windows\System32</field>
    </rule>
  </group>
  ```
- History: `# /var/ossec/bin/syscheck_control -i <agent id>` (list modified files); `-f <file>` for detailed values (size, perms, UID, GID, MD5, SHA1)












