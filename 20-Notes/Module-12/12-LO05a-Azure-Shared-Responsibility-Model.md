---
type: note
module: "12"
lo: "05"
tags: [concept, policy, mod/12, flashcard/12]
topic: "Azure shared responsibility model"
exam_weight: unknown
status: done
unresolved:
  - "p157 Figure 'Understand Azure's Shared Responsibility Model' is a coloured grid: the row labels and the three legend bands OCR cleanly (Always Retained by Customer / Responsibility Varies by Service Type / Responsibility Transfers to Cloud Provider) but the per-cell check marks are graphic and did NOT OCR. No cell is asserted from the figure; the whole matrix below is taken from the p157-p158 prose, which is where the colour coding is restated in words."
  - "p157/p158 prose names the bottom layer 'physical data' while the p157 figure row label prints 'Physical Data Center'. Both printed forms are kept; they are not assumed to be the same row."
  - "p156 lists seven LO#05 areas; only area 1 (shared responsibility) is covered here. The other six (IAM, encryption/keys, data at rest and in transit, network security, data storage security, monitoring and logging) are stated on p156 but their content is outside this page range."
  - "p157 sentence 'Because the customer owns the data and identities, it is the responsibility of the customer to secure the data and identities' is printed inside the SaaS paragraph only; the courseware does not restate it for PaaS/IaaS. It is not generalised to the other service models here."
---

[[MOC-Module-12]]

# Azure Shared Responsibility Model (§12.05)

> **LO#05: Security in Microsoft Azure Cloud** — "The objective of this section is to explain the
> various security features provided by the Microsoft Azure Cloud." _(Mod 12 p156)_
> **Area 1 of 7.** Covers pp. 156–158.

## The seven LO#05 areas _(Mod 12 p156)_

1. Azure shared responsibility model
2. Azure IAM features and best practices to securely implement IAM
3. Azure encryption and key management features
4. Encryption of data at rest and data in transit and managing the encryption keys
5. Implementation of Azure network security measures
6. Azure data storage security features
7. Azure monitoring and logging features

## Model rule _(Mod 12 p157)_

- "In the Microsoft Azure shared responsibility model, the customers and Microsoft Azure service
  providers **share various responsibilities** depending on the **cloud service model
  (IaaS, PaaS, SaaS, or on-premise data center)**."
- Shared-responsibility items listed on the slide: data classification and accountability · client
  and endpoint protection · identity and access management · application-level controls · network
  controls · host infrastructure · physical security. _(p157)_

## Layer × service model

Figure row labels and the prose agree on the layer stack. Matrix below is built **only** from the
p157–p158 prose (see `unresolved:` on the figure cells). _(Mod 12 pp157–158)_

| Layer (figure row) | SaaS | PaaS | IaaS | On-premises |
|---|---|---|---|---|
| Information and Data | Customer | Customer | Customer | Customer |
| Devices (Mobile and PCs) | Customer | Customer | Customer | Customer |
| Account and Identities | Customer | Customer | Customer | Customer |
| Identity and Directory Infrastructure | **Shared** | **Shared** | Customer | Customer |
| Applications | Provider | **Shared** | Customer | Customer |
| Network Controls | Provider | **Shared** | Customer | Customer |
| Operating System | Provider | Provider | Customer | Customer |
| Physical Hosts | Provider | Provider | Provider | Customer |
| Physical Network | Provider | Provider | Provider | Customer |
| Physical Data *(figure prints "Physical Data Center")* | Provider | Provider | Provider | Customer |

Legend bands as printed: **Responsibility Always Retained by Customer** · **Responsibility Varies
by Service Type** · **Responsibility Transfers to Cloud Provider**. _(p157)_

## Per-model statements, as printed _(Mod 12 pp157–158)_

**SaaS** _(p157)_ — customer retains information and data, devices (mobile and PCs), accounts and
identities. Provider owns completely: applications, network controls, operating systems (OSes),
physical hosts, physical network, physical data. Identity and directory infrastructure is
**shared**. "Because the customer owns the data and identities, it is the responsibility of the
customer to secure the data and identities."

**PaaS** _(pp157–158)_ — customer owns information and data, devices (mobile and PCs), accounts and
identities. Provider retains completely: OS, physical hosts, physical network, physical data.
**Shared**: identity and directory infrastructure, applications, network controls.

**IaaS** _(p158)_ — customer **completely retains** information and data, devices (mobile and PCs),
accounts and identities, identity and directory infrastructure, applications, network controls, OS.
Provider owns physical hosts, physical network, physical data center.

**On-premises** _(p158)_ — "All responsibilities are retained by the customer."

## Exam angles

- Physical layers (hosts / network / data) are **never** the customer's job above on-premises.
- **Applications** are the pivot row: provider-only → shared → customer as SaaS → PaaS → IaaS.
- Identity and directory infrastructure follows the same shared → customer path.
- On-premises is the only model where the customer holds *every* layer.

Generic model: [[12-LO02a-Cloud-Security-Shared-Responsibility]] ·
AWS variant: [[12-LO04a-AWS-Shared-Responsibility-Models]]

## Cards

Which layers does the Azure service provider own completely under SaaS?
?
Applications · network controls · operating system · physical hosts · physical network · physical data

Which Azure service model has the customer completely retaining identity and directory infrastructure, applications and network controls?
?
IaaS — plus information and data, devices, accounts and identities and the OS; the provider keeps only physical hosts, physical network and physical data center

What is shared between the customer and Azure under SaaS?
?
Identity and directory infrastructure — only; data, devices and identities stay with the customer, applications/network/OS/physical layers go to the provider

Under PaaS, which layers are shared between customer and Azure?
?
Identity and directory infrastructure · applications · network controls

What is the responsibility split under the Azure on-premises data center model?
?
All responsibilities are retained by the customer

Shared responsibility items enumerated by the Azure courseware
?
Data classification and accountability · client and endpoint protection · identity and access management · application-level controls · network controls · host infrastructure · physical security
