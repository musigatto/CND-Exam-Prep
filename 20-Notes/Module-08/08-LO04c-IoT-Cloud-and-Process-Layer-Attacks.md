---

type: note
module: "08"
lo: "04"
tags: [threat, process, mod/08]
topic: "IoT Cloud and Process Layer Attacks & Countermeasures"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Cloud & Process Layer Attacks + Countermeasures (§8.4)

## IoT Cloud / Process (Communication, Data Center) Layer — Attacks
| Attack | Vector |
|---|---|
| **Account/user/device theft** | stolen cloud credentials |
| **Data in transit/at rest compromise** | weak/missing crypto |
| **Key/certificate storage attacks** | steal keys/certs |
| **Malware injections** | software vulnerabilities |
| **Botnet attacks** | hijacked devices/cloud |
| **Backdoor/DoS/DDoS** | resource exhaustion |
| **Cloud access network bypass** | VPN/CORBA security gaps |
| **Aura jamming, LDoS aggressive traffic floods** | RF + large traffic DoS |
| **Uplink QoS mapping** | bypass node |
| **Cloud service interruption** | federation/availability flaws |
| **Hosted sensor network intruder** | compromised sensors |
| **Core network Internet transitivity** | poor carrier segmentation |
| **Process-layer weakness** | human error, poor policy, poor interfaces |

## IoT Cloud / Process Layer — Countermeasures
| Layer | Countermeasure |
|---|---|
| **Data Transit Protection** | TLS v1.2, IPSec, DTLS, ACLs for subnet firewalls, network redundancy |
| **Data at Rest Protection** | AES-256 (devices at rest often use RSA 2048/AES-256; TLS 1.2 across the web), HSM-based key management |
| **Cloud Access / platform protection** | mutual auth, HSM keys, secure onboarding, per-policy segmentation, secure BGP peering, RFC1918 routing filters |
| **Data, app, and command integrity** | digital signatures, hash-chain timestamping, event/command logging |
| **Endpoint (device) protection** | SELinux, container isolation, secure boot/OS integrity, software-defined perimeter (SDP) |
| **Process layer security** | governance/policies, audit programs, user training, incident response, continuous improvement |

## IoT Attack Surface — Additional Vectors
- **Account/user/device theft (cloud)**, **data in transit/at rest compromise**, **key/certificate storage attacks**
- **Backend data moved over bleeding-edge encryption**
- **Mirai botnet** exploits default credentials in IoT devices
- **Cross-site scripting (XSS)** on IoT control dashboards; insecure web interfaces → command injection





