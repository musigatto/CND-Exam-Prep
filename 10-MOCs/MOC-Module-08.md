---

type: moc
module: "08"
tags: [concept, mod/08]
topic: "Module 08 — Endpoint Security - IoT Devices"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "SeaCat.io port semantics: OCR shows 48101 as the SeaCat mTLS gateway tunnel port with Nginx on 443; vendor naming kept as printed."
  - "IoT stackwise principle table compresses a multi-page figure; kept the layer-aligned countermeasure rows as printed."
---
# Module 08 — Endpoint Security - IoT Devices

> [!abstract] Scope
> 7 LOs · 7 sections · courseware pp. 1079–1214. IoT endpoint security: IoT/IoE basics + application areas, IoT ecosystem/architecture/communication models, IoT security challenges + threat landscape (incl. OWASP Top 10), security in IoT-enabled environments (stack-wise principles + device/communication/cloud/process layer attacks and countermeasures), 27 security measures for IoT-enabled IT environments, IoT security tools + best practices, and standards/initiatives (AIOTI, NIST, DHS, GSMA).

## Sections
| LO   | §   | Section                                                        | Course pp. |
| ---- | --- | -------------------------------------------------------------- | ---------- |
| LO01 | 8.1 | IoT Devices, Their Need, and Application Areas                 | 1080       |
| LO02 | 8.2 | IoT Ecosystem, Architecture, and Communication Models          | 1086       |
| LO03 | 8.3 | Security Challenges and Risks in IoT-enabled Environments      | 1098       |
| LO04 | 8.4 | Security in IoT-enabled Environments                           | 1110       |
| LO05 | 8.5 | Security Measures for IoT-enabled IT Environments              | 1147       |
| LO06 | 8.6 | IoT Security Tools and Best Practices                          | 1188       |
| LO07 | 8.7 | Standards, Initiatives, and Efforts for IoT Security           | 1197       |

## Technical focus
- **LO01:** IoT = Internet of Things / Internet of Everything (IoE) — web-enabled sensing/communication devices · "thing" = device embedded on natural/man-made/machine-made objects · three-dimensional plane (anyone/anytime, outdoor/indoor, on the move, away from PC) · interaction types H2H/H2T/T2T · 4 component systems (sensing tech, gateways, cloud server/storage, remote-control mobile apps) · smart-security-system working flow · application areas table (Commercial/Institutional, Industrial, Consumer & Home, Healthcare, Transportation, Retail, Security/Public, IT & Networks) · IIoT 3 growth approaches.
- **LO02:** architecture blocks (gateway + cloud gateway, streaming data processors, data lakes, big data warehouse, data analytics, machine learning, control apps rule/ML-based, user apps) · 4-layer IoT architecture (Device → Communication → Cloud Platform → Process) · 4 communication models (Device-to-Device, Device-to-Cloud, Device-to-Gateway, Back-end Data-Sharing/cloud-to-cloud) · IoT-enabled IT environment tiers + features (real-time monitoring/analytics, multi-layer security, light-weight protocols, any-anywhere access).
- **LO03:** security challenges (scale, differing device types, no transparency, real-time auth beyond CIA, deployed without IT oversight, never-turned-off devices → botnets, 5G bandwidth → larger DDoS, lateral movement, SCA on low-cost hardware, obscure standards/liability) · 12 inherent security issues (no security/privacy, vulnerable web interfaces, legal/regulatory gaps, default/weak/hardcoded creds, cleartext protocols + open ports, coding errors, storage limits, hard firmware updates, interoperability, physical theft/tampering, no vendor support, emerging-economy issues) · threat landscape per layer (device/communication/cloud/process → impacts) · attack vector categories (malicious firmware, USB malware, software vulns, key/cert storage attacks, malicious apps, MITM, sniffing, dict attacks, DDoS) · DDoS-from-hacked-IoT (4 phases; JTAG + SSH) · **OWASP Top 10 IoT** vulnerabilities (#1 weak/hardcoded passwords, #2 insecure network services, #5 lack of secure updates, #8 no physical hardening...).
- **LO04:** stack-wise security principles per layer (device physical: tamper detection + TLS 1.2/1.3 + per-device keys Zero Trust; communication edge: edge firewalls + IPsec ESP; data-center: secure BGP + route filtering; cloud: SIEM + IDPS + security analytics; SSH/HTTPS/HSM for access) · IoT system mgmt (device mgmt incl. provisioning MAC/IMEI/one-off tokens + MQTT broker + WSO2 IoT; user mgmt with 2FA/SSO/OAuth/SAML; security monitoring via GE Predix + Bayshore) · **device layer attacks**: node tampering, jamming/RF interference, malicious node injection, tag cloning, malicious code injection, replay, timing/SCA, eavesdropping, object replication, hardware trojan, outage · ctr (FHSS, spread spectrum, Perrig lightweight auth, AES/Elliptic-Curve per-node ACLs) · **communication layer**: RFID (relay/crypto → challenge-response, distance-bounding, AES/RSA/TDES) · NFC (relay, eavesdrop, tag clone/spoof, data corruption → RF shields) · **Bluetooth** (Bluesnarfing, BlueBugging, Bluejacking, BlueSmack, Car Whisperer, KNOB) · Wi-Fi (WEP: Korek/Chopchop/Fragmentation/FMS/PTW + Google replay; Michael TKIP; dictionary → rekey/CCMP/AES/IPsec/DTLS) · ZigBee/IEEE 802.15.4 (KillerBee suite; AES-128) · Z-Wave (S2) · **RPL** (DOG, global repair, version number, DAO inconsistencies) · **6LoWPAN** (DoS buffer-full, fragmentation, hammering) · TCP/UDP (SYN flood, UDP flood, XMAS, Smurf, IP spoof → SYN cookies) · application-protocol (CoAP/MQTT amplification → auth tokens + TLS/DTLS).
- **LO05:** 27 security measures — M01 complete visibility (AssetExplorer, ServiceNow, Azure/AWS IoT) · M02 asset maps (Oracle IoT Asset Monitoring) · M03 behavior monitoring (Domotz Pro, TeamViewer IoT, Azure/AWS) · M04 ecosystem interfaces · M05 network segmentation (VLANs, firewall zones) · M06 limit access (PACL/VACL ACL commands) · M07 malware/ransomware monitoring (Mirai, Echobot, Torii, WannaCry) · M08 vulnerability scanning (Nexpose, Qualys, Tenable, RloT Scanner, beSTORM) · M09 firmware updates (OTA, rollback) · M10 close insecure services (nmap -sS -sU -O) · M11 E2E encryption (TLS 1.2/1.3, IPsec, DTLS, AES-256) · M12 identity mgmt (X.509, mTLS, PKI/CA) · M13 strong authentication (MFA, per-device secrets) · M14 chip-level security (TPM 2.0, RoT, secure SoC) · M15 hardware security (HSM, SGX/TrustZone) · M16 gateway security · M17 control server security · M18 remote admin (SSH + "Unplug n' Pray") · M19 router security (WPA2/WPA3, disable WPS/UPnP/SNMP, Zenmap/ShieldsUP) · M20 Wi-Fi isolation (pcWRT guest network) · M21 Ethernet isolation (VLAN ports X1/X2/X3) · M22 internet-access control (whitelist domains) · M23 network activity monitoring (pcWRT) · M24 bandwidth monitoring (SolarWinds NPM/NTA, Paessler PRTG) · M25 centralized access logs (Cloud IoT Core + Stackdriver) · M26 public-Wi-Fi security · M27 shadow IoT mgmt (Shodan).
- **LO06:** IoT security checklist (device/network/overall + port 48101, disable Telnet 23, Lock Out feature, geo detection) · tools: SeaCat.io (Teskalabs mTLS tunnel; SeaCat Gateway; ports 48101 + Nginx 443; deviceLock, netAuth OS-level SSO, Auto-Updater, jail) · DigiCert IoT Security (mTLS for constrained fleets) · additional tools (PwnPulse, Allot, Cisco IoT Threat Defense, SecEdge, net-Shield, Noddos, AWS IoT Device Defender, Trustwave EPS, Subex, libsecurity-go).
- **LO07:** AIOTI (17+2 WGs; WG01 research → WG09 privacy/security) · NIST 8 security-function areas (asset identification, device config, data protection, access, updates, event monitoring, interface access, hardening) + supporting standards (MUD, OMA, IEEE 802.1X, 802.1AR, PAP) · DHS 6 strategic principles (security by design, updates/vulnerability mgmt, recognized security practices, prioritize by impact, transparency, connect carefully) · GSMA 85 recommendations + IoT Security Assessment 8 areas (secure boot, storage, key mgmt, OTA, app isolation, DDoS protection, user-data privacy, attack mitigation) · attack/vulnerability standards (CWE, CAPEC, FIPS 140-3, Common Criteria ISO/IEC 15408 EAL 1–7) · additional initiatives (ISO/IEC JTC 1, IEEE P2413, ITU-T Y.4000, OCF, oneM2M, Thread/ZigBee/Z-Wave Alliances, OpenIoT etc.).

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: IoT vs IoE definition + "thing" · interaction types H2H/H2T/T2T · 4 component systems · 4-layer architecture · 4 communication models (+protocols per model: ZigBee/Z-Wave device-to-device vs gateway) · 12 inherent security issues · OWASP #1/IoT list · DDoS-from-hacked-IoT 4 phases + JTAG · stack-wise countermeasure-layer mapping (edge: IPsec ESP; cloud: SIEM/IDPS) · device-layer attack names (Bluesnarfing vs BlueBugging vs Bluejacking; KNOB; BlueSmack) · WEP attack families (Korek/Chopchop/Fragmentation/FMS/PTW) · Michael/TKIP fix = CCMP · KillerBee (ZigBee) + AES-128 · RPL DOG attack · 27-measure M-numbers (asset maps = M02, PACL/VACL = M06, RloT Scanner/beSTORM = M08, Unplug n' Pray = M18, pcWRT guest = M20, X1/X2/X3 = M21, Stackdriver = M25, Shodan = M27) · SeaCat.io port 48101 + DigiCert IoT · GSMA assessment 8 areas · DHS 6 principles · Common Criteria ISO/IEC 15408 + FIPS 140-3.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-08")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/08-iot-endpoint-map.canvas|IoT Endpoint Map]]
- Flows to visualize: IoT device → gateway → cloud → app (4-layer architecture + 4 communication models) → threat landscape by layer → stack-wise countermeasures per layer → device/communication/cloud/process attack taxonomy → 27-measure security checklist (visibility → access → crypto/hardware → isolation → monitoring) → tools (SeaCat.io/DigiCert) → standards (AIOTI/NIST/DHS/GSMA).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-07]] (mobile endpoint counterpart) · [[MOC-Module-06]] (Linux endpoint counterpart) · [[MOC-Module-05]] (Windows endpoint hardening: patches, services) · [[MOC-Module-03]] (network security: VPN, IPSec, IDS/IPS, firewall segmentation overlap) · [[MOC-Module-02]] (policies, data classification, privacy) · [[MOC-Module-01]] (threat landscape: DDoS/botnets, Mirai).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- SeaCat.io ports: OCR shows "48101 = SeaCat® <mutual TLS> gateway tunnel" beside Nginx 443 — kept as printed; vendor pages not used.
- The IoT stack-wise principle table compresses several figure pages (cleartext figure content); only layer-row countermeasures stated in text are recorded.

## Quick review
Module 08 subject scope?
?
IoT endpoint security: IoT/IoE basics + app areas, ecosystem/architecture/communication models, security challenges + OWASP Top 10, stack-wise security + device/communication/cloud/process layer attacks, 27 security measures, tools + best practices, and standards (AIOTI/NIST/DHS/GSMA).

4 IoT communication models?
?
Device-to-Device · Device-to-Cloud · Device-to-Gateway · Back-end Data-Sharing (cloud-to-cloud).

Favorite crackable exam items?
?
H2H/H2T/T2T + 4 component systems · 4-layer architecture · model↔protocol mappings (ZigBee/Z-Wave; IEEE 802.15.4) · 12 inherent issues · OWASP #1 · DDoS 4 phases + JTAG · stack-wise layer counters (edge IPsec ESP; cloud SIEM/IDPS) · Bluesnarfing vs BlueBugging vs Bluejacking vs BlueSmack · KNOB entropy 8→1 · WEP families Korek/Chopchop/Fragmentation/FMS/PTW · Michael→CCMP · KillerBee AES-128 · RPL DOG · M-numbers (M02 asset maps, M06 PACL/VACL, M08 RloT Scanner, M18 Unplug n' Pray, M20 pcWRT, M21 X1/X2/X3, M25 Stackdriver, M27 Shodan) · SeaCat 48101 · GSMA 8 areas · DHS 6 principles · Common Criteria ISO/IEC 15408.
