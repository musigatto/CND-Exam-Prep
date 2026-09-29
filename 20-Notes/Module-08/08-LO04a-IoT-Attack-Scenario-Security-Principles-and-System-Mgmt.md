---
type: note
module: "08"
lo: "04"
tags: [process, threat, concept, mod/08]
topic: "IoT Attack Scenario, Security Principles, and System Management"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# Security in IoT-enabled Environments — Scenario, Principles, Mgmt (§8.4)

## Attack Scenario in an IoT-enabled Environment
- **Attacker** (competitor/political opponent) targets **smart building** whose **CCTV/security system = connected IoT devices**
- **Attack path:** attacker → mobile device (smartphone/TV) → bypass/freeze front-end camera → computer vision system + object detection → AC/humidity sensors readings spoofed → plant discovery + damage → digital map of building + options for bad parties
- System components: CCTV + camera, computer vision algorithms, body/intrusion detection systems, object detection (daily pedestrian flow), AC + humidity sensors, front-end/back-end web apps controlling them, data center in cloud hosting plant discovery + digital mapping apps
- **Trust relationships + attack surface** expand across the ecosystem (user layer → gateway → cloud apps)

## Security in IoT-enabled Environments — Stack-wise IoT Security Principles (countermeasures per layer)
![IoT architecture last layer note]
| Layer | Recommended |
|---|---|
| **Device Layer (physical)** | tamper detection · encryption at rest · **TLS v1.2/v1.3** · authentication protocol (IoT-specific) |
| **Device Layer (operational)** | understand affected devices · segment: deblock RFC1918 source-address space · **Zero Trust** (per-device keys) · MFA · defensive coding · hardware-assisted roots of trust · memory encryption |
| **Communication Layer (edge)** | edge firewalls · IPsec **ESP** · traffic shaping (DNS, ICMP, ARP) · Out-Of-Band appliances (purple-patch tunneling) |
| **Communication/data layer (data center)** | routing plan (star/ring/mesh) · secure BGP peering · **route filtering** (RFC1918, invalid BGP) · traffic shaping · Secure DNS/CDN |
| **Communication/data layer (access)** | Figure-efficient secure **SSH** (SCP/SFTP) · HTTPS APIs · secure HSM/SSL key storage |
| **Cloud Platform Layer** | Security Information & Event Management (**SIEM**) · **IDPS** · security analytics · federated access/BYOK |

## IoT System Management (3 components)
### 1. Device Management
- Security: strong bootloader & installed-device identification
- **Provisioning setup pane:** MAC address + IMEI, geolocation (simplifies physical authentication), one-off tokens, push-button, context-based
- **Client-server architecture:** Security Services Interface (SSI) + connectivity connectivity broker (subscribes/publishes over MQTT)
- Server side: command line tool (netconf/restconf) from WSO2 IoT (Security Interfaces, Device Management, Identity Server)
- Client side: device onboarding + configuration download
### 2. User Management
- Access from mobile/web/wearable clients, 2FA (sso, oauth2.0, saml); password recovery
### 3. Security Monitoring
- **GE Predix** + **Bayshore Networks Remote Configuration** monitor device data/commands, threat intelligence

## Cards
Q:: IoT stack-wise security principle for device layer?
A:: Tamper detection, encryption at rest, TLS v1.2/1.3, IoT-specific authentication protocols; Zero Trust per-device keys.
#flashcard
Q:: Communication edge layer countermeasures?
A:: Edge firewalls, IPsec ESP, traffic shaping (DNS/ICMP/ARP), out-of-band appliances.
#flashcard
Q:: Cloud platform IoT countermeasures?
A:: SIEM, IDPS, security analytics, federated access / bring-your-own-key.
#flashcard
Q:: Example IoT attack scenario target?
A:: Smart-building CCTV/security system — attacker spoofs cameras and AC/humidity sensors, maps the plant, causes damage.
#flashcard
Q:: IoT system management components?
A:: Device management · user management · security monitoring.
#flashcard