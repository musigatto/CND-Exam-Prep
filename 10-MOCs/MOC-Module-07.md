---
type: moc
module: "07"
tags: [concept, mod/07]
topic: "Module 07 — Endpoint Security - Mobile Devices"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "COBO divider/paragraph wording partly garbled in OCR (single-application device phrasing); kept to verified list items."
---
# Module 07 — Endpoint Security - Mobile Devices

> [!abstract] Scope
> 6 LOs · 6 sections · courseware pp. 991–1076. Mobile endpoint security: enterprise mobile usage policies (BYOD/COPE/COBO/CYOD), security risks + guidelines, enterprise mobile management solutions (MDM/MAM/MCM/MTD/MEM/EMM/UEM), general mobile security best practices, and platform-specific security for **Android** (Device Admin API + tools) and **iOS**.

## Sections
| LO   | §    | Section                                                | Course pp. |
| ---- | ---- | ------------------------------------------------------ | ---------- |
| LO01 | 7.1  | Common Mobile Usage Policies in Enterprises            | 992        |
| LO02 | 7.2  | Security Risks and Guidelines for Mobile Policies      | 1010       |
| LO03 | 7.3  | Enterprise-Level Mobile Security Management Solutions  | 1017       |
| LO04 | 7.4  | General Security Guidelines and Best Practices         | 1042       |
| LO05 | 7.5  | Security Guidelines and Tools for Android Devices      | 1053       |
| LO06 | 7.6  | Security Guidelines and Tools for iOS Devices          | 1068       |

## Technical focus
- **Policies:** 4 approaches — BYOD (Bring Your Own Device)/BYOT/BYOP/BYOPC · COPE (Co-Owned, Personally Enabled) · COBO (Company Owned, Business Only) · CYOD (Choose Your Own Device) · decision questions (device type/selection/cost, management/support, integration/apps) · 5-step implementation ladder (requirements → device+data mgmt → policies → security → support) · BYOD PIA + mobile governance committee · COPE containerization · COBO single-application (Blackberry classic).
- **Risks:** 4 challenge categories — physical (loss/theft, malicious flashing), network (WPA2, IPSec/SSL/SSH/HTTPS/Kerberos, content filter + DLP gateways), system (SwiftKey, OS vulns), application (unpatched apps) · top-10 policy risks (unsecured-network sharing, endpoint data leakage, improper disposal, device sprawl, personal/private mixing, lost/stolen, unawareness, policy bypass, infrastructure, disgruntled employees) · admin/employee guideline sets · access gateway auth (No auth · Domain · SMS · RSA SecurID · Domain+RSA SecurID).
- **LO03 stack:** MDM (console + agent; 10 features; premise/SaaS/managed delivery; deployment = policy, risk mgmt, config mgmt, app testing, procurement, compliance, activation, disposition; challenges; selection factors) · MAM (enterprise app store, version mgmt, push, reporting, usage analytics, event mgmt, app wrapping; Intune MDM+MAM vs MAM-WE) · MCM (file storage + file sharing; multi-channel delivery, access control, multi-client/multi-site templates, location-based) · MTD (extends EMM/MDM; devices/physical, malware, phishing, network; device/network/app levels; MobileIron, Lookout, Wandera) · MEM (S/MIME, SCEP for iOS/Windows, attachment control, managed email client) · EMM = MDM+MAM+MTM+MCM+MEM (4-phase deployment: Plan/Design/Deploy/Implement) · UEM (single interface, per-app VPN, containerization, certificate identity, DLP; CMT+MDM+MAM+MCM; Scalefusion, Ivanti, Workspace ONE/AirWatch).
- **LO04:** app security list (no saved passwords, no query string, obfuscation/encryption, 2FA, SSL/TLS, no caching, input validation, containerization, jailbreak protection) · data security (device + OTA encryption, backups, private data centers, no public Wi-Fi) · network guidelines (disable BT/IR/Wi-Fi, encrypted Wi-Fi only, SSID/VLAN isolation) · general guidelines (passcode/erase data, updates, remote mgmt via MDM, no root/jailbreak, Find My Device/Find My iPhone wipe, Encrypt Storage, backup/sync control, email DLP, signed-app rules, browser rules, device policies, Citrix + Follow-Me-Data/ShareFile) · admin guidelines · **SMS phishing countermeasures**.
- **LO05 Android:** Device Administration API (Android 2.2; password policies incl. complex (3.0), max failed attempts → wipe, inactivity lock 1–60 min, storage encryption (3.0), disable camera (4.0)) · securing Android (no root, official market, no APK downloads, Android Protector, AppLock, Lookout/3cX/SeekDroid remote erase, GPS) · Find My Device (google.com/android/find; prerequisites; Play sound 5 min / Lock / Erase) · AV: Kaspersky VPN & Antivirus (+Avira, Avast, McAfee, Sophos, Malwarebytes, Trend Micro...) · scanners: X-Ray (+Threat Scan, Astra, Zimperium, Quixxi, Armis BlueBorne, EternalBlue) · trackers: Google Find My Device, Where's My Droid (+Prey, iHound, Hoverwatch, Life360, GadgetTrak, TrackView, Lost Android).
- **LO06 iOS:** Passcode Lock, Alpine root password change, no jailbreak, App Store only, Ask to Join Networks, Erase Data, Delete Keyboard Cache, Geotagging off, Safari privacy + Do Not Track, disable BT/Wi-Fi, iCloud off for enterprise data, Find My iPhone (Lost Mode iOS 6+, Find My network, Send Last Location) · security tools: Avira Mobile Security (+Norton, LastPass, McAfee, SplashID, Webroot, Wickr Me, 1Password, GadgetTrak).

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: approach definitions (BYOD vs COPE vs COBO vs CYOD; COBO single-app/Blackberry) · COPE cheapest-to-buy/slowest deploy · 5-step BYOD/CYOD/COPE/COBO implementation · 10 policy risks · risk categories (physical/network/system/application; SwiftKey) · MDM features + delivery methods (premise/SaaS/managed) · MAM services (app wrapping) · Intune MDM+MAM vs MAM-WE · MCM components (file storage+sharing; multi-client vs multi-site templates) · MTD levels (device/network/application) + what MTD adds beyond MDM/MAM · MEM SCEP · EMM = MDM+MAM+MTM+MCM+MEM formula · UEM definition + per-app VPN/scalable identity · passcode/erase-data specifics · Find My Device prerequisites + 3 actions · SMS phishing countermeasures · Android Device Admin policy details (max failed attempts wipe; disable camera Android 4.0; complex password Android 3.0) · X-Ray (duo labs) · Where's My Droid attention word + Commander · iOS Alpine default root password · Find My iPhone Lost Mode iOS 6+ · Avira Mobile Security.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-07")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/07-mobile-endpoint-map.canvas|Mobile Endpoint Map]]
- Flows to visualize: policy choice (BYOD vs CYOD vs COPE vs COBO → 5-step implementation) → risk layers (physical/network/system/application → top-10) → management stack (MDM → MAM → MCM → MTD → MEM → EMM = all → UEM single interface) → general best practices (app/data/network + platform guidelines) → platform-specific zones (Android: Device Admin API + tools · iOS: passcode/Find My/tools).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-05]] (Windows endpoint counterpart) · [[MOC-Module-06]] (Linux endpoint counterpart) · [[MOC-Module-02]] (admin security: policies, data classification, privacy) · [[MOC-Module-03]] (network security: VPN, NAC overlap) · [[MOC-Module-01]] (threat landscape: phishing/smishing, malware).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- COBO implementation paragraph: OCR garbled wording on "device that runs a single application... otherwise smartphones with prohibited personal use" — kept the verified list; no invented specifics.

## Cards
Q:: Module 07 subject scope?
A:: Mobile endpoint security: mobile usage policies (BYOD/COPE/COBO/CYOD), risks + guidelines, management solutions (MDM/MAM/MCM/MTD/MEM/EMM/UEM), general best practices, Android + iOS specific security.
#flashcard
Q:: Mobile management stack hierarchy?
A:: MDM → MAM → MCM → MTD → MEM; EMM = comprehensive (MDM+MAM+MTM+MCM+MEM); UEM extends MDM+EMM to all internet-enabled devices via a single interface.
#flashcard
Q:: Favorite crackable exam items?
A:: Approach definitions + COPE/CYOD/COBO traits · 5-step implementations · risk categories · MDM delivery methods + features · Intune MAM-WE · MCM multi-client/multi-site · MTD levels · EMM deploy phases · UEM per-app VPN · Find My Device prerequisites/actions · Android Device Admin policies (wipe, disable camera 4.0, complex 3.0) · iOS Alpine + Lost Mode.
#flashcard