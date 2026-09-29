---

type: note
module: "07"
lo: "03"
tags: [concept, tool, process, policy, mod/07, flashcard/07]
topic: "Mobile Device Management (MDM) Solutions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# Mobile Device Management (MDM) Solutions (§7.3)

- **MDM** = deploy, secure, monitor, and manage company- and employee-owned devices
- Network defenders use the **MDM server management console** to remotely configure the **MDM agents** installed on the devices
- Gains importance with BYOD adoption; reduces support costs, mitigates security risks, reduces business discontinuity

## MDM Solution Features
- Security management · device configuration management · device inventory + tracking · over-the-air (OTA) application distribution · enterprise policy management · password enforcement · data encryption enforcement · enterprise network integration · remote data wipe · blacklisting/whitelisting apps and devices

## Delivery Methods
| Method | Apt for |
|---|---|
| **Premise-based** | High control · reliable IT skills/resources · direct control of security/administration · can bear larger up-front investment |
| **SaaS-based** | No servers on site but still want management/admission; mitigate up-front cost; pay monthly/annual fees |
| **Managed services-based** | Organizations lacking expertise/over-extended; support without draining internal resources; regular status reports (roll-outs, software/hardware updates, asset/inventory control) |

## MDM Deployment — Key Considerations
- **Well-defined policy** (management direction + support for IT/information security)
- **Periodic risk assessment** (risk mgmt: extra controls for high risk; minimal for low/non-existent risk)
- **Configuration management:** automatic config of device settings (password policy, email, Wi-Fi, VPN) — prevents user error, reduces misconfiguration vulnerabilities, role-based lockdown
- **Test mobile apps separately** before OTA distribution; whitelisting/blacklisting via software distribution + configuration management
- **Procurement terms/conditions** in policy + employee agreements (HR + legal): expense compensation · employee privacy policy · shared responsibility for device/content security + misuse · secure wipe incl. personal data on loss/theft
- **Policy compliance + enforcement:** asset-based inventory (corporate/regulatory mandates) · jail-broken/rooted device detection · encryption · privacy-based separation of corporate vs personal content
- **Enterprise activation/de-activation** (connect mobile devices to org network; reduces provisioning burden)
- **Asset disposition (de-commission):** notify inventory management → generate user receipt → accept user acknowledgment · de-commissioning = secure wipe of corporate data, hand device to employee without touching personal data, log user activity per local laws

## Security Settings
- **User security:** encryption, authentication, lock code, selective wipe (when remote wipe issued)
- **Data security:** wipe corporate/private data if device lost/stolen

## MDM Implementation Challenges
- Cost-prohibitive if BYOD defined improperly/enforced ineffectively
- False positives / many false negatives if policies poorly defined → reduced morale + confusion
- Unawareness → employees freely share devices → data breach
- Damage by close associates (identity theft/fraud) → consequences up to job dismissal
- Social engineering → unaware employee shares org data

## Selecting an MDM — Factors
- **Custom app store:** install custom/unapproved apps + company-app-store experience
- **Application security:** built-in malicious-app scanning
- **Browser security:** filtered mobile web browsing
- **Encryption levels:** entire device vs company-specific/selected files+folders
- **Data wiping:** selective wipe support
- **Auto-provisioning** of devices
- **Architecture:** sandbox, virtualization, or integrated approach
- **Location capabilities + network access restrictions**
- **Inventory management:** search/filter/modify individual endpoints (hundreds of devices)
- **Reports:** new devices, out-of-compliance apps, devices not checked-in for days

## MDM Solution Examples
- **VMware Workspace ONE:** intelligence-driven digital workspace; MDM + secured app access + reporting/automation; add devices quickly, deploy from one console, OTA updates/config, remote wipe/lock
- **IBM MaaS360:** complete MDM lifecycle (iPhone, iPad, Android, Windows Phone, BlackBerry, Kindle Fire); integrated cloud platform
- **XenMobile (Citrix):** role-based management/config/security; blacklist/whitelist apps, detect jailbroken/out-of-compliance devices (+ block ActiveSync email access), full or selective wipe
- **Absolute Manage MDM:** zero-touch IT asset management, self-healing endpoint security, always-on data visibility
- **Sicap DMC:** auto-detects new devices + real-time config; white-labeled web tool/mobile apps; DMC analytics
- **SOTI MobiControl:** remote control, helpdesk, location, AV/malware protection, provisioning, asset management
- **Scalefusion MDM:** multi-OS mgmt; integrated with Eva Communication Suite
- **ManageEngine Mobile Device Manager Plus:** iOS, Android, Windows, macOS, Chrome OS
- **MobileIron MDM:** enrollment, automated setup, access control, secure connectivity, compliance, policy enforcement
- **MediaContact (Telelogos):** Windows, Windows Mobile, Android (laptop PCs, smartphones, tablets, rugged, embedded)
- **Beachhead SimplySecure:** remote enforcement, full encryption, instant admin-enabled remote restoration, complete data wipe, threat responses
- **Microsoft Intune:** manage iOS/Android/Windows/macOS securely · device/app compliance · org-data-safe policies (org-owned + personal) · single unified solution for devices/apps/users/groups · control access/share of data

## Cards
MDM in one line?
?
Deploy, secure, monitor, and manage company/employee-owned devices via an MDM server management console + MDM agents on the devices.

MDM delivery methods?
?
Premise-based (high control, larger up-front) · SaaS-based (no on-site servers, monthly/annual fees) · managed services-based (orgs lacking expertise; status reports provided).

MDM key feature list?
?
Security mgmt · device config mgmt · inventory/tracking · OTA app distribution · enterprise policy mgmt · password enforcement · data encryption enforcement · network integration · remote data wipe · blacklisting/whitelisting.

MDM selection factors (short list)?
?
Custom app store · application security scanning · browser filtering · encryption levels · selective wipe · auto-provisioning · architecture (sandbox/virtual/integrated) · inventory + reports.

Example MDM vendors?
?
VMware Workspace ONE, IBM MaaS360, XenMobile, Absolute, Sicap DMC, SOTI MobiControl, Scalefusion, ManageEngine, MobileIron, MediaContact, Beachhead SimplySecure, Microsoft Intune.
