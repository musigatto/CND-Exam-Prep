---

type: note
module: "10"
lo: "09"
tags: [concept, process, protocol, crypto, mod/10]
topic: "Data Integrity — Meaning, Types, Checking, Checklist"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Integrity (§10.9)

## What is data integrity
- **Accuracy, consistency, and reliability of data throughout its lifecycle** — unaltered and trustworthy from creation to consumption/deletion
- Fundamental to data quality; keeps credibility + usefulness of data
- Guarantees data intact/uncorrupted, free from unauthorized modification; aids GDPR compliance, prevents corruption

## Characteristics
Complete · Accurate · **Safe** (accessible only by authorized) · Compliance (privacy rules) · Consistent (same object across datasets) · Reliable · **Timeliness** (up to date / accessible within acceptable window)

## Types
| Type | Scope |
|---|---|
| **Physical integrity** | Correctness/accuracy during storage + retrieval; threats = natural disasters, deterioration, hardware failures, radiation/extreme temp+pressure, power outages; countermeasures = error-correcting memory, battery-protected write cache, redundant storage (**RAID**) |
| **Logical integrity** | Data remains intact while used in relational databases; 4 sub-types: |
| → Entity integrity | No duplication; no key entry kept null/blank |
| → Referential integrity | Rules governing storage/use; only authorized changes/deletions/additions; prevents duplication + irrelevant data |
| → Domain integrity | Column accepts only correct type/amount/range (numeric → numeric only) |
| → User-defined integrity | Org-specific rules beyond entity/referential/domain |

## Data integrity checking — methods
| Method | How it works |
|---|---|
| **Checksums / hash functions** (MD5, SHA-256, SHA-3) | Fixed-length value before vs after transmission; match = unaltered, mismatch = possible compromise |
| **Parity checks** | Parity bit forces even/odd count of 1s; receiver re-tallies; mismatch → error |
| **CRC checksum** | Polynomial-division remainder check value over network communication + storage; mismatch → corruption |
| **Data validation rules** | Range checks, format checks, input validation, constraint validation at app level |
| **ECC** (error-correcting codes) | Adds redundancy to detect+correct errors in memory/storage; encryption fails decryption if tampered |
| **Digital signatures** | Sender signs w/ private key; recipient verifies w/ public key; alteration invalidates signature |

## Checklist to preserve data integrity
1. **Validate input** — critical for known + unknown sources
2. **Validate data** — verify accuracy of data entry (users, malicious users, apps)
3. **Remove duplicate data** — confidentiality: no copy/paste of secure data into public docs/emails/folders
4. **Perform regular backups** — restore up-to-date versions after ransomware/loss; back up often
5. **Control access** — least-privileged access; restrict unauthorized/impersonation
6. **Prepare audit trail** — monitor breaches, identify circumstances + locate perpetrator

## Data integrity vs quality vs security vs accuracy
| Concept | Meaning |
|---|---|
| Data integrity | Data stays **unaltered and full** w/ planned significance; guarantees reliability |
| Data quality | General appropriateness/reasonableness for expected use; accuracy, fulfilment, consistency, importance, availability |
| Data security | Protects against **unauthorized access, disclosure, modification, destruction**; keeps data private |
| Data accuracy | Correctness and reliability — data accurately reflects real-world facts/attributes |









