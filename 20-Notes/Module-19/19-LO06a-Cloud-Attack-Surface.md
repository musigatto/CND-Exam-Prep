---
type: note
module: "19"
lo: "06"
tags: [process, concept, threat, mod/19]
topic: "cloud attack surface"
exam_weight: unknown
status: done
unresolved:
  - "p50 table/grid OCR is jumbled; row-to-example mapping is taken from the pp51-52 prose, not the p50 grid order."
  - "p50 participant-classes sentence truncated at 'the attack attempts in the C...' — remainder not in slice."
  - "p53 IoT taxonomy table starts on this page but is covered in full in the sibling IoT note; only the p53 definition and area list are recorded here."
---

[[MOC-Module-19]]

# Cloud Attack Surface (§19.06)

> **LO#06: Discuss attack surface analysis specific to cloud and IoT** _(Mod 19 pp49–53)_
> Covers pp49–53. Sibling: [[19-LO06b-IoT-Attack-Surface-and-Module-Summary]].

## Why cloud/IoT widens the surface

- **Increased use of Cloud and IoT expands the attack surface**; more Cloud use + more connected IoT = more endpoints to protect _(Mod 19 p49)_.
- Understanding the Cloud and IoT attack surfaces helps secure the Cloud/IoT-supported network _(Mod 19 p49)_.

## Model: three participant classes

- **Service users, Service instances or Services, and Cloud provider** _(Mod 19 p50)_.
- Interactions involve **at least two** participant-class entities — e.g. user requesting a service, service instance requesting more CPU from infrastructure _(Mod 19 p50)_.

## Six cloud attack surfaces

| Surface | What is exposed | Covers / examples |
|---|---|---|
| Service to User | Server-to-client interface; service interface exposed towards clients | **All attacks possible in a client-server architecture** — **buffer overflow, SQL injection, privilege escalation**. **Most important** attack surface of a Cloud solution _(Mod 19 pp50–51)_ |
| User to Service | Client program (user service) interface provided towards the service (server) | **Browser-based application attacks**, attacks on **browser caches**, **phishing attacks on email client** _(Mod 19 pp50–51)_ |
| Cloud to Service | Cloud resources/interfaces exposed to service instances | **Service instance's attacks against its Cloud host** — **resource exhaustion**, triggering the provider for more resources ending in **DoS**, attacks on the **Cloud system hypervisor** _(Mod 19 pp50–51)_ |
| Service to Cloud | Service instance exposed to the Cloud provider | **All types of attacks by the provider on a service running on it**. **Most critical** — easy to exploit, high impact: **availability reductions (shutdown service instances)**, **privacy attacks (scanning a service's data in process)**, **malicious interference (tampering data in process, injecting additional operations)**, **data integrity attack**, **data confidentiality attack** _(Mod 19 pp51–52)_ |
| Cloud to User | Cloud-control service between provider and user (adding/deleting service instances); difficult to define | **Attacks a Cloud service faces from a user's point of view**; attacks on **Cloud control** _(Mod 19 p52)_ |
| User to Cloud | User exposed to the Cloud | Attack vectors **targeting the user, originating at the Cloud** — e.g. **phishing-like attempts presenting a fake usage bill** _(Mod 19 pp50–52)_ |

## Recommendations for reducing the cloud attack surface

1. Identify and map **all assets** across the Cloud _(Mod 19 p52)_.
2. Map **internal and external** network infrastructures for a **single view** of the network _(Mod 19 p52)_.
3. Identify and understand **vulnerabilities, misconfigurations, and threats** to all assets _(Mod 19 p52)_.
4. Implement security controls for **local network and Cloud infrastructure** _(Mod 19 p52)_.
5. Protect **every endpoint** device _(Mod 19 p52)_.
6. Ensure security of **all data repositories** _(Mod 19 p52)_.
7. Understand the **internal access control and security contract** of the provider **before signing the Service Level Agreement** _(Mod 19 p52)_.

## Lead-out: IoT surface starts on p53

- IoT attack surface = **combination of potential vulnerabilities/threats** of the IoT, its applications and devices, on which attacks can be initiated _(Mod 19 p53)_.
- p53 area list: **Ecosystem Access Control, Device Memory, Device Physical Interfaces, Device Web Interface, Device Firmware, Device Network Services, Administrative Interface, Local Data Storage, Cloud Web Interface, Ecosystem Communication, Vendor Backend (APIs), Third-Party Backend APIs, Update Mechanism, Mobile Application, Vendor Backend APIs, Network Traffic** — `Source:` printed as `https://www.owasp.org` _(Mod 19 p53)_.
- Full IoT detail → [[19-LO06b-IoT-Attack-Surface-and-Module-Summary]].






