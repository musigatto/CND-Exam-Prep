---
type: note
module: "12"
lo: "04"
tags: [concept, policy, mod/12, flashcard/12]
topic: "AWS shared responsibility models"
exam_weight: unknown
status: done
unresolved:
  - "pp.40-43 present NO three-model taxonomy. The module summary elsewhere in the courseware claims AWS devised three shared responsibility models (infrastructure services, container services, abstract services); none of those three terms appear in this page range. What pp.41-43 actually present is ONE model (the AWS shared responsibility model) decomposed into TWO control types - Inherited Controls and Shared Controls - plus a SIX-item customer responsibility list. The three-model claim is not verifiable from this slice and is not asserted here."
  - "p41: 'Customers should perform all the required security configuration and management tasks if they select an Amazon IaaS (EC2, VP3, S3)'. The middle service token OCR's as 'VP3' and is not resolvable from the slice; reproduced as printed, not completed from outside knowledge."
  - "p41 figure 'Understanding AWS Shared Responsibility Model': the layer labels OCR'd but the horizontal boundary line / shading that separates the customer band from the AWS band is image-only. The band split reproduced below follows the printed prose lists on p41-p42 (AWS = global infrastructure + software; customer = the six items), not the unreadable shading."
  - "p41 prose: 'Constant IT maintenance and physical security protection ensure the security of the AWS infrastructure, which includes regional, available, and edge zones.' 'available' is printed as-is; the corresponding figure labels read Regions / Availability Zones / Edge Locations. The two readings are not reconciled by the courseware."
  - "p43 section 'Customer Specific' carries exactly one worked example (Service and Communication Protection / Zone Security). The remaining customer-specific control areas are not listed on p43."
---

[[MOC-Module-12]]

# AWS Shared Responsibility Models (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS).**
> Objective as printed: "The objective of this section is to explain the various security
> features provided by the Amazon cloud (AWS)." _(Mod 12 p40)_
> Section scope _(Mod 12 p40)_: AWS shared responsibility model · AWS IAM features and best
> practice to implement IAM securely · AWS encryption and key management features
> (encryption of data at rest and transit, and manage the encryption keys) · implement AWS
> network security measures · AWS data storage security features · AWS monitoring and
> logging features.
> **This note = area 1 of 6** (pp. 40–43).

## How many models does p40–43 actually present? _(Mod 12 pp40–43)_

- **One** model: the **AWS shared responsibility model** — "a model that distinguishes the
  security controls between the AWS and customers". _(p41)_
- Decomposed into **two** control types: **Inherited Controls** · **Shared Controls**. _(p42)_
- Plus a **six-item** customer responsibility list. _(p42)_
- **No** "infrastructure services / container services / abstract services" taxonomy appears
  anywhere in pp. 40–43 — see `unresolved:`. Do not answer "three models" from this page range.

> Core split: **"The customers decide the access levels he chooses to give from and to his
> resources, while AWS secures the cloud."** A good understanding of the model "enables the
> building and maintenance of a highly secure and reliable environment." _(p41)_

## The two bands _(Mod 12 p41)_

Figure title: *Understanding AWS Shared Responsibility Model*. Layer labels as printed,
band assignment per the p41–42 prose lists:

| Security **"in" the Cloud** — customer side | Security **"of" the cloud** — AWS side |
|---|---|
| Customer Data | Software |
| Platform, Applications, Identity and Access Management | Compute · Storage · Database |
| OS, Network, and Firewall Configuration | Hardware / AWS Global Infrastructure |
| Client-Side Data Encryption and Data Integrity Authentication | Regions · Availability Zones · Edge Locations |
| Server-Side Encryption (File System and/or Data) | |
| Network Traffic Protection (Encryption/Integrity/Identity) | |

_(Mod 12 p41)_

## AWS security responsibilities _(Mod 12 p41)_

"AWS is responsible for the security of the cloud infrastructure", comprising:

| AWS element | Printed statement |
|---|---|
| **Global Infrastructure / Hardware** | Constant IT maintenance and physical security protection ensure the security of the AWS infrastructure, which includes regional, available, and edge zones |
| **Software** | AWS security services — **encryption keys, network monitoring tools, database protection** — secure the computation, storage, database, and networking in the cloud |

_(Mod 12 p41)_

## Customer security responsibilities _(Mod 12 pp41–42)_

"Customers are responsible for the security of their specific instances and their
responsibilities are determined according to the **selected AWS cloud service**."
_(p41)_

| Customer responsibility | What it covers (as printed) |
|---|---|
| **Customer Data** | Securing the business data on the network **because they enter and exit** the cloud service |
| **Platform, Applications, Identity and Access Management** | Managing and securing the platforms running on the cloud, plus application maintenance and IAM |
| **Client-Side Data Encryption** | Using either an **AWS-managed encryption key** or a **personal key not provided by AWS** |
| **File System Encryption** | An independent protection system or file system protection to secure the customer data **at rest** |
| **Network Traffic Protection** | Guarantee the security of all traffic **entering and exiting** the server |
| **Service and Communication Protection** | Routing and **zoning** data within specific security environments |

_(Mod 12 p42)_

- Trigger printed: "Customers should perform all the required security configuration and
  management tasks if they select an Amazon IaaS (EC2, `VP3`*, S3)." *(p41)* — `*` see `unresolved:`

## Two control types _(Mod 12 p42)_

> "AWS provides customers with an infrastructure and the customers provide their own control
> implementation techniques under the AWS services." _(p42)_

| Type | Definition | Example |
|---|---|---|
| **Inherited Controls** | Controls **inherited completely** from AWS to its customers | Physical and Environmental controls |
| **Shared Controls** | Controls applied to **both** the infrastructure and the customer layers, with separate perspectives — AWS owns the infrastructure requirement, the customer implements their own control as part of using AWS services | Patch Management · Configuration Management · Awareness and Training |

_(Mod 12 p42–43)_

### The three shared controls, split _(Mod 12 pp42–43)_

| Shared control | AWS | Customer |
|---|---|---|
| **Patch Management** | Patching and fixing flaws **within the infrastructure** | Patching their **guest OS and applications** |
| **Configuration Management** | Configuring the **infrastructure devices** | Configuring their **guest OSes, databases, and applications** |
| **Awareness and Training** | Trains the **AWS** employees | Trains **their** employees |

_(Mod 12 pp42–43)_

## Customer-specific controls _(Mod 12 p43)_

"Customers are responsible for the controls based on the applications they deploy within the
AWS services." Only one control is worked: **Service and Communication Protection / Zone
Security** — customers are responsible for routing or zoning data within specific security
environments. _(p43)_

Upstream: [[12-LO02a-Cloud-Security-Shared-Responsibility]] (generic cloud model) ·
related: [[12-LO01b-Cloud-Service-Delivery-Models]]

## Cards

AWS shared responsibility — who secures what
?
Customers decide the access levels they give from and to their resources; AWS secures the cloud. "In the cloud" = customer band · "of the cloud" = AWS band

The two control types the AWS shared responsibility model uses
?
Inherited Controls — inherited completely from AWS to customers (e.g. physical and environmental) · Shared Controls — applied to both the infrastructure and the customer layer with separate perspectives

Shared Control: Patch Management split
?
AWS patches and fixes flaws within the infrastructure; customers patch their guest OS and applications

Shared Control: Configuration Management split
?
AWS configures the infrastructure devices; the customer configures their guest OSes, databases, and applications

Shared Control: Awareness and Training split
?
AWS trains the AWS employees; customers train their employees

Client-Side Data Encryption — which keys may the customer use
?
Either an AWS-managed encryption key or a personal key not provided by AWS
