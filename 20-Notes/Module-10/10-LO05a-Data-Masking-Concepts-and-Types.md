---
type: note
module: "10"
lo: "05"
tags: [concept, process, tool, mod/10]
topic: "Data Masking — Concepts, Types, Reasons"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Masking Concepts (§10.5.1)

## What it is
- **Data masking / data obfuscation** = hiding original data with random characters or other data
- Purpose: **minimize unnecessary exposure** of sensitive info — **PII, PHI, PCI-DSS card data, intellectual property (ITAR)**
- Replaces vulnerable/sensitive data with **fictitious but functional data** that seems real → safe for uses where original data not required
- **Basic format stays the same, key values change**: `2424 6789 4545 3421` → `2424 XXXX XXXX 3421`

## Reasons to include masking in data security
| Reason | Detail |
|---|---|
| **Protect nonproduction data** | Dev/testing/training/analytics copies multiply exposure; masking secures safe sharing |
| **Insider threats** | Employees work against masked data instead of real production data |
| **Third parties** | Safe to share PII/card/PHI with market researchers |
| **Compliance** | GDPR + regulations; without affecting business operations |

## Types of data masking
| Type | Behavior |
|---|---|
| **Static data masking (SDM)** | Masks sensitive data **at rest** in the original DB environment (copies masked for non-prod) |
| **Dynamic data masking (DDM)** | Temporarily masks data **in transit** without affecting data at rest; role-based security; SQL-query alteration via proxy |
| **On-the-fly data masking** | Applied as data **transitions from one environment to another**; transforms production data into high-quality masked data |

- Choose type by: org size, **location (cloud vs on-premise)**, complexity of data to secure

## Cards
Q:: What is data masking?
A:: Hiding original data with random characters/other data, minimizing exposure of PII, PHI, PCI card data, IP while keeping a realistic format.
#flashcard
Q:: SDM vs DDM vs on-the-fly masking?
A:: SDM = mask at rest (DB copy); DDM = mask in transit (role-based, proxy alters SQL); on-the-fly = transform between source and target environments.
#flashcard
Q:: 4 reasons to include masking in data security?
A:: Nonproduction data protection · insider threats · third-party sharing · regulatory compliance (GDPR).
#flashcard
Q:: Masked card example `2424 6789 4545 3421`?
A:: `2424 XXXX XXXX 3421` — format preserved, key values changed.
#flashcard
Q:: What factors guide data masking type selection?
A:: Organization size · location (cloud vs on-premise) · complexity of data to secure.
#flashcard