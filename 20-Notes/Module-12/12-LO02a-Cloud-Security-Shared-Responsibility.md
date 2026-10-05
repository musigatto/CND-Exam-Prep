---
type: note
module: "12"
lo: "02"
tags: [concept, policy, mod/12]
topic: "Cloud security shared responsibility model"
exam_weight: unknown
status: done
unresolved:
  - "p22 figure 'Shared Responsibility Model for Security in the Cloud': the row labels (User Access, Data, Applications, Operating System, Network Traffic, Hypervisor, Infrastructure, Physical) and the four column headers (On-premises, IaaS, PaaS, SaaS) OCR'd, but the shaded responsibility cells did not. Which stack layer falls to provider vs customer for each service model is NOT recoverable from the slice — no per-model matrix is asserted here."
  - "p24 figure 'Elements of Cloud Security: Consumer vs. Provider': the on-premise, IaaS and PaaS column bodies OCR'd; the SaaS column body did not. The layer list is transcribed for on-premise/IaaS/PaaS only."
  - "p25 IAM lifecycle diagram is a screenshot-style image and is heavily garbled ('Loong' = logging, 'Management Sunliers', 'Autiwrizatim Model', 'Managem«'t Autiwrizatim'). Its structure is not transcribed; only the readable p25 prose is used."
  - "p25: the p25 figure's list of IAM sub-services could not be read, so the identity-lifecycle items in this note come solely from the p25 prose, which is silent on the individual lifecycle stages."
---

[[MOC-Module-12]]

# Cloud Security Shared Responsibility (§12.02)

> **LO#02 — Understanding cloud security insights**
> Section scope: shared responsibility across IaaS/PaaS/SaaS · enterprise roles in securing
> cloud elements (IAM, encryption & key management, application-level security, data storage
> security, monitoring, logging, compliance) _(Mod 12 p20)_

## What changes, what does not _(Mod 12 p21)_

| | Statement |
|---|---|
| Does **not** change | The **security protocols** required in traditional (on-premise) networks |
| **Does** change | The **security focus** of the cloud consumers |

> The implementation of cloud does not change the security protocols required in traditional
> networks; instead it changes the **security focus** of the cloud consumers. _(Mod 12 p21)_

## Shared responsibility principle _(Mod 12 p22–23)_

- Cloud security **and compliance** are the shared responsibility of the cloud **provider and
  consumer**. _(Mod 12 p22)_
- **If the consumers do not secure their functions, the entire cloud security model will fail.** _(Mod 12 p22)_
- Traditional IT: a **single organization** holds authority over the *complete stack* of computing
  resources and the whole system life cycle. Cloud: provider and consumer **work together** to
  design, build, deploy and operate cloud-based systems, and **both share** the duty of adequate
  security. _(p22–23)_
- CSPs and consumers have **varying levels of control** over the available computing resources. _(Mod 12 p22)_

### How the boundary shifts by service model _(Mod 12 p22–23)_

Matrix in the courseware, columns left→right: **On-premises (for reference) · IaaS ·
PaaS · SaaS**; stack rows top→bottom:

```
User Access · Data · Applications · Operating System · Network Traffic · Hypervisor ·
Infrastructure · Physical
```
_(Mod 12 p22)_

- **Different cloud service models (IaaS, PaaS, SaaS) imply varying levels of controls between
  cloud service providers and cloud consumers.** _(Mod 12 p23)_
- The per-cell shading of that matrix is image-only in the PDF — see `unresolved:`. The
  consumer/provider split that *is* printed in text is in the next section.

## Consumer vs. provider elements _(Mod 12 p24)_

| Cloud service **consumers** are responsible for | Cloud service **providers** are responsible for |
|---|---|
| User security and monitoring — **identity and access management (IAM)** | Securing the **shared infrastructure**: routers, switches, load balancers, firewalls, hypervisors, storage networks, management consoles, DNS, directory services, cloud API |

_(Mod 12 p24)_

Layer breakdown printed in the p24 figure _(readable part: On-premises / IaaS / PaaS columns)_:

| Layer | Printed content |
|---|---|
| **User Security and Monitoring** | Identity services (AuthN/Z, federation, delegation, provisioning) |
| **Information Security – Data** | Encryption (transit, rest, processing), key management, ACL, logging |
| **Application-level Security** | Application stack, service, database, storage |
| **Platform and Infrastructure Security** — PaaS | NoSQL, API, message queues, storage |
| — Guest OS-level | Firewall, hardening, security monitoring |
| — Hypervisor / Host-level | Firewalls, security monitoring |
| — Network-level | BGP, load balancers, firewalls, security monitoring |

_(Mod 12 p24)_

> The p24 figure has no SaaS column body in the slice — the SaaS layer list is not asserted here.

## Identity and Access Management (IAM) _(Mod 12 p25)_

**Definition.** The management of the **digital identities of users and their rights to access
cloud resources** — creating, managing and removing digital identities, plus authorization of
users. _(Mod 12 p25)_

- IAM offers **role-based access control** to an organization's customers or employees for
  accessing critical enterprise information; it comprises the **business processes, policies and
  technologies** that enable surveillance of electronic/digital identities. _(Mod 12 p25)_
- IAM products give system administrators tools to **regulate user access** (create, manage,
  remove) to systems or networks **based on the roles** of individual users. _(Mod 12 p25)_

| Item | Detail |
|---|---|
| Authentication form of choice | Organizations generally prefer **all-in-one authentication** that can be extended to **Identity Federation** |
| Identity Federation = | IAM **with single sign-on (SSO)** and a **centralized AD account** for secure management |
| MFA | IAM enables **multi-factor authentication (MFA)** for the root user and its associated user accounts |
| MFA purpose | To **control access to cloud service APIs** |
| Best MFA option | **Virtual MFA device or hardware device** |

_(Mod 12 p25)_

Related: [[12-LO02b-Cloud-Data-and-Network-Security]] · [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]







