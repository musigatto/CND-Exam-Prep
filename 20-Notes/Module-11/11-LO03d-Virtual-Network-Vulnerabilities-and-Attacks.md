---
type: note
module: "11"
lo: "03"
tags: [threat, mod/11, flashcard/11]
topic: "Virtual Network Vulnerabilities and Attacks"
exam_weight: unknown
status: done
unresolved:
  - "p32 printed table 'Vulnerabilities: Virtual Networks' is flattened by OCR: the columns (Threat | Weakness | Consequence) and the cell-to-row adjacency could not be mapped cell-for-cell. The table below is built from the p33 narrative; only p32 consequence cells confirmed by that narrative are attached to a row."
  - "p32 third-column header OCRs as 'Vulnerability Enables'; the printed header is taken as 'Consequence' from the table's own framing - the exact printed header wording is uncertain."
  - "p32 Disruption weakness cell 'Resource-management error, Improper Access control' has no matching description bullet in p33; which p33 bullet, if any, belongs to it is not stated in recoverable text."
  - "p33 bullet 'Software-controlled latency over virtualized networks may result in DoS at the network-level' names no weakness; the p32 weakness cell it pairs with cannot be identified."
  - "p32 consequence cell 'Access of physical network' (Disclosure block) has no counterpart in the p33 narrative; it may belong to either Disclosure row - placement unstated."
  - "p32 Disruption consequence cells 'Denial of service' and 'Denial of service (DoS)' are near-duplicates; which one belongs to Improper Validation, and whether the other belongs to a different Disruption row, is not recoverable."
---

[[MOC-Module-11]]
# Virtual Network Vulnerabilities and Attacks (§11.03)

## Table shape _(Mod 11 p32)_

- p32 framing: "The following are some of the threats, weaknesses, and vulnerabilities found in virtual networks."
- **Four threat classes:** `Disclosure` · `Deception` · `Disruption` · `Usurpation` _(p32 header)_
- Columns: **Threat | Weakness | Consequence**.
- Same shape as the hypervisor/VMM weakness analysis earlier in the LO: classified by **potential threat × weakness**. _(p32)_

## Disclosure _(Mod 11 p32–p33)_

| Weakness | Vulnerability / consequence |
|---|---|
| **Information management errors** | Uncontrolled handling of **sequential requests for virtual networks** → **reconstructing the physical topology of the underlying network** and **network topology poisoning attacks** |
| **Information management errors + improper access control** | **Inspecting virtual network traffic** or **accessing a virtual router** → attackers obtain **critical routing information from the virtual network** |

## Deception _(Mod 11 p32–p33)_

| Weakness | Vulnerability / consequence |
|---|---|
| **Injection** (injection of malicious messages) | Messages injected so other entities **believe they originate from a legitimate entity in the network** → **identity fraud** |
| **Information management errors + data handling** | **Rollback of networking activity logs stored in a VM** → loss of network entity activities → **impacts the non-repudiation of actions** |

## Disruption _(Mod 11 p32–p33)_

| Weakness / cause | Vulnerability / consequence |
|---|---|
| *weakness not stated* — **software-controlled latency** over virtualized networks | **DoS at the network level** |
| **Insufficient verification of data authenticity** | **Misbehaving virtual routers resend old control messages repeatedly → reply attacks → corruption of the data plane + DoS** |
| **Resource management error** | **Uncontrolled allocation of resources of different virtual networks on the same substrate** as the physical network → **degradation of performance** |
| **Improper validation** | DoS via **incorrect throwing of exceptions** when handling **malformed, truncated, or maliciously crafted packets** |

## Usurpation _(Mod 11 p32–p33)_

| Weakness | Vulnerability / consequence |
|---|---|
| **Injection** | Malicious messages injected **from a fake source with high privileges** → **privilege escalation** |
| **Privileges and permissions** | Improper handling of **identities and associated privileges** → **controlling virtual network nodes** like **virtual routers** |
| **Credentials management** | Accessing the **network management console** by **brute-force password guessing** → attacks on the network |

## Weakness → threat index _(Mod 11 p32)_

| Threat | Weakness cells |
|---|---|
| Disclosure | Information management errors · Information management errors + improper access control |
| Deception | Injection · Information management errors + data handling |
| Disruption | Resource-management error + improper access control · Insufficient verification of data authenticity · Resource management error · Improper validation |
| Usurpation | Injection · Privileges and permissions · Credentials management |

**Exam trap:** `Injection` appears under **both** Deception and Usurpation — same weakness, different stated outcome (**identity fraud** vs **privilege escalation**). _(p32–p33)_

Countermeasures for this material: [[11-LO03g-Virtual-Network-Security]].

## Cards

List the four threat classes the courseware uses to classify virtual network vulnerabilities.
?
Disclosure, Deception, Disruption, Usurpation. _(Mod 11 p32)_

Insufficient verification of data authenticity in a virtual network: what does it produce?
?
Misbehaving virtual routers repeatedly resend old control messages (reply attacks), corrupting the data plane and causing DoS. _(Mod 11 p32–p33)_

Why does rollback of networking activity logs stored in a VM matter (Deception)?
?
It causes the loss of network entity activities and subsequently impacts the non-repudiation of actions. _(Mod 11 p32–p33)_

Improper validation in a virtual network: how is the DoS produced?
?
Incorrect throwing of exceptions when handling malformed, truncated, or maliciously crafted packets. _(Mod 11 p33)_

Usurpation: give the three weakness and effect pairs.
?
Injection -> privilege escalation; privileges and permissions -> controlling virtual network nodes like virtual routers; credentials management -> brute-force password guessing against the network management console. _(Mod 11 p33)_

Which weakness sits under both Deception and Usurpation, and how do the effects differ?
?
Injection. Deception: messages made to look as if from a legitimate entity -> identity fraud. Usurpation: messages from a fake source with high privileges -> privilege escalation. _(Mod 11 p32–p33)_
