---
type: note
module: "07"
lo: "03"
tags: [concept, tool, threat, process, mod/07]
topic: "Mobile Content Management (MCM) and Mobile Threat Defense (MTD)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# MCM and MTD Solutions (§7.3)

## Mobile Content Management (MCM) / Mobile Information Management (MIM)
- Provides **secure access to corporate data** (documents, spreadsheets, email, schedules, presentations, other enterprise data) on mobile devices across org networks, without compromising speed
- Easy + secure content sharing between devices within an enterprise
- **Two main components: file storage + file sharing services**
- Encrypts important information; content accessed/transmitted/stored only via **authorized apps** with strong-password protection policies

### MCM capabilities
- **Multi-channel content delivery:** central content repository; deliver to devices simultaneously
- **Content access control:** authorization · authentication · access approval · download control · **wipe-out for specific users** · time-specific access
- **Specialized templating system:**
  - **Multi-client approach** — different versions of a site on the same domain; suitable templates per device
  - **Multi-site approach** — mobile sites on a targeted sub-domain
- **Location-based content delivery** (based on device physical location)

### MCM examples
- **Vaultize MCM:** mobile data containerization; end-to-end data security; encryption, tracking + wiping of files from source to devices
- **MobileIron MCM:** access + collaborative work across any network/device without security-prompt interruptions
- **APPTEC MCM/ContentBox:** simple, functional mobile apps with control over confidential data

## Mobile Threat Defense (MTD) / MTM / MTP
- MTD/MTM/MTP protects orgs + employees from threats on **iOS and Android** mobiles using different security technologies
- MDM/MAM only set baseline management profiles; they lack insights on app characteristics, threat protection, user behaviors, dynamic reaction, continuous device-health/trust visibility → **MTD extends EMM/MDM** with additional security capabilities

### What MTD secures against
- **Device/physical threats:** active threat detection + **risk-based mobile management** → more educated policy enforcement
- **Malware:** scan devices/apps for malicious activity · inform security teams · find zero-day threats · monitor connections to suspicious domains · block malicious downloads before they reach the device · prevent outbound connections attempted by malware
- **Phishing:** visibility when an employee navigates to a known mobile phishing page · quick blocking of phishing links
- **Network attacks:** auto-encrypt traffic on open Wi-Fi · scan real-time data communications per website/app · identify insecure data transmissions · identify data leaks → block risky content (removes MITM possibility)

### MTD at different mobile-enterprise levels
- **Device level:** monitor OS versions · security-update versions · system parameters · device configuration · firmware · system libraries; check for **modification of system libraries**, configuration modification, **privilege escalation (jailbreak/root)**
- **Network level:** monitor cellular + wireless traffic for unauthorized access · monitor malicious behavior · detect invalid/spoofed certificates · strip TLS/SSL · customized MITM detection techniques
- **Application level:** identify grayware/malware via **application sandboxing + code analysis**; techniques = signature-based anti-malware filtering · code emulation/simulation · application reverse engineering · static + dynamic app security testing

### Selecting an MTD solution — factors
- OS employed · mobile approach (BYOD or COPE) · type of access granted on devices · the EMM employed

### MTD examples
- **MobileIron MTD:** always-on protection with machine-learning algorithms; blocks all mobile device threats
- **Lookout MTD:** protects against phishing, content filtering, VPN
- **Wandera MTD:** multi-level protection for users, endpoints, corporate apps; controls unwanted access, prevents data breaches

## Cards
Q:: MCM main components?
A:: File storage + file sharing services; secure access to corporate data via authorized apps; wipe-out for specific users.
#flashcard
Q:: MCM templating approaches?
A:: Multi-client (different site versions on the same domain) · multi-site (mobile sites on a targeted sub-domain).
#flashcard
Q:: What does MTD add beyond MDM/MAM?
A:: Insights into app characteristics, threat protection, user behavior, dynamic threat reaction, continuous device-health/trust visibility — extends EMM/MDM.
#flashcard
Q:: MTD protection levels in the mobile enterprise?
A:: Device level (OS/config/firmware checks, privilege escalation) · network level (traffic monitoring, spoofed certs, TLS/SSL stripping, MITM detection) · application level (sandboxing, code analysis, anti-malware signatures, reverse engineering, static/dynamic testing).
#flashcard
Q:: MTD vendor examples?
A:: MobileIron, Lookout, Wandera.
#flashcard