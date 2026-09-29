---
type: exam
module: "key"
tags: [exam, mod/01]
topic: "CND Answer Key — one-line justifications"
exam_weight: high
status: draft
unresolved: []
---
# Answer Key

> [!info] Convention
> `Q#### → Answer` + one-line justification citing `Module NN · Topic`.

## Module 01
- Q001 — **A** — Courseware §1.1: *Risk = Asset + Threat + Vulnerability* (Module 01 · Essential Terminologies).
- Q002 — **B** — *DHCP starvation* floods the server with spoofed-MAC requests using tools such as Gobbler, exhausting the IP pool → DoS (Module 01 · Network-level Attacks).
- Q003 — **C** — *Session side-jacking* uses packet sniffing to intercept session cookies when the site does not use SSL/TLS for the **entire** session (Module 01 · Application-level Attacks — Session Hijacking).
- Q004 — **B** — *Reactive approach* is complementary to preventive and includes security monitoring methods such as IDS, SIMS, TRS, and IPS (Module 01 · Continual/Adaptive Security Strategy).
- Q005 — **B** — The 11 Enterprise tactics are derived from the later Cyber Kill Chain stages: exploit, control, maintain, and execute (Module 01 · Hacking Methodologies — MITRE ATT&CK).

## Module 02
- Q006 — **B** — Compliance hierarchy: *Frameworks → Policies → Standards → Procedures → Guidelines* (Module 02 · Regulatory Frameworks Compliance).
- Q007 — **A** — A *data controller* alone or jointly determines purposes/means of processing; a *data processor* processes on the controller's behalf; controllers/processors in the EU must comply with GDPR (Module 02 · Regulatory Frameworks — GDPR).
- Q008 — **D** — *Prudent*: all services blocked by default, network defender individually enables safe/necessary services, maximum security + everything logged (Module 02 · Security Policy — Internet Access Policies).
- Q009 — **B** — Asset categorization groups by type, usage, location, owner/department, lifecycle stage, vendor/manufacturer, criticality, and license type (Module 02 · Asset Management — ITAM process).
- Q010 — **A** — A *Secret*-level user has "access to secret + confidential + restricted + unclassified" but **NOT** top secret; only Top Secret users access everything (Module 02 · Security Awareness Training — Data Classification).

## Module 03
- Q011 — **C** — *Research* honeypots evaluate the attacker's steps precisely to build countermeasures; *production* honeypots look real next to production servers to identify attackers (Module 03 · Essential Network Security Solutions — Honeypot).
- Q012 — **C** — NAC checks AV presence/update, configured firewall or IPS, viruses, and OS updates — a Wi-Fi password check is **not** listed (Module 03 · Essential Network Security Solutions — NAC).
- Q013 — **B** — *TACACS+* (Cisco) separates AAA and encrypts the entire client–server communication including the password; it is connection-oriented over **TCP port 49** vs RADIUS (UDP) (Module 03 · Essential Network Security Protocols — TACACS+).
- Q014 — **A** — *AH* authenticates the sender only; *ESP* authenticates the sender **and** encrypts the data (Module 03 · Essential Network Security Protocols — IPsec).
- Q015 — **C** — *UTM* combines firewall, IDS, anti-malware, spam filter, content filtering, DLP, and VPN in one appliance; a known drawback is single point of failure (Module 03 · Essential Network Security Solutions — UTM).

## Module 04
- Q016 — **B** — *Packet filtering* firewalls "work at the network level of the OSI model," checking each packet's header against rules; circuit-level works at the session layer and application-level at the application layer (Module 04 · LO02 Firewall Technologies).
- Q017 — **A** — Deployment *L1 (outside the perimeter firewall)* is tuned to least-sensitive attacks, "logs attack attempts only, no alerts"; L2 DMZ covers low–moderate, L3 backbone medium–high, L4 critical high-impact (Module 04 · LO12 NIDS Deployment Locations).
- Q018 — **A** — Because encrypted payloads can't be matched to signatures, the courseware advises placing "an IDS behind a VPN termination with SSL encryption" so traffic arrives decrypted (Module 04 · LO13 Dealing with False Negatives).
- Q019 — **C** — *Static* port security "allows only a single MAC address to be connected to a port"; sticky assigns per port (lost on reboot), dynamic is the CAM default (Module 04 · LO16 Switch Security Measures).
- Q020 — **D** — The *SDP controller* is "an authentication point that evaluates the policy and grants access to the client" and determines which client↔gateway pairs communicate; traffic tunnels only after controller approval (Module 04 · LO17 SDP Architecture and Components).

## Module 05
- Q021 — **B** — *Virtual service accounts* run each service under its own account/SID named `NT SERVICE\<service name>`, with password set and periodically changed by Windows (Module 05 · §5.3 Windows Security Features — Virtual Service Accounts).
- Q022 — **A** — `net user guest /active:No` disables the Guest account (guards against password-less/unauthenticated Internet access); policy variant: `Accounts: Guest account status` (Module 05 · §5.5 User Account and Password Management).
- Q023 — **A** — `sc config wuauserv start= auto` enables automatic-start of the Windows Update service (Module 05 · §5.6 Windows Patch Management).
- Q024 — **A** — *Just Enough Administration (JEA)* grants only needed cmdlets/scripts/functions via role capability files + session configuration files (Module 05 · §5.7 User Access Management).
- Q025 — **B** — DNSSEC guarantees *authenticity*, *integrity*, and *non-existence* of a domain name or type; it explicitly does **not** guarantee confidentiality or DoS protection (Module 05 · §5.10 Network Services and Protocol Security — DNSSEC).

## Module 06
- Q026 — **B** — `find / -perm +4000` shows *all files with SUID set* (`+2000` = SGID); `chmod a-s` removes the bit — a wrong SUID list is a privilege-escalation risk (Module 06 · §6.4 File Permissions — SUID/SGID).
- Q027 — **B** — The courseware's Table 6.5 maps *blocking an XMAS scan* to `iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP`; the NULL/fragment rules are separate entries (Module 06 · §6.5 Host-based Firewall with iptables).
- Q028 — **B** — *Permissive* "prints warnings instead of enforcing"; *enforcing* applies the SELinux policy (blocks requests) and *disabled* loads no policy (Module 06 · §6.6 Security-Enhanced Linux modes).
- Q029 — **C** — Ubuntu minimal installation *removes approximately 80 packages* vs the default, restricting third-party/untrusted applications that may be vulnerable to new exploits (Module 06 · §6.2 Linux Installation — Minimal Installation).
- Q030 — **C** — Chroot SFTP: comment out the sftp Subsystem and append `Subsystem sftp internal-sftp` + `Match group sftponly` block (`ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, `ForceCommand internal-sftp`) (Module 06 · §6.5 Setup Chroot SFTP).

## Module 07
- Q031 — **C** — *CYOD* lets employees select devices (laptops, smartphones, tablets) from a *company-approved list*; the company purchases the selected device (Module 07 · §7.1 Choose Your Own Device).
- Q032 — **C** — *System-based risks* cover vulnerabilities unintentionally introduced by manufacturers, e.g., in *SwiftKey keyboards* or mobile OSes; mitigation is regular device updates (Module 07 · §7.2 Risk and Challenge Categories).
- Q033 — **B** — *SaaS-based MDM* suits organizations that do not want to maintain on-site servers but still want management and admission; they can negate up-front cost by paying monthly/annual fees (Module 07 · §7.3 MDM Delivery Methods).
- Q034 — **D** — The guidelines list *remote wipe services* such as Find My Device (Android) and Find My iPhone / FindMyPhone (iOS) to locate/wipe lost or stolen devices (Module 07 · §7.4 Use Remote Wipe Services).
- Q035 — **C** — *Maximum failed password attempts* specifies how many wrong entries are allowed before the device wipes its data; the API also allows remote factory reset for lost/stolen devices (Module 07 · §7.5 Android Device Administration API).

## Module 08
- Q036 — **C** — *Device-to-Device*: connected devices interact directly via the Internet (often primarily directly) using Bluetooth, Z-Wave, Zigbee, or Wi-Fi (smart-home devices, wearables, ECG/EKG paired to smartphone) (Module 08 · §8.2 IoT Communication Models).
- Q037 — **D** — *Bluesnarfing* = via Bluetooth, exploit OBEX Push to access phone/Laptop data; *BlueBugging* = remote control of device (unrestricted access, AT commands, Internet connect, place calls) via OBEX Push profile / personal-area-network FTP (Module 08 · §8.4 Bluetooth Attacks).
- Q038 — **A** — *KillerBee* is the ZigBee/IEEE 802.15.4 exploitation toolkit: zbdump, zbconvert, zbreplay, zbstumbler, zbfind, zbinject, zbopenear (Module 08 · §8.4 ZigBee / IEEE 802.15.4 Attacks).
- Q039 — **C** — *SeaCat.io* gateway tunnel listens on **48101** (SeaCat mutual-TLS), with Nginx on 443 (Module 08 · §8.6 IoT Security Tools — SeaCat.io).
- Q040 — **B** — The *GSMA IoT Security Assessment* audits 8 areas: secure boot, storage, key management, over-the-air updates, app isolation, DDoS protection, user-data privacy, attack mitigation — *secure boot* is one of them (options A/C/D are NIST areas) (Module 08 · §8.7 GSMA IoT Security Guidelines).

## Module 09
- Q041 — **B** — *Whitelisting* = trust-centric, allow only approved, deny by default; *blacklisting* = threat-centric, allow by default, deny a list of known-bad programs; blacklist cons = never comprehensive, no zero-day defense, easily evadable (Module 09 · §9.1 Whitelisting/Blacklisting Approaches).
- Q042 — **C** — The SRP *hash rule* hashes the file so the rule applies wherever the file is located (even after rename/move); path rules break when the file moves, certificate rules use signing (not enabled by default), internet-zone rules apply only to .msi (Module 09 · LO01 Software Restriction Policy Rule Types).
- Q043 — **B** — *WDAG* runs Microsoft Edge in a hardened container: blocks websites from local storage, memory, installed apps, corporate network endpoints; prerequisites include 64-bit, ≥4 cores with virtualization + SLAT, ≥8 GB RAM (Module 09 · LO02 Windows Defender Application Guard).
- Q044 — **A** — Patch-management flow: *scan for new/missing patches → download to a central location → select the relevant client patch → test the patch → deploy if the test succeeds* (Module 09 · LO03 Application Patch Management).
- Q045 — **C** — WAF *limitations* include "cannot read database commands" → not complete web-app attack protection; it is not a substitute for user auth/input filtering, not set-and-forget, and offers no false-positive protection (Module 09 · LO04 WAF Limitations).

## Module 10
- Q046 — **A** — Courseware maps safeguards to the 3 data states: *in transit* → SSL/TLS and PGP/S-MIME email encryption; *in use* → authentication, memory encryption, strong identity, patching; *at rest* → encryption, password/tokenization, access control (Module 10 · LO01 Three States of Data).
- Q047 — **B** — *Always Encrypted deterministic* encryption produces the same ciphertext for the same plaintext, enabling equality lookups; randomized always produces different ciphertext (less predictable); TDE encrypts data at rest only and the engine holds keys (Module 10 · LO03 Always Encrypted).
- Q048 — **A** — Oracle data-masking F.A.S.T. = *Find → Access → Secure → Test*; discovery jobs find sensitive columns (CREDITCARDNUMBER, SSN 9-digit) before the masking definition/job "secures" them (Module 10 · LO05 Oracle Data Masking F.A.S.T.).
- Q049 — **B** — Oracle cold backup: *SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN*; a closed database needs no archive logs, unlike the RMAN hot backup with ARCHIVELOG (Module 10 · LO06 Oracle Cold vs Hot Backup).
- Q050 — **B** — *Purging* (degaussing + Secure Erase) defends against laboratory attacks using signal-processing recovery; clearing/overwriting only counters keyboard-level convenience attacks (Module 10 · LO07 Data Destruction Techniques).