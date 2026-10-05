---

type: note
module: "07"
lo: "03"
tags: [concept, tool, process, mod/07]
topic: "MEM, EMM, and UEM Solutions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# MEM, EMM, and UEM Solutions (§7.3)

## Mobile Email Management (MEM)
- Ensures security of the **corporate email infrastructure + data** on mobile devices
- Allows: controlling devices that access emails · data-loss prevention · strict compliance policies · encrypting sensitive corporate data

### MEM key features
- **Preconfigure email on devices remotely (MDM):** create email accounts via email policy; set email signature + default account
- **Ensure only approved apps/devices access email (MDM):** extra encryption layer via **S/MIME MDM** · **SCEP** (Simple Certificate Enrollment Protocol) for iOS + Windows to secure email with certificates
- **Prevent unauthorized access of email attachments:** secure attachments in transit + after download; secure viewing/storage in built-in document viewer of MEM/MDM apps; restrict sharing to other devices/cloud
- **Pre-install the email client:** managed app configs customize/distribute/preconfigure (account type, domain, signature) + app permissions

### MEM examples
- **ManageEngine Mobile Device Manager Plus MSP** (configure/secure/manage corporate mobile email)
- **42Gears MEM** (control device email access, data-loss prevention, compliance, encryption)
- **Hiver** (email, live chat, knowledge base, voice inside Gmail; end-to-end accountability for incoming mail)

## Enterprise Mobility Management (EMM)
- **EMM is a comprehensive solution for MDM, MAM, MTM, MCM, and MEM** — safeguards enterprise data accessed/used by employee mobile devices

### EMM responsibilities
- **Device management** (foundation): automatic device configuration · productivity on preferred devices · **selective wipe** of enterprise data without touching personal data · secure/manage across multiple OSes (Android, iOS, macOS, Windows 10)
- **Content management:** encrypt email attachments · **DLP controls** · content-level policies for corporate-data distribution (device-independent encryption keys, authentication, file sharing)
- **Application management:** protect apps on any device · enterprise app store · end-user device authentication · separate business/personal apps
- **User and identity management**
- **Mobile threat management** (threats on iOS/Android)
- **MEM** (corporate email infrastructure + data)

### EMM deployment process (4 phases)
1. **Plan:** understand EMM requirements from org perspective + stakeholder feedback (employee expertise · mobile OSes/device support · network complexity · IT governance framework/policies/process · employee training resources · org security requirements)
2. **Design:** define mobility policies → define **roles** (admin tasks + admins) · define **visibility** (admin → device access) · assign **actors** (actions per admin) · manage **distribution** (apps/policies/configs, users, timing)
3. **Deploy:** choose cloud-based or on-premise approach; examine pricing models (subscription rate vs perpetual licensing)
4. **Implement:** prepare the helpdesk — train on devices/servers/network issues · define troubleshooting/escalation/responsibilities · provide resources · educate on device upgrades

### EMM implementation considerations
Understand requirements · understand end users + IT infrastructure · decide deployment approach · total cost · infrastructure suitability · select EMM vendor · manage IT/helpdesk change · design EMM policies · end-user training · actionable timeline + launch

### EMM examples
- **ManageEngine Mobile Device Manager Plus** — smartphones, tablets, laptops, desktops, TVs, rugged devices; Android, iOS, iPadOS, tvOS, macOS, Windows, Chrome OS
- **42Gears MEM** — email access control, data-loss prevention, compliance, encryption
- **Scalefusion EMM** — perimeter-less mobility strategy; Pervasive Windows OS + device management agility

## Unified Endpoint Management (UEM)
- UEM = remote **provisioning, managing, controlling, + securing** internet-enabled devices (mobiles, desktops, apps, content) from a **single interface**; extends **MDM and EMM**

### UEM features/capabilities
- Remote/manual/automatic **pushing of updates** · on-device security policy configuration · support employee-owned devices · **remote erase** of lost/stolen device data · device-usage tracking · threat detection + mitigation · **API framework** for custom apps
- App containerization · multi-OS environment · closed-loop automation · **certificate-based identity management** · security for enterprise email/apps/content · self-service IT features · **DLP (open-in + copy/paste)** · policy compliance · secure multi-user profiles (shared device) · security invisible to end users · **per-app VPN** (corporate access for authorized apps only) · find/install critical apps · separate sensitive personal + corporate data

### UEM components
- **CMT:** IT infrastructure for efficient mobile enterprise operation + end-user service
- **MDM (foundation):** secure corporate email · certificate-based security · automatic device configuration · productivity on preferred devices · selective wipe · multi-OS management (Android, iOS, macOS, Windows 10)
- **MAM:** protect apps · enterprise app store · end-user authentication · separate business/personal apps
- **MCM:** encrypt email attachments · DLP controls · content-level distribution policies (device-independent keys, authentication, file sharing)

### UEM examples
- **Scalefusion UEM:** secures/manages endpoints (tablets, smartphones, digital signages, rugged devices); API for custom management
- **Ivanti Unified Endpoint Manager:** discovers everything touching the enterprise network · automates software delivery · reduces login-performance issues · integrates with multiple IT solutions
- **Workspace ONE UEM (VMware):** powered by **AirWatch**; modern OTA management; cost reduction + security at each layer

## Stack summary
```
MDM → deploy/secure/monitor/manage devices
MAM → manage + distribute enterprise apps
MCM → secure access to corporate content
MTD → threat defense (extends EMM/MDM)
MEM → secure corporate email
EMM = MDM + MAM + MTM + MCM + MEM  (comprehensive)
UEM → single-interface mgmt (extends MDM + EMM; covers desktops too)
```






