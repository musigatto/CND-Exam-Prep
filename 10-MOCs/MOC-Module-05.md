---

type: moc
module: "05"
tags: [concept, mod/05]
topic: "Module 05 — Endpoint Security - Windows Systems"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "LO06: Registry auto-update method — NoAutoUpdate value semantics ambiguous in OCR (screenshot shows 0x00000001)."
  - "LO09: SMM two defense methods listed, but OCR captured only the second (Supervisor SMI handler) in full."
---
# Module 05 — Endpoint Security - Windows Systems

> [!abstract] Scope
> 10 LOs · 10 sections · courseware pp. 627–864. Endpoint security for **Windows systems**: OS security concerns, security components, security features, baseline configuration, account/password management, patch management, user access management, OS security hardening, **Active Directory security best practices**, and **network services + protocol security** (PS Remoting, RDP, DNSSEC/DNS, SMB).

## Sections
| LO   | §    | Section                                             | Course pp. |
| ---- | ---- | --------------------------------------------------- | ---------- |
| LO01 | 5.1  | Windows OS and Security Concerns                    | 628        |
| LO02 | 5.2  | Windows Security Components                         | 639        |
| LO03 | 5.3  | Windows Security Features                           | 657        |
| LO04 | 5.4  | Windows Security Baseline Configurations            | 686        |
| LO05 | 5.5  | Windows User Account and Password Management        | 690        |
| LO06 | 5.6  | Windows Patch Management                            | 707        |
| LO07 | 5.7  | Windows User Access Management                      | 719        |
| LO08 | 5.8  | Windows OS Security Hardening Techniques            | 732        |
| LO09 | 5.9  | Windows Active Directory Security Best Practices    | 756        |
| LO10 | 5.10 | Windows Network Services and Protocol Security      | 815        |

## Technical focus
- **Platform + components:** Windows family/MS-DOS lineage · user vs kernel mode (rings) · SRM · security components (LSASS, SAM/DSRM, AD/LDAP, auth packages, Winlogon, NetLogon, KSecDD).
- **Features + baseline:** object/securable objects · ACL/DACL/SACL/ACE · access tokens + SIDs · integrity levels (MIC) · virtual service accounts · secure file sharing · security auditing (4625) · Smart App Control · Vulnerable Driver Blocklist · Credential Guard; SCT/build-time baselines, Policy Analyzer, LGPO, SetObjectSecurity, GPO2PolicyRules.
- **Management:** account types + guest/admin policies · password policy · patch management (auto-update, no-force-restart, third-party) · NTFS/UAC/SID enumeration/JEA access management · hardening (BIOS password, LM-hash prevention, restrict installs, disable services, RDP off, AV, Defender Firewall, registry monitoring).
- **AD security:** LSA protection · clean Domain Admins (pass-the-hash) · LAPS · block NTLM · AD event monitoring + PS cmdlets · AD best practices (Protected Users, tiered admin, FGPP, WDigest=0, LLMNR/NetBIOS off).
- **Network services/protocols:** PS Remoting (WinRM 5985/5986, endpoints, logging, PS2.0 off, execution policy, Constrained Language Mode, Device Guard UMCI) · RDP (users, scoping, gateways, NLA, Remote Credential Guard) · DNSSEC (auth/integrity/non-existence; not confidentiality/DoS) · DNS debug logging · SMB 1.0 disable + SMB encryption.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: PS Remoting ports 5985/5986 + WinRM · endpoint permissions (admins + Remote Management Users) · SFC options table (`/FILESONLY`, `/SCANONLY` semantics) · Get-FileHash default SHA256 · chkdsk read-only vs `/f` `/r` · WRP (formerly WFP, Windows Modules Installer) · TPM + Secure Boot/BitLocker · NTLM vs NTLMv2 hashing (MD4/MD5) · LAPS (schema attrs, CSE) · pass-the-hash vs DA group · KRBTGT rotation · DNSSEC guarantees (auth/integrity/non-existence; NOT confidentiality/DoS) · SMB version–feature mapping (3.1.1+ pre-auth integrity, 3.0+ encryption, 2.02+ signing) · RDP scoping/gateway/NLA/Remote Credential Guard · PS 2.0 disable command · execution policies (Restricted→AllSigned→RemoteSigned→Unrestricted).

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-05")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/05-windows-endpoint-map.canvas|Windows Endpoint Map]]
- Flows to visualize: integrity management (UAC→signing→WRP→TPM) → integrity checking ladder (SFC → DISM → chkdsk → PowerShell catalogs/hash → Tripwire/OSSEC) · PS Remoting defense layers (endpoints → logging → execution policy → language mode → UMCI) · RDP stack (users → scoping → gateway → NLA → credential guard) · SMB hardening path (1.0 off · encryption) · AD account protection flow (DA clean-up → LAPS → NTLM block → event monitoring).

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-01]] (attack types mitigated by hardening) · [[MOC-Module-02]] (baselines, patch/change policy) · [[MOC-Module-03]] (network + host security, IDS) · [[MOC-Module-04]] (perimeter controls interplay) · [[MOC-Module-19]] (security architecture) · [[MOC-Module-20]] (as emerging-technology overlap).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- LO06 registry auto-update method (`NoAutoUpdate` semantics) — OCR ambiguity.
- LO09 SMM defense methods — second method (Supervisor SMI handler) only fully captured.

## Quick review
Module 05 subject scope?
?
Windows endpoint security: OS components/features, baseline, accounts/passwords, patches, access, hardening, AD security, network services/protocol security.

PS Remoting default ports?
?
5985 (HTTP/WinRM) and 5986 (HTTPS); traffic encrypted even over 5985.

DNSSEC guarantees and what it does NOT provide?
?
Authenticity, integrity, non-existence of name/type; NOT confidentiality or DoS protection.

SMB versions with security features from strongest down?
?
3.1.1+ pre-auth integrity · 3.0/3.02 secure dialect · 3.0+ encryption + insecure guest blocking · 2.02+ signing.
