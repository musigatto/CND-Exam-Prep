---
type: note
module: "08"
lo: "07"
tags: [policy, process, bestpractice, mod/08]
topic: "IoT Security Standards, Initiatives, and Efforts"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Standards, Initiatives, and Efforts (§8.7)

## AIOTI (Alliance for Internet of Things Innovation)
- Industry-driven multi-stakeholder platform coordinated by EC; **17+2 Working Groups (WG01–WG19)**
- Key WGs: WG01 (IoT Research), WG02 (Innovation Ecosystem), WG03 (IoT Standardisation), WG04 (Policy), WG05 (Smart Living), WG06 (Smart Farming), WG08 (Smart Manufacturing), WG09 (IoT Privacy/Security), WG10 (Smart Mobility), WG13 (Wearables), WG14 (Smart City)

## NIST (U.S. NISTIR 8228) — 8 IoT Security Feature Recommendations + Practices
1. **Asset identification** (Physical/logical/Profile: DMA, MUD, PAP)
2. **Device configuration** (DMA, SENSEI, MUD, OMA, IEEE 802.1X, 802.1AR)
3. **Data protection** (DF)
4. **Logical access** to interfaces (DMA, PANA, EAP)
5. **Software & firmware updates** (UPD)
6. **Cybersecurity event monitoring** (MUD)
7. **Logical access to interfaces** (See above)
8. **High-level IoT device hardening** (27301 xx)

## DHS Strategic Principles for Securing the IoT
| Principle | Focus |
|---|---|
| **Security by design** | Design phase, not patch/after |
| **Security updates & vulnerability management** | Vendor responsibility |
| **Recognize security practices** | Legislative/industry standards |
| **Prioritize by impact** | Risk-based |
| **Transparency** | Consumers informed |
| **Connect carefully and deliberately** | Deployment best-practice |

## GSMA IoT Security Guidelines
- 14 high-level guidelines (device/implementation/network/secure interface) + **85 recommendations** (device considerations)
- **IoT Security Assessment** (guided security audit) — security score + **8 areas: secure boot, storage, key mgmt, over-the-air updates, app isolation, DDoS protection, user-data privacy, attack mitigation**

## Standards for Potential IoT Attacks & Vulnerabilities
| Standard | Purpose |
|---|---|
| **CWE (Common Weakness Enumeration)** | software weakness taxonomy (CWE-264, CWE-255, CWE-639) |
| **CAPEC** | attack pattern enumeration (CAPEC-21 Exploitation of Trusted Credentials) |
| **FIPS 140-3** | cryptographic module security |
| **Common Criteria (ISO/IEC 15408)** | IT-security evaluation profile (EAL 1-7) |

## Other Standards / Initiatives
- R2M (Reliable, Security, Safe); ISO/IEC JTC 1 IoT; IEEE P2413 (IoT Architecture); ITU-T Y.4000 (IoT Overview); IoT Alliance Australia; Open Connectivity Foundation (OCF · OCF IoTivity); IPSO Alliance; AllSeen Alliance; oneM2M; EnOcean Alliance; Thread Group; ZigBee Alliance; Z-Wave Alliance; GSMA IoT; Opere Alliance; M2M Alliance; Internet of Things Council / IoT Security Foundation; IEEE P2413 (IoT Architecture). Also OWASP IoT Top 10 (see [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]).

## Cards
Q:: AIOTI?
A:: Alliance for Internet of Things Innovation — EU multi-stakeholder platform; 17+2 WGs (WG09 = IoT Privacy/Security).
#flashcard
Q:: NIST IAIP for IoT — 8 feature areas?
A:: Asset identification · device config · data protection · logical access · firmware updates · event monitoring · interface access · hardening.
#flashcard
Q:: DHS IoT strategic principles (6)?
A:: Security-by-design · updates/vuln mgmt · recognized security practices · prioritize by impact · transparency · connect carefully.
#flashcard
Q:: GSMA IoT security — 8 assessment areas?
A:: Secure boot · storage · key mgmt · OTA updates · app isolation · DDoS protection · user-data privacy · attack mitigation.
#flashcard
Q:: Common Criteria standard for IoT eval?
A:: ISO/IEC 15408 — EAL 1–7 evaluation (FIPS 140-3 = crypto modules).
#flashcard