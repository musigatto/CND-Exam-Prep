---
type: note
module: "11"
lo: "04"
tags: [threat, mod/11, flashcard/11]
topic: "SDN Vulnerabilities and Attacks"
exam_weight: unknown
status: done
unresolved:
  - "Table 11.1 row boundaries: the OCR text run on pp.68-70 interleaves the 'Category of Attack' and 'Type of Attack' columns (labels like 'Data Leakage', 'Denial of Service' appear in the type stream and vice-versa), so the exact cell-to-layer mapping of Table 11.1 is not recoverable. Only the Data Layer group and the column vocabularies are reconstructed; the remaining layer groups are listed as observed tokens, not asserted mappings."
  - "Table 11.1 category label printed as 'System-Level SDN Security' — reproduced verbatim; the intended phrase (possibly 'system-level security') is not certain."
  - "The p.68 figure 'SDN-Specific Vulnerabilities and Attacks' did not OCR in reading order: its attack labels are scattered across the Application Plane / Northbound API / Control Plane / Southbound API / Data Plane boxes and several tokens are cut off ('Lack of standar', 'Configuratim conflicts', 'Njacking c anprmnise', 'Lack of accountabil-'). Only unambiguous terms are reproduced; garbled fragments are omitted rather than guessed."
  - "The category token 'Data Leakage State' on p.69 is not resolved — it may be a splice of 'Data Leakage' with a following cell."
---

[[MOC-Module-11]]
# SDN Vulnerabilities and Attacks (§11.04)

## Limitations (p67)

- **SDN changes the entire network security model.**
- The **overlay and encapsulation techniques of SDN are incompatible with current security tools**.
- **Lacks physical access** — the SDN security model differs from the traditional one *as it lacks physical access*.
- **Increased potential for Denial of Service** — SDN technologies are vulnerable to various attacks like DoS.
- Implementing the SDN protocol and SDN controller **requires reconfiguration of the network infrastructure**.
- Requires **new tools and trained employees** to use them.
- SDN is virtual and **lacks the security that the router, switches, and firewalls provide**.
- SDN security risks are **distributed across the control and data plane**. _(Mod 11 p67)_

### Security limitations by layer

| Layer | Limitation |
|---|---|
| Data Plane | Insecure implementation of the management application |
| Control Plane | Potential for compromise of the control of network flow |
| Application Plane | No proper authentication mechanism for the application to access the control plane |

_(Mod 11 p67)_

- Insecure implementation of applications for managing the **data plane** → vulnerable to attacks like **DDoS** and **side-channel** attacks.
- The **controller must be fully secured** — a compromised controller leads to various security loopholes. _(Mod 11 p67)_

## Table 11.1 — SDN-Specific Vulnerabilities and Attacks

"**The SDN architecture layers are the most common targets of various attacks.**" _(Mod 11 p68)_

### Column vocabularies (as printed)

| SDN Layer | Category of Attack | Type of Attack |
|---|---|---|
| Application Layer | Unauthorized Access | Unauthorized/Unauthenticated Application Attack |
| Application-Control Layer Interface | Malicious/Compromised Application | Fraudulent Rule Insertion |
| Control Layer | Configuration Issues | Lack of TLS Adoption |
| Control-Data Interface | Policy Enforcement | Lack of Secure Provisioning |
| Data Layer | Data Leakage / Data Modification / Denial of Service / Configuration Issues / System-Level SDN Security | *see table below* |

_(SDN Layer and Category values as printed, pp.68–70)_

### Reconstructed — Data Layer rows

| Category of Attack | Type of Attack |
|---|---|
| *(not recoverable)* | **Credential Management** (Keys, Certificates for each Logical Network) |
| | **Forwarding Policy Discovery** (Packet Processing Timing Analysis) |
| | **Flow Rule Modification to Modify Packets** (Man-in-the-Middle attack) |
| | **Controller-Switch Communication Flood** |
| | **Switch Flow Table Flooding** |
| | **Lack of TLS Adoption** |
| | **Lack of Secure Provisioning** |
| | **Lack of Visibility of Network State** |
| **Data Modification** | |
| **Denial of Service** | |
| **Configuration Issues** | |
| **System-Level SDN Security** | |

_(Mod 11 p69, p70)_

Other `Type of Attack` tokens appearing in the same run, layer not recoverable:
`Unauthorized Controller Access/Controller Hijacking` · `Flow Rule Discovery (Side-Channel Attack on Input Buffer)` · `Lack of Visibility of Network [State]` (Control-Data Interface) · `Malicious/Compromised Applications` _(Mod 11 pp68–70)_

### p68 figure — attack vocabulary (order scrambled, not mappable to a plane)

Man-in-the-middle attack · Flow rule injection · Faked controller · Malicious flow attack · Fraudulent flow rules insertion · Flow rule manipulation · Device attack · Protocol attack · Side channel attack · Compromised controller · Storage attack · Storage data tampering · Control message attack · Access control attack · Code injection · Resource attack · Network manipulation · Core services manipulation · Interception attack · Eavesdropping attack · Availability attack · Flooding attacks · Scalability and availability · Data leakage · TCP-level attack · ARP spoofing · LLDP spoofing · Configuration conflicts _(Mod 11 p68)_

## Attacks by component impacted

"Based on the components impacted, SDN attacks are broadly classified into the following types." _(Mod 11 p70)_

### Data Plane — 3 attacks

| Attack | Target |
|---|---|
| **Device Attack** | Software or hardware vulnerabilities of the **SDN switch** — software bugs such as **firmware attacks**, or hardware features such as the **ternary content-addressable memory (TCAM)** |
| **Protocol Attack** | Network **protocol** vulnerabilities of the forwarding device |
| **Side Channel Attack** | Deduces the network **forwarding policy** from the **performance metrics** of the forwarding device |

_(Mod 11 p70)_

### Southbound API — 3 attacks

| Attack | Effect |
|---|---|
| **Interception Attacks** | Adversary targets network **behavior** by **modifying the exchanged messages** |
| **Eavesdropping Attacks** | Attacker targets the information exchanged between the **control and data plane** |
| **Availability Attacks** | Numerous requests → **failure in the implementation of network policy** |

_(Mod 11 p70)_

### Control Plane — 3 attacks

| Attack | Effect |
|---|---|
| **Manipulation Attack** | Targets the **controller's understanding of the data plane** → improper decision making |
| **Availability Attack** | Controller unavailable for a period for part or all of the network — e.g. numerous **unauthenticated packet-in messages** to the controller |
| **Software Hack** | Controller is hosted on a **commodity server**; e.g. **altering a system variable like time** may take the controller offline |

_(Mod 11 p70, p71)_

### Northbound vs Southbound API

Northbound is compromised through **interception, eavesdropping and availability attacks**; the southbound through **other kinds of malicious attacks and standardization issues**. _(Mod 11 p71)_

| # | Difference |
|---|---|
| 1 | Attacking the **northbound** API requires **high-level of access** and operates in the **application plane** |
| 2 | Info exchanged between application plane and control plane **affects network policies** → impact of a compromised **northbound** layer is **potentially higher** than a compromised southbound API |
| 3 | **OpenFlow** is the standard protocol for the **southbound** API; the **northbound API lacks any standards** |

_(Mod 11 p71)_

### Application Plane — 4 policy attacks

| Attack | Target |
|---|---|
| **Storage Attack** | Access privilege of SDN applications to **shared storage** |
| **Control Message Attack** | A **malicious application** targets network control by sending control messages |
| **Resource Attack** | System resources such as **memory and CPU** — degrades performance of the application and controller |
| **Access Control Attacks** | The **controller** when there is improper enforcement of control over **authentication, authorization, and accountability** |

_(Mod 11 p71)_

**Controller** — policy attacks to compromise the controller are executed through **malicious actions and configuration conflicts**. _(Mod 11 p71)_

## Cards

SDN data plane — the three major attacks
?
Device Attack (SDN switch software/hardware vulns: firmware, TCAM) · Protocol Attack (network protocol vulns of the forwarding device) · Side Channel Attack (deduce forwarding policy from performance metrics)

SDN control plane — the three major attacks
?
Manipulation Attack (controller's understanding of the data plane) · Availability Attack (e.g. numerous unauthenticated packet-in messages) · Software Hack (commodity server; e.g. altering a system variable like time)

SDN southbound API — the three major attack types
?
Interception Attacks (modify exchanged messages) · Eavesdropping Attacks (info between control and data plane) · Availability Attacks (numerous requests fail network policy implementation)

Why is a compromised northbound API worse than a compromised southbound API?
?
The data exchanged between application plane and control plane affects network policies, so impact is potentially higher; also OpenFlow standardises the southbound API whereas the northbound API has no standard

SDN application plane — policy attacks
?
Storage Attack · Control Message Attack · Resource Attack · Access Control Attacks

SDN security limitation per layer (p67 figure)
?
Data Plane: insecure implementation of the management application. Control Plane: potential for compromise of the control of network flow. Application Plane: no proper authentication mechanism for the application to access the control plane
