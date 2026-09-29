---
type: note
module: "07"
lo: "02"
tags: [concept, threat, mod/07]
topic: "Enterprise Mobile Security Risks and Challenges"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# Enterprise Mobile Security Risks and Challenges (§7.2)

Mobile use in work environments changed organizational security; on top of device-level risks (weak security systems, insufficient configuration) enterprises face extra challenges in **four categories**.

## Risk/Challenge Categories
### 1. Physical risks and challenges
- Devices lost/stolen because portable + lightweight
- Attacker with physical access can **flash the device with a malicious system image**, connect to a computer to install malicious app, or extract data
- Mitigations: never leave unattended · enforce **device authentication + encryption** · **multiple forms of authentication** (not just a simple password)

### 2. Network-based risks and challenges
- Wi-Fi/Bluetooth connectivity → vulnerable to **wireless eavesdropping**
- Mitigations: connect to trusted networks with **WPA2** · secured protocols (**IPSec, SSL, SSH, HTTPS, Kerberos**) · special gateways with customized firewalls/security controls to direct mobile traffic (**content filtering** + **DLP** tools)

### 3. System-based risks and challenges
- Manufacturers may introduce vulnerabilities unintentionally (e.g., **SwiftKey keyboards** or mobile OSes)
- Mitigation: update devices regularly to reduce threats

### 4. Application-based risks and challenges
- Vendors may not release timely app updates / support old OS versions; users may not update apps
- Attackers exploit app vulnerabilities to steal data, download other malware, or **control the device remotely** → financial loss + reputational risk
- Mitigations: strict controls on downloading/installing apps · mobile anti-virus · policies to limit/block third-party apps

## Risks Associated with BYOD, CYOD, COPE, and COBO (top 10)
1. **Sharing confidential data on unsecured networks** — public connections may not be encrypted → data leakage
2. **Data leakage + endpoint security issues** — mobile = insecure cloud-connected endpoint; lost device can expose all corporate data
3. **Improperly disposing of devices** — devices hold financial info, credit-card details, contact numbers, corporate data; wipe before disposal/handing over
4. **Supporting various devices** — employee-owned devices have limited cross-platform security; deters IT management/control
5. **Mixing personal and private data** — hard to isolate business vs personal use (compromised shopping sites, public Wi-Fi, lending the device)
6. **Lost or stolen devices** — corporate data on the device may be compromised
7. **Lack of awareness** — uneducated employees compromise corporate data on mobile devices
8. **Bypassing network policy rules** — wireless devices can bypass policies enforced only on wired LANs
9. **Infrastructure issues** — many platforms/technologies; IT struggles to support data, security, backup, compatibility across devices
10. **Disgruntled employees** — misuse corporate data, leak sensitive info to competitors

## Cards
Q:: Four enterprise mobile security risk categories?
A:: Physical (loss/theft, malicious flashing) · network-based (wireless eavesdropping) · system-based (vendor vulnerabilities like SwiftKey) · application-based (unpatched apps → malware/remote control).
#flashcard
Q:: MITM-risk mitigations for mobile networks?
A:: WPA2 + secured protocols (IPSec, SSL, SSH, HTTPS, Kerberos) + gateways with content filtering and DLP.
#flashcard
Q:: Name the 10 policy-related mobile risks?
A:: Unsecured-network sharing · data leakage/endpoint · improper disposal · supporting many devices · mixing personal/private data · lost/stolen devices · lack of awareness · bypassing network policy · infrastructure issues · disgruntled employees.
#flashcard