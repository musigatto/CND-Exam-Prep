---
type: note
module: "10"
lo: "08"
tags: [concept, process, tool, mod/10]
topic: "Data Loss Prevention (DLP)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Loss Prevention Concepts (§10.8)

## What is DLP
- **DLP** = set of software products + processes that do **not allow users to send confidential corporate data outside the organization**
- Rules **block the transfer of confidential info across external networks**, control unauthorized access to company info, prevent sending malicious programs into the org
- Also known as: **data leak prevention, information loss prevention, or extrusion prevention**
- Used to: discover sources of data leaks · monitor data leakage sources · protect assets/resources · prevent accidental disclosure to unintended parties · manage resources via business rules, policies, software
- DLP adopted when **internal threats detected**; new tools also monitor/control irregular activity

## Types of DLP solutions
| Type | Protects | Scope |
|---|---|---|
| **Endpoint DLP** | **data in use** | PC-based systems (tablets, laptops); clipboard, email, copy to removable media, printing |
| **Network DLP** | **data in transit** | Installed at **perimeter**; scans all data crossing ports/protocols; email, social media, **SSL traffic**, IM; reports who/what/where; data stored in DB; regulatory compliance |
| **Storage DLP** | **data at rest** | Data center file servers, **SharePoint, databases**; locates + verifies secure storage of sensitive info |

## DLP solution examples
- **WIP** (Windows Information Protection): endpoint DLP; stores business data only on approved devices/apps; Windows Defender ATP evaluates Windows 11 file content, applies DLP at endpoint, integrates with **Azure Information Protection (AIP)**; works w/ Intune / SCCM; separates corporate vs personal data, can remove corporate data from Intune-enrolled devices
- **MyDLP**: **free and open-source**; inspection channels = web, email, IM, printers, **removable storage devices, screenshots**; centralized mgmt, Google-like full-text search of quarantined/archived files, AD integration

## Best practices for successful DLP implementation
1. Identify the **main objective** of DLP
2. Identify **sensitive data** for protection
3. Evaluate **available DLP vendors**
4. Ensure product compatibility with required data types + data stores
5. Identify **roles and responsibilities** of individuals
6. **Implement DLP with a minimal base to reduce false positives**, then enhance gradually

## Vendors (courseware)
**Symantec DLP** (Broadcom; single web console, on-prem/cloud/mobile) · **McAfee Total Protection for DLP** (ePolicy Orchestrator) · **Quantum DLP** (Check Point) · **Trustwave DLP** (web comms, HTTP/HTTPS/FTP) · **Digital Guardian** (scanning endpoints/servers + cloud) · **Forcepoint Enterprise DLP** (user-risk scoring) · **DriveStrike** (lost/stolen device locate/lock/wipe) · **Retrospect** · **Safend** (**Data Protection Suite**)

## Cards
Q:: What is DLP?
A:: Software products + processes that prevent users from sending confidential corporate data outside the organization.
#flashcard
Q:: Name the 3 DLP types and what data phase each protects.
A:: Endpoint DLP = data in use · Network DLP = data in transit · Storage DLP = data at rest.
#flashcard
Q:: Where is Network DLP typically installed and what does it scan?
A:: At the network perimeter; scans all data in transit — email, social media, SSL, IM across ports/protocols.
#flashcard
Q:: What inspection channels does MyDLP (open source) support?
A:: Web, email, instant messaging, printers, removable storage devices, screenshots.
#flashcard
Q:: Key DLP implementation best practice regarding false positives?
A:: Implement with a minimal base to reduce false positives, then enhance gradually as sensitive data is identified.
#flashcard
Q:: Which Microsoft solution provides endpoint DLP and integrates with AIP?
A:: Windows Information Protection (WIP); Windows Defender ATP evaluates content, Azure Information Protection aggregates labeled files.
#flashcard