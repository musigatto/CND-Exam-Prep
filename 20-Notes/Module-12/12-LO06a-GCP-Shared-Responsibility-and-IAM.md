---
type: note
module: "12"
lo: "06"
tags: [concept, policy, mod/12, flashcard/12]
topic: "GCP shared responsibility model and GCP IAM"
exam_weight: unknown
status: done
unresolved:
  - "p246 figure 'Understanding Google Cloud Shared Responsibility': the left-hand stack row labels OCR, but NOT ONE cell value of the IaaS/PaaS/SaaS grid OCR'd. Only the three model labels (IaaS, PaaS, SaaS) and the two column headers (User's Responsibility, Google's Responsibility) are readable. The layer split recorded here is therefore taken from the body prose printed directly under the figure, not from the figure cells. The figure carries no 'Figure 12.xx' caption number."
  - "p246: in the IaaS sentence the user-side list both opens 'guest OS, data and content' and closes '... usage, access policies, and content', so 'content' appears twice. Reading: the leading one is part of the 'Guest OS, data and content' row label and the trailing one is the separate 'Content' row. This is inferred from the figure row labels, not stated."
  - "p246: the SaaS sentence is cut off mid-word - '...whereas access policies and content are the responsibilities of the' - so the subject ('user') is not printed. It is supplied from the identical IaaS/PaaS construction and is an inference, not a reading."
  - "p247: the member list ends 'All authenticated users / All user' - singular in the body prose, while the figure on the same page reads 'All users'. Both are kept as printed."
  - "p247: the Principal definition names only four of the seven members printed on the page ('Google account, service account, Google group, or cloud identity domain'). Google Workspace account, All authenticated users and All users appear in the member list but are not defined on p247."
  - "p247: 'Roles' and 'Policy' appear only as figure text ('Roles: Collection of permissions', 'Policy: Binds a set of members to a role - Bindings (1 or more)'). The body says the model 'consists of three major divisions' and then defines only Principal; Roles and Policy are never expanded in the body on this page."
---

[[MOC-Module-12]]

# GCP Shared Responsibility Model and GCP IAM (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Section title as printed: "LO#06: Security in Google Cloud Platform (GCP)". "This section
> aims to explain the various security features provided by the Google Cloud Platform (GCP)."
> Covers pp. 245–247: LO scope (p245) · Google Cloud shared responsibility model (p246) ·
> GCP Identity and Access Management (p247).

## What LO#06 covers — the printed list _(Mod 12 p245)_

| # | Feature as printed |
|---|---|
| 1 | GCP **shared responsibility model** |
| 2 | GCP **IAM features and best practice to implement IAM securely** |
| 3 | GCP **encryption and key management features** — sub-line: "How to encrypt data at rest and data in transit and manage the encryption keys" |
| 4 | Implement GCP **network security measures** |
| 5 | GCP **data storage security features** |
| 6 | GCP **monitoring and logging features** |

## Google Cloud shared responsibility model — rules, not figure cells _(Mod 12 p246)_

- "In the Google shared responsibility model, the users and Google cloud resource providers
  share the responsibilities **based on the workload**." Categorized by layer:
  **IaaS · PaaS · SaaS**.
- **Figure row labels** (left column, as printed): `Content` · `Access Policies` · `Usage` ·
  `Deployment` · `Web Application Security` · `Identity` · `Operations` · `Access and
  Authentication` · `Network Security` · `Guest OS, data and content` · `Audit Logging` ·
  `Network Storage and Encryption` · `Hardened Kernel and IPC` · `Hardware`.
  Column headers: **User's Responsibility** · **Google's Responsibility**; model labels
  **IaaS · PaaS · SaaS**. *No cell value survived OCR* — see `unresolved:`.

| Layer | Google / resource provider | User |
|---|---|---|
| **IaaS** | hardware · hardened kernel and IPC · storage and encryption · network · audit logging | guest OS, data and content · network security · access and authentication · operations · identity · web application security · deployment · usage · access policies · content |
| **PaaS** | hardware · hardened kernel and IPC · storage and encryption · network · audit logging · guest OS, data and content · network security · access and authentication · operations · identity · web application security | deployment · usage · access policies · content |
| **SaaS** | hardware · hardened kernel and IPC · storage and encryption · network · audit logging · guest OS, data and content · network security · access and authentication · operations · identity · web application security · deployment · usage | access policies · content |

_(Mod 12 p246)_

**Exam handle** — climbing the stack only ever *removes* user-side rows: **IaaS** keeps
everything above *Network*; **PaaS** stops at *Deployment*; **SaaS** stops at *Access
Policies*. **`Content` and `Access Policies` are the customer's at all three layers.**
Cross-module: `[[12-LO02a-Cloud-Security-Shared-Responsibility]]` ·
`[[12-LO04a-AWS-Shared-Responsibility-Models]]` · `[[12-LO03b-CSP-Security-Feature-Comparison]]`

## GCP Identity and Access Management _(Mod 12 p247)_

- "GCP IAM provides **granular access to specific Google Cloud resources** and **prevents
  unauthorized access** to resources."
- "By implementing **IAM policies**, administrators can control the **access (roles) of
  users/members** to specific resources."
- "GCP IAM provides granular access to users with **POLP (principle of least privilege)**
  security for the essential Google cloud resources."
- "The GCP IAM model consists of **three major divisions**."

| Division | Printed as |
|---|---|
| **Principal** | "could be a **Google account, service account, Google group, or cloud identity domain** with an identity to access the Google cloud resource". "In Google Account, Google group, and service account, **the identity is an email address**." |
| **Roles** *(figure text only)* | "**Collection of permissions**" |
| **Policy** *(figure text only)* | "**Binds a set of members to a role** — **Bindings (1 or more)**" |

_(Mod 12 p247)_

**Members — 7, identical in the figure and the body list** _(p247)_:
`Google account` · `Service account` · `Google group` · `Google Workspace account` ·
`Cloud Identity domain` · `All authenticated users` · `All user(s)`.

**Google account** — "constitutes a **developer, an administrator, or any individual** who
connects to the Google cloud with an identity such as an email address." _(p247)_

Nothing else is defined on p247 — the remaining six members are only named. Their
definitions start in [[12-LO06b-GCP-Service-Accounts]] (service account, Google group, G Suite
domain, Cloud Identity domain, role, permission), and the rules that constrain them in
[[12-LO06c-GCP-IAM-Security-Best-Practices]].

## Cards

Features listed under LO#06
?
GCP shared responsibility model · GCP IAM features and best practice to implement IAM securely · GCP encryption and key management (data at rest / data in transit) · GCP network security measures · GCP data storage security · GCP monitoring and logging

In Google's shared responsibility model, which rows stay with the **user** at each layer
?
IaaS: guest OS/data/content down to content (everything above network) · PaaS: deployment · usage · access policies · content · SaaS: access policies · content — content and access policies are the customer's at all three layers

The three divisions of the GCP IAM model
?
Principal (an identity — an email address) · Roles (a collection of permissions) · Policy (binds a set of members to a role, via one or more bindings)

The seven GCP IAM members
?
Google account · Service account · Google group · Google Workspace account · Cloud Identity domain · All authenticated users · All users

GCP IAM stated purpose
?
Granular access to specific Google Cloud resources, preventing unauthorized access, under POLP (principle of least privilege) — administrators control access by implementing IAM policies
