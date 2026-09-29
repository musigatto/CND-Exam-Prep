---
type: note
module: "08"
lo: "03"
tags: [threat, concept, bestpractice, mod/08]
topic: "IoT Security Challenges, Risks, Threat Landscape, and OWASP Top 10"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Challenges, Risks, Threat Landscape, and OWASP Top 10 (§8.3)

## Security Challenges in IoT-enabled Environments
- Sheer number of devices, complexity, and speed of adoption → hard to keep pace with emerging threats
- Devices very different; security depends on type/model; many fail to secure all device interfaces
- Inherently insecure — not designed with security in mind
- No transparency about functionality; manufacturer updates may enable unwanted functions
- Real-time authentication/authorization needed beyond CIA triad → MITM, physical (spoofing/cloning), software, encryption attacks
- IoT often deployed without IT oversight (BYOD-like); risk of same kind as mobile devices
- Risk factors: **weak IoT configurations · shared secrets · software security degrading over time · operating in safe and hostile environments**
- Devices with **default firmware, usernames/passwords** that cannot be updated/changed are unsafe
- Devices **not under IT/user supervision** are most vulnerable
- **5G**: huge data at high speeds → data compromise risk + increased bandwidth for IoT DDoS
- Devices **never turned off** → vulnerable to DDoS or cryptojacking
- **Lateral movement** via pivoting/propagating devices
- Non-IT individuals deploy devices; IT unaware → breached via console/USB → backdoors
- Low-cost/low-power devices → physical attacks, **side-channel attacks (SCAs)**
- Botnet co-option → botnet attacks
- Obscure standards/regulations, immature security frameworks, unclear liabilities → barriers

## Inherent Security Issues with IoT Devices
| # | Issue |
|---|---|
| 01 | **Lack of security and privacy** |
| 02 | **Vulnerable web interfaces** (embedded web server technology) |
| 03 | **Legal, regulatory, and rights issues** (existing laws can't address) |
| 04 | **Default, weak, and hardcoded credentials** |
| 05 | **Cleartext protocols and unnecessary open ports** |
| 06 | **Coding errors (buffer overflow, SQL injection)** — embedded web services |
| 07 | **Storage issues** (small capacity vs limitless data) |
| 08 | **Difficulty to update firmware and OS** (may break functionality) |
| 09 | **Interoperability standard issues** (can't test APIs, third-party software, common management layer) |
| 10 | **Physical theft and tampering** (hardware modification, malicious code, counterfeiting) |
| 11 | **Lack of vendor support for fixing vulnerabilities** |
| 12 | **Emerging economy and development issues** (new policy blueprints needed) |

## IoT Threat Landscape and Impact (by layer)
| Layer | Threats | Impact |
|---|---|---|
| Device Layer | Spoofing, DoS, Tampering, Information Disclosure, Elevation of Privilege, Theft, Repudiation | Fraud, Service Interruption, Data Breach, Privacy Violation, Extortion, Reputational Damage |
| Communication Layer | Tampering, Information Disclosure, DoS, Spoofing | Data Breach, Service Interruption, Privacy Violation, Reputational Damage, Fraud |
| Cloud Layer | Tampering, Information Disclosure, Elevation of Privilege, Theft, DoS | Data Breach, Extortion, Service Interruption, Privacy Violation, Reputational Damage |
| Process Layer | Intellectual Property Theft, Theft, Repudiation | Lawsuits, Reputational Damage |

- **Spoofing:** pretend to be legitimate user; steal cryptographic keys (software/hardware level); identity theft
- **DoS:** degrade/deny service; interference with RF or cut wires
- **Tampering:** replace device software; leverage genuine device identity
- **Repudiation:** perform action, deny it
- **Information disclosure:** manipulated software + extracted key → siphon info
- **Elevation of privilege:** force device to do unintended task (e.g., open valve fully)
- **Theft:** steal device/IP/data in transit/at rest (eavesdropping)

## Attack Vectors in IoT Architecture
- **Malicious firmware updates** (hijack device functions; e.g., camera routed to remote machine)
- **Malware delivery via data storage devices** (USB autorun; replication each reboot)
- **Software vulnerabilities** (SQL injection, OS command injection, buffer/integer overflow)
- **Attacks on key/certificate storage** (steal → gain trusted status → bypass controls)
- **Attacks from downloaded apps** (malicious apps posing legitimate)
- **MITM attacks** · **Sniffing of user data** · **Attacks from mobile devices** · **Password dictionary attacks**
- **DDoS attacks** · **Malware** (viruses, worms, trojans)

## DDoS Attack from Hacked IoT Devices
- Convert IoT devices into botnets to launch huge network traffic
- Vulnerability sources: embedded OS/firmware · weak authentication/hardcoded passwords not reset · insecure SSH/Telnet (malware install) · unencrypted traffic device↔control service · physical chipset access via open JTAG interface
- **4 phases:** identify + take over control → reprogram devices for malicious actions → activate → launch DDoS
- Hackers use **JTAG** (standard chip test/debug interface) with debugging software to learn chip responses; use SSH to compromise and build botnets

## OWASP Top 10 IoT Vulnerabilities
1. **Weak, Guessable, or Hardcoded Passwords**
2. **Insecure Network Services** (e.g., Telnet, Wi-Fi, ZigBee, Bluetooth, FTP, SSH, UPnP)
3. **Insecure Ecosystem Interfaces** (web/backend API/cloud/mobile; weak auth/encryption/filtering)
4. **Use of Insecure or Outdated Components** (deprecated software/libs, supply chain)
5. **Lack of Secure Update Mechanism** (no firmware validation, no anti-rollback)
6. **Insufficient Privacy Protection**
7. **Insecure Data Transfer and Storage** (weak/lack of crypto, weak key rotation)
8. **Lack of Physical Hardening**
9. **Insufficient Security Configurability** (stronger auth/logging/encryption strength mgmt)
10. **Lack of Device Management** (asset mgmt, update mgmt, secure decommissioning, monitoring)

## Cards
Q:: Key inherent IoT issues (top 6)?
A:: No security/privacy · vulnerable web interfaces · legal/regulatory gaps · default/weak/hardcoded credentials · cleartext protocols + open ports · coding errors (buffer overflow).
#flashcard
Q:: Why are IoT DDoS/cryptojacking effective?
A:: IoT devices are usually never turned off, and many use default/hardcoded credentials.
#flashcard
Q:: OWASP #1 IoT vulnerability?
A:: Weak, guessable, or hardcoded passwords.
#flashcard
Q:: DDoS-from-hacked-IoT four phases?
A:: Identify + take over → reprogram device → activate → launch DDoS.
#flashcard
Q:: Process-layer IoT threat impacts?
A:: Intellectual property theft, theft, repudiation → lawsuits, reputational damage.
#flashcard