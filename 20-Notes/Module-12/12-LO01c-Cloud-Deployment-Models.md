---
type: note
module: "12"
lo: "01"
tags: [concept, mod/12]
topic: "Cloud deployment models"
exam_weight: unknown
status: done
unresolved:
  - "p12: the public cloud advantage 'Reduced time' carries a garbled, truncated explanation in the source ('when a reconfigured) server crashes, the cloud must be restarted or'). Only the advantage label is used."
---

[[MOC-Module-12]]

# Cloud Deployment Models (§12.01)

> Four standard models — **public · private · community · hybrid** — plus **multi-cloud**,
> with pros/cons exactly as the courseware lists them _(Mod 12 p12–15)_

## Selection drivers _(Mod 12 p12)_

Deployment model selection is based on the enterprise requirements:

- Where cloud computing services are **hosted**
- **Security requirements**
- Ability to **share** cloud services
- Ability to **manage some or all** cloud services
- **Customization** capabilities

## Model map _(Mod 12 p12)_

| Model | One-line definition |
|---|---|
| **Public** | Services rendered over a public network — provider offers applications, servers, data storage to the public over the internet |
| **Private** | Cloud infrastructure operated **exclusively for a single organization** (a.k.a. internal/corporate cloud; can sit inside the corporate firewall) |
| **Community** | Shared infrastructure between several organizations from a specific community with common concerns (security, compliance, jurisdiction…) |
| **Hybrid** | Composition of two or more clouds (private, community, public) that remain **unique entities but are bound together**, offering the benefits of multiple deployment models |
| **Multi-cloud** | Utilizes **numerous public clouds** rather than combining private and public clouds |

## Public cloud _(Mod 12 p12–13)_

Provider is **liable for the creation and constant maintenance** of the public cloud and its IT
resources. May be free or pay-per-usage. Examples: Amazon EC2, IBM's Blue Cloud, Google App
Engine, Windows Azure Services Platform.

| Advantages (4) | Disadvantages (5) |
|---|---|
| Simplicity and efficiency | Security is not guaranteed |
| Low cost | Lack of control (third-party providers are in charge) |
| Reduced time _(explanation garbled in source)_ | Slow speed (relies on internet connections, data transfer rate is limited) |
| No maintenance (service is hosted off-site) | |
| No contracts (no long-term commitments) | |

## Private cloud _(Mod 12 p13)_

Exclusively operated by one organization; deployed to **retain full control over corporate data**.

| Advantages (5) | Disadvantages (2) |
|---|---|
| Enhance security (dedicated to a single organization) | Expensive |
| More control over resources (the organization is in charge) | On-site maintenance |
| Greater performance (inside the firewall → high data transfer rates) | |
| Customizable hardware, network and storage performance (org owns the cloud) | |
| Sarbanes-Oxley, PCI DSS and HIPAA compliance data significantly easier to acquire | |

## Community cloud _(Mod 12 p13–14)_

Multi-tenant infrastructure shared among organizations with common computing concerns — security,
regulatory compliance, performance requirements, jurisdiction. **On-premise or off-premise**;
governed by the participating organizations **or** a third-party managed service provider.

| Advantages (5) | Disadvantages (5) |
|---|---|
| Less expensive compared to private cloud | Competition between consumers in usage of resources |
| Flexibility to meet the community needs | No accurate prediction of required resources |
| Compliance with legal regulations | Who is the legal entity in case of liability? |
| High scalability | Moderate security (other tenants may be able to access data) |
| Organizations can share a pool of resources from anywhere via the internet | Trust and security concerns between tenants |

## Hybrid cloud _(Mod 12 p14)_

Two or more clouds that stay unique entities but are bound together. The organization
**provides and manages some resources in-house** while others are offered externally.
Courseware example: critical activities (operational customer data) on a **private** cloud,
non-critical activities on a **public** cloud.

| Advantages (4) | Disadvantages (4) |
|---|---|
| More scalable (contains both public and private clouds) | Network-level communication may be conflicted (uses both public and private clouds) |
| Offers secure and scalable public resources | Challenging data compliance |
| High level of security (comprises a private cloud) | Relies on the internal IT infrastructure to handle any outage (maintain redundancy across data centers) |
| Reduces and manages cost according to the requirement | Complex service-level agreements (SLAs) |

## Multi-cloud _(Mod 12 p14–15)_

**Trap:** multi-cloud ≠  hybrid. A combination of **only two or more public cloud services**; it
does **not** mix public and private. Strategy = an organization merging services from various
public cloud providers.

| Advantages (5) | Disadvantages (3) |
|---|---|
| For each task, the best service can be selected | Security can be a concern when integrating different providers |
| Lowers the cost | Difficult to manage when using many different public cloud providers |
| Improved redundancy and backup options | Cost models can vary among providers |
| Freely choose public cloud and connectivity providers | |
| Scalable and flexible environments | |

The **service — deployment combination matrix** (the table that categorizes cloud service
delivery) sits on p16, which leads the NIST reference-architecture note.

Exam cross-refs: [[Question-Bank]]







