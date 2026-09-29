---

type: note
module: "09"
lo: "01"
tags: [concept, process, bestpractice, mod/09, flashcard/09]
topic: "Application Whitelisting and Blacklisting — Approaches, SRP, AppLocker"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Application Whitelisting & Blacklisting (§9.1a)

## Whitelisting Approach
- **Whitelisting** = security practice to **control access by allowing only a list of approved applications/software/emails/domains** (whitelisted applications); **denies everything else** (Deny by Default / Do Not Run)
- **Trust-centric**; to run a program the defender must first add it to the whitelist
- Any of: runtime process, host, app + components (plug-ins, config files, software libraries, extensions), email addresses, port numbers can seed a whitelist

### Advantages (8)
1. Protection against malware attacks (non-whitelisted apps blocked)
2. Mitigating zero-day attacks (blocks vuln execution while AV/patches lag)
3. Improved efficiency of computers (no unauthorized apps running)
4. Increased visibility + greatly reduced attack surface (tracks run/blocked apps)
5. Reclaiming bandwidth from streaming/sharing apps (social media, games, destructive apps)
6. Avoiding lawsuits / unnecessary license fees (stops unlicensed/illegal apps)
7. Security independent of constant application updating (unlike AV)
8. Easier attack detection (blocked attacks generate noise → intel for IR teams)
9. Reduced BYOD risk (via mobile-application policy enforcement)

## Blacklisting Approach
- **Blacklisting** = security practice to **prepare a list of undesirable (blacklisted) applications and prevent their execution**; **allows everything else** (Allow by Default)
- **Threat-centric**; most AV programs, spam filters, IDS/IPS use it
- Blacklist can comprise malware, users, IPs, applications, email addresses, domains
- **Advantages:** simple to implement; low maintenance (lists compiled by security software)
- **Disadvantages:** list can never be comprehensive (threat volume grows); cannot stop **zero-day** attacks (first targets unprotected); hackers craft malware to evade blacklist detection

## Whitelisting Controls — Windows Software Restriction Policies (SRP)
- **SRPs** = Active Directory + Group Policy feature to identify & control application execution; define trust policies to restrict unauthorized software
- Accessible via **Local Group Policy Editor** → Software Restriction Policies extension / **MMC Local Security Policy**
- **4 rule types for whitelisting**:
| Rule | Mechanism | Notes |
|---|---|---|
| **Path rule** | locates app by file path (or registry key as path) | if file moves, rule stops applying; wildcards: `?` single char, `*` series (e.g., `C:\MyFiles *.exe`); env vars `%temp% %windir% %programfiles% %appdata% %systemroot% %userprofile%` allowed; **Disallowed app can still run if copied elsewhere**; set Windows folder to Disallowed (affects OS) |
| **Hash rule** | hashes the file; rule applies wherever file is | hash unchanged by rename/move; newer app version bypasses; any byte change alters hash |
| **Certificate rule** | identify app by signing certificate; auto-trust trusted vendors (email hash, not virus) | **not enabled by default**; needs admin credentials |
| **Internet zone rule** | locates software by IE zones: My Computer, Internet, Trusted Sites, Local Intranet, Restricted Sites | applies **only to Windows Installer (.msi)** packages |

- Security levels: **Disallowed · Basic User · Unrestricted**
- Notes: GPO create/modify permissions needed; log out/in to apply; conflicts resolved by rule **precedence**

## AppLocker (Whitelisting)
- **AppLocker** = in-built Windows security component controlling which apps users run: **executables, Windows Installer files, DLLs**
- Default executable rules = based on **folder paths** (all files under those paths allowed)
- **Group Policy AppLocker** sets rules for apps in a domain
- AppLocker rules apply **only to specific Windows editions**
- Rule collections: **Executable Rules · Script Rules · Windows Installer Rules · Packaged app rules**

## Cards
Whitelisting = ? / philosophy?
?
Allow-list control (trust-centric): allow only approved apps, deny by default → blocks everything not whitelisted.

Whitelisting mitigates which attack class?
?
Zero-day attacks (blocks vuln code execution while patches/signatures lag).

Blacklisting = ? / philosophy?
?
Deny-list control (threat-centric): block known-bad apps, allow by default (AV, spam filters, IDS/IPS).

Blacklisting's main weakness?
?
Cannot stop zero-day attacks and is never comprehensive (unknown theats slip through).

SRP rule types (4)?
?
Path · Hash · Certificate · Internet Zone rules (of the default Disallowed level).

Most common whitelisting via SRP — two big caveats?
?
A Disallowed app can still be run by copying it elsewhere; internet zone rules apply only to .msi.

AppLocker controls which files?
?
Executables, Windows Installer files, and DLLs (default rules = folder paths).

AppLocker rule collections?
?
Executable · Script · Windows Installer · Packaged app rules.
