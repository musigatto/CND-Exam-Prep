---
type: note
module: "12"
lo: "01"
tags: [concept, process, mod/12]
topic: "Cloud service delivery models (IaaS/PaaS/SaaS)"
exam_weight: unknown
status: done
unresolved:
  - "p11: the figure 'Customer vs. CSP Shared Responsibilities in IaaS, PaaS, and SaaS' is an image. Only axis labels OCR'd (premise, service provider, subscribers/tenants/customers, cloud computing as a service, virtual network) — the responsibility cells are not recoverable from the slice."
---

[[MOC-Module-12]]

# Cloud Service Delivery Models (§12.01)

> Three categories: **IaaS · PaaS · SaaS** — what the subscriber controls vs. what the CSP runs,
> plus the stated advantages/disadvantages of each _(Mod 12 p9–11)_

## Control split at a glance _(Mod 12 p9–10)_

| | Subscriber receives | Subscriber's authority | Examples the courseware gives |
|---|---|---|---|
| **IaaS** | Virtual machines + other abstracted hardware and OSes, controllable through a service API | CSP manages the **underlying cloud-computing infrastructure**, so the subscriber avoids human capital and hardware costs | Amazon EC2, GoGrid, SunGrid, Windows SkyDrive, Rackspace |
| **PaaS** | Development tools, configuration management and deployment platforms on demand | Authority over the **deployed applications** and *probably* the application hosting environment configurations — not over the software/infrastructure underneath | Intel MashMaker, Google App Engine, Force.com, Microsoft Azure |
| **SaaS** | Application software over the internet | Application only | Google Docs/Calendar, Salesforce CRM, FreshBooks, Basecamp |

## IaaS — Infrastructure-as-a-Service _(Mod 12 p9)_

On-demand fundamental IT resources: **computing power, virtualization, data storage, network**.

| Advantages (6) | Disadvantages (2) |
|---|---|
| Dynamic infrastructure scaling | Software security is at high risk (third-party providers are more prone to attacks) |
| Guaranteed uptime | Performance issues and slow connection speeds |
| Automation of administrative tasks | |
| Elastic load balancing (ELB) | |
| Policy-based services | |
| Global accessibility | |

## PaaS — Platform-as-a-Service _(Mod 12 p10)_

Platform for developing applications and services. Writing applications in the PaaS environment
brings **dynamic scalability, automated backups, and other platform services without requiring
explicit codes**.

| Advantages (6) | Disadvantages (3) |
|---|---|
| Simplified deployment | Vendor lock-in |
| Prebuilt business functionality | Data privacy |
| Lower risk | Integration with other system applications |
| Instant community | |
| Pay-per-use model | |
| Scalability | |

## SaaS — Software-as-a-Service _(Mod 12 p10)_

Application software on demand over the internet. Providers charge **pay-per-use via
subscription, advertising, or sharing among multiple users**.

| Advantages (4) | Disadvantages (3) |
|---|---|
| Low cost | Security and latency issues |
| Easy administration | Total dependency on the internet |
| Global accessibility | Switching between SaaS vendors is difficult |
| Compatible — no specialized hardware or software is required | |

## Separation of customer vs. CSP responsibilities _(Mod 12 p11)_

> "It is important to ensure the separation of responsibilities of the subscribers and service
> providers." What separation of duties buys:
> - prevents **conflicts of interest, illegal acts, fraud, abuse, and errors**
> - helps **identify security control failures** — information theft, security breaches, invasion of security controls
> - **restricts the amount of influence held by an individual**
> - ensures there are **no conflicting responsibilities** _(Mod 12 p11)_

> "It is essential to know the **limitations of each cloud service delivery model** when
> accessing specific clouds and their models." _(Mod 12 p11)_

The p11 figure that draws this split is image-only in the source — the control boundary is
carried here by the IaaS/PaaS/SaaS authority column above. NIST's version of the same idea
(SaaS/PaaS/IaaS service layers and the five actors) is in the architecture note.

Exam cross-refs: [[Question-Bank]]







