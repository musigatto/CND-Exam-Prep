---
type: note
module: "12"
lo: "01"
tags: [concept, policy, mod/12]
topic: "NIST cloud reference architecture and actors"
exam_weight: unknown
status: done
unresolved:
  - "p16: the service — deployment combination matrix is image-only. The slice carries just the sentence 'The combination of service and deployment models categorize the delivery of cloud services.' — no cell data recoverable."
  - "p17: Figure 12.1's diagram text is partial OCR — the first pass renders the service layer as 'paas IaaS' while the body pass renders it 'SaaS PaaS IaaS'. Layer and actor names here are taken from the readable body pass; the connector/edge topology is not recoverable from text."
---

[[MOC-Module-12]]

# NIST Cloud Reference Architecture (§12.01)

> The five actors, the layers, and the broker service categories _(Mod 12 p16–19)_

## Service — deployment combination _(Mod 12 p16)_

> "The combination of service and deployment models categorize the delivery of cloud services."
> _(Mod 12 p16)_

The matrix that expresses this is an image in the source — no cell data transcribed.

## Figure 12.1 — Separation of Cloud Responsibilities Specific to Service Delivery Models _(Mod 12 p17)_

A generic high-level architecture showing the primary actors, their activities and functions —
there to understand the applications, requirements, characteristics and standards of cloud
computing.

**Stack layers** _(p17 figure)_

| Layer | Contents read from the figure |
|---|---|
| Service Layer | **SaaS · PaaS · IaaS** |
| Resource Abstraction and Control Layer | — |
| Physical Resource Layer | Hardware Facility |
| Cross-cutting | Cloud Service Management (Provisioning / Configuration) · Business Support · Portability / Interoperability |

**Actors and their activities in the figure** _(Mod 12 p17)_

| Actor | Activities shown |
|---|---|
| Cloud Provider | owns the stack |
| Cloud Consumer | uses the Service Layer |
| Cloud Auditor | Security audit · Privacy Impact Audit · Performance Audit |
| Cloud Carrier | connectivity/transport between consumer and provider |
| Cloud Broker | Service Intermediation · Service Aggregation · Service Arbitrage |

## The five significant actors _(Mod 12 p18)_

Order as printed: cloud consumer → cloud provider → cloud carrier → cloud auditor → cloud broker.

| Actor | Definition (p17 figure box + p18 body) |
|---|---|
| **Cloud consumer** | A person or organization that maintains a business relationship with the CSPs and uses cloud computing services |
| **Cloud provider (CSP)** | Acquires and manages the computing infrastructure intended for providing services (directly or via a cloud broker) to interested parties via network access |
| **Cloud carrier** | Intermediary providing **connectivity and transport services** between the CSPs and cloud consumers; gives consumers access via networks, telecommunication and other access devices |
| **Cloud auditor** | Party that **independently examines the cloud service controls to express a corresponding opinion** |
| **Cloud broker** | Entity that manages cloud services regarding **usage, performance and delivery**, and maintains the relationship between the CSPs and cloud consumers |

### Cloud consumer mechanics _(Mod 12 p18)_

- Browses the CSP **service catalog**, requests the desired services, sets up service contracts
  (directly **or via a cloud broker**), then uses the service.
- The **CSP bills the consumer** for the services provided.
- The CSP should fulfil an **SLA in which the consumer specifies technical performance
  requirements** — quality of service, security, and remedies for performance failure.
- The CSP may also define the **limitations and obligations** the consumer must accept.

**Services available to the consumer per model** _(Mod 12 p18)_

| Model | Services |
|---|---|
| PaaS | database · business intelligence · application deployment · development and testing · integration · storage · service management · content delivery network (CDN) · platform |
| IaaS | hosting · backup and recovery · computing |
| SaaS | human resources · enterprise resource planning (ERP) · sales · customer relationship management (CRM) · collaboration · document management · email and office productivity · content management · financials · social networks |

### Cloud auditor scope _(Mod 12 p18)_

Audits verify **adherence to standards by reviewing objective evidence**. A cloud auditor can
evaluate the CSP's services regarding:

- **Security controls** — management, operational and technical safeguards intended to protect
  the confidentiality, integrity and availability of the system and its information
- **Privacy impact** — compliance with applicable privacy laws and regulations governing the
  privacy of an individual
- **Performance**

### Cloud broker — why, and the three service categories _(Mod 12 p18–19)_

Integration of cloud services has become **significantly complicated** for consumers, so a
consumer may request services **from a cloud broker instead of directly contacting a CSP**.

| Category | Definition |
|---|---|
| **Service intermediation** | Improves a given function by a specific capability and provides value-added services to cloud consumers |
| **Service aggregation** | Combines and integrates multiple services into one or more **new** services |
| **Service arbitrage** | Similar to aggregation, but the services being aggregated are **not fixed** — the broker may choose from multiple agencies |

> Aggregation vs. arbitrage = **fixed set** vs. **broker's choice**. _(Mod 12 p19)_

Exam cross-refs: [[Question-Bank]] · [[Exam-Facts]]







