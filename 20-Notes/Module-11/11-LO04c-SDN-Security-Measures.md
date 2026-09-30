---
type: note
module: "11"
lo: "04"
tags: [bestpractice, mod/11, flashcard/11]
topic: "SDN Security Measures"
exam_weight: unknown
status: done
unresolved:
  - "Vendor/product token on p.73 printed as 'WedgeTail' in the 'Implement an Intrusion Prevention System like WedgeTail for the data plane' bullet. Reproduced verbatim; the OCR may have garbled the product name - not corrected."
  - "Vendor/product token on p.76 printed as 'Fortnox' ('Implement Fortnox, an extension to the NOX controller. This provides non bypass flow rules'). Reproduced verbatim; the intended product spelling is not certain - not corrected."
  - "The p.76 figure 'SDN Attack-Specific Countermeasures' did not OCR in a stable reading order - its Attack/Mitigation cells are interleaved (e.g. 'Password Guessing or Brute e e e' is truncated, and 'Recognize 3 standard authorization levels among flow rule producers' is unanchored). Only the clean body-prose mitigation list on the same page is reproduced; the figure's full attack-to-mitigation cell mapping is omitted rather than guessed."
  - "p.74 bullet 'Avoid SDNS that use redundant controllers' - the acronym printed as 'SDNS' is reproduced as-is; whether it is an OCR artifact for 'SDN systems' is not certain."
---

[[MOC-Module-11]]
# SDN Security Measures (§11.04)

## Security principles (p72)

"Security principles to be applied to **all protocols, components, and interfaces** of the SDN architecture." _(Mod 11 p72)_

| Principle | Requirement |
|---|---|
| Clearly define **security dependencies and trust boundaries** | Define dependencies between SDN components, while specifying a security mechanism for SDN networks |
| Assure **robust identity** | Strong identity framework for secure authentication and authorization |
| Build security based on **open standards** | Open standards with proven protocols and methodologies for portability and interoperability |
| Protect the **information security triad** | Evaluate new controls → their impact on **confidentiality, integrity, availability** |
| Protect **operational reference data** | Reference data generated, processed, maintained and transported securely |
| Make systems **secure by default** | Controls provide security at **multiple levels**; address all requirements of potential system use cases |
| Provide **accountability and traceability** | All security controls, critical states and actions are **audited** |
| Consider properties of **manageable security controls** | When adding a control/standard, verify all its properties are aligned with the current system |

_(Mod 11 p72)_

## Measures by layer

"The layers of an SDN system must be secured to prevent exposing an organization to attacks." _(Mod 11 p73)_

### Application plane

- **Strengthen end-user security** by implementing **in-line mode security functions** in the application.
- Use **authentication and encryption** to secure communications from the applications and services that **request services or data from the controller**.
- **Northbound applications requesting SDN resources** should implement **secure coding practices**.
- **Secure public-facing Internet web applications**. _(Mod 11 p73, p74)_

### Data plane

- Implement the cryptographic **transport layer security (TLS)** protocol to authenticate and encrypt traffic between **network devices, SDN agents and the controller** — prevents **eavesdropping and spoofed southbound communications**.
- Figure spec: **TLS 1.2 (or UDP/DTLS)** between network device agent and controller.
- **Secure communication by selecting one of the available options based on the southbound protocol currently in use**, e.g.:
  - Use **protocols within TLS sessions**.
  - Use **shared secret passwords** or use **nonce** to **avoid replay attacks**.
  - Use **SNMPv3** instead of **SNMPv2c**.
  - Use **secured shell (SSH)** instead of **telnet**.
- Use **passwords and shared-secrets to authenticate tunnel endpoints**, and secure tunneled traffic based on the **data center interconnect (DCI)** protocol currently in use.
- **Separate protocol traffic from data flow** through an **out-of-band network** or security measures.
- Implement an **Intrusion Prevention System** like `WedgeTail` for the data plane. _(Mod 11 p73, p74)_

### Controller (control) plane

- Ensure the SDN systems permit configuration of **secure and authenticated administrator access** to the controller.
- Ensure controller administrators use **role-based access control (RBAC)** policies.
- Implement **logging and audit trails** to check for unauthorized changes made by administrators or attackers.
- Use a **high-availability (HA) controller architecture** if a risk of **DoS** attacks on the controller exists.
- **Avoid SDN systems that use redundant controllers** — this may enable an attacker to cause DoS in *all* controllers while leaving the attacker undetected.
- Figure spec: **certificates** to authenticate controller and network devices / SDN agents · **role-based access policies** · **harden host OS** to harden the controller and the network elements · **monitor controllers for suspicious activity** · **HA controller architecture**. _(Mod 11 p73, p74)_

### SDN layer

- Use an **out-of-band (OOB) network for control traffic** — a convenient and inexpensive protection measure for data centers. Using it for **northbound and southbound** communications secures the protocols for controller management.
- Use **TLS, SSH, or any other method** to protect northbound communications; **secure the management of the controller**.
- Use **OOB + secure protocols** for controller management and northbound communications; **TLS or SSH** for secure northbound communications and controller management.
- Use devices like **`FlowChecker`** to validate flows in network device tables **against controller policy** — they identify **malicious traffic** and any discrepancies that may be caused by an attack. _(Mod 11 p73, p74, p75)_
- **Separate the control protocol traffic and primary data flows** through an **OOB network**.
- **Authorize tunnel endpoints** and protect tunneled traffic using **DCI protocols**. _(Mod 11 p77)_

## Additional controller-restriction measures (p76)

| # | Measure |
|---|---|
| 1 | Establish a **secure channel between the switch and the controller** |
| 2 | Increase the use of **identification and authentication** |
| 3 | Use **audited and reviewed role-based access policies** consistently |
| 4 | Use **audited and reviewed configuration changes** regularly |
| 5 | **Monitor controllers for malicious activity** and implement **alerts to security staff** |
| 6 | Follow best practices for **hardening and patching**; otherwise **document, measure and approve the risk and its impact** |
| 7 | Prevent **DDoS** by implementing a **high-availability controller architecture** |
| 8 | Use **HA in the architecture to examine changes/updates in production**, with **immediate failover** if a change fails to function |
| 9 | Use **TLS/SSH (or UDP/DTLS)** to encrypt northbound communication |
| 10 | **Secure coding of northbound applications** |
| 11 | Use **authentication for northbound applications instead of default passwords** before they communicate with the controller |
| 12 | **Authenticate endpoints using TLS** for southbound communication |

_(Mod 11 p76)_

## Cards

Data plane — which protocol versions replace the insecure ones?
?
SNMPv3 instead of SNMPv2c; secured shell (SSH) instead of telnet; TLS 1.2 (or UDP/DTLS) between network device agent and controller

Data plane — anti-replay and tunnel options
?
Use protocols within TLS sessions · use shared secret passwords or use nonce to avoid replay attacks · use passwords and shared-secrets to authenticate tunnel endpoints and secure tunneled traffic with the DCI protocol in use

Controller layer — the five measures
?
Secure + authenticated administrator access · RBAC policies · logging and audit trails · HA controller architecture if DoS risk exists · avoid SDN systems with redundant controllers

Which two techniques protect the tunnel / control path?
?
Authorize tunnel endpoints and protect tunneled traffic using data center interconnect (DCI) protocols; separate control protocol traffic from primary data flows through an out-of-band (OOB) network

FlowChecker — what does it do?
?
Validates flows in network device tables against controller policy, identifying malicious traffic and discrepancies caused by an attack

Why avoid SDN systems with redundant controllers?
?
It may enable an attacker to cause DoS in all the controllers in the SDN system, while leaving the attacker undetected
