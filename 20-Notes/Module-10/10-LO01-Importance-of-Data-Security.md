---

type: note
module: "10"
lo: "01"
tags: [concept, threat, process, mod/10, flashcard/10]
topic: "Data Security Importance — Critical Data, States, Technologies"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Security and Its Importance (§10.1)

## What is business-critical data?
- **Data = heart of any organization** · data loss → severe business damage
- **Critical data** = information important for business operation; identification + classification of business-critical data = **first step** in securing data
- **Examples**: accounting files · databases/business-related data · OS files purchased with computer (CDs, software) · office documents/spreadsheets · software downloaded/purchased from Internet · contact info (email address book) · personal photos/music/videos · any other critical file
- **How to identify**: conduct **business impact analysis** to find critical functions/data · identify processes/functions that depend on/co-exist with critical data · evaluate impact of data damage on the business

## Need for data security
| Cause | Effect |
|---|---|
| Loss/theft of laptops + mobile devices | Brand damage, reputation loss, competitive advantage loss |
| Unauthorized data transfer to USB devices | Loss of customers, market share loss |
| Improper sensitive data categorization | Shareholder value erosion |
| Data theft by employees/external parties | Fines, civil penalties |
| Printing/copying of sensitive data by employees | Litigation/legal actions |
| Insufficient response to intrusions | Regulatory fines/sanctions |
| Unintentional sensitive data transmission | Significant cost/effort to notify affected parties + recover |

- Breaches/cyberattacks ↑ from computer-network expansion → data security necessary

## Definition + three states of data
- **Data security** = controls preventing intentional/unintentional **data misuse, destruction, modification**
- Data is secured when: restrict data from intentional/accidental **destruction, modification, disclosure** · **recover** lost/modified data post-incident · have **data retention + destruction policies**
- **3 states**: at rest · in transit · in use (Table 10.1)

| | Data at Rest | Data in Use | Data in Transit |
|---|---|---|---|
| Description | **Inactive**, stored digitally at a physical location | Stored/processed in **memory** | Traversing via some communication means |
| Example | Customer bank balance in database | Data stored in **RAM** | An email being sent |
| Controls | Data encryption, password protection, tokenization, tight control of accessibility | Authentication techniques, full memory encryption, data federation, strong identity management, identify critical assets/vulnerabilities, software up-to-date | **SSL/TLS**, email encryption (**PGP/S/MIME**), firewall controls, data-loss-prevention solutions, firewalls |

- at rest = inactive but still accessed by an app/program; mediums: hard drives, laptops, backup tapes, mobile, offsite/cloud backup
- in transit = moves across network; encrypted channels HTTPS, SSL, TLS, FTPS

## Data security technologies
| Technology | Purpose |
|---|---|
| **Data access control** | Authenticate + authorize users to access data |
| **Data encryption** | Transform data so unauthorized party cannot read it |
| **Data masking** | Obscure specific areas with random chars/codes |
| **Data resilience + backup** | Duplicate copy for restore/recovery when primary lost/corrupted |
| **Data destruction** | Destroy data so it cannot be recovered/misused |
| **Data retention** | Store data securely for compliance/business requirements |
| **Hardware-based security** | Protect device physically, not only via software (hardened devices) |

## Cards
What are the three states of data?
?
Data at rest (inactive, stored) · data in use (RAM/CPU/database, actively processed) · data in transit (moving across the network).

Which state does SSL/TLS and email encryption (PGP, S/MIME) protect?
?
Data in transit.

How is business-critical data identified?
?
Business impact analysis → identify critical functions/data + dependent processes → evaluate impact of data damage on the business.

What makes data "secured" (3 provisions)?
?
Restrict destruction/modification/disclosure · recover lost/modified data after incidents · retention + destruction policies.

Name the 7 data security technologies.
?
Access control · encryption · masking · resilience/backup · destruction · retention · hardware-based security.
