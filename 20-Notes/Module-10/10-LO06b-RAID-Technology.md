---

type: note
module: "10"
lo: "06"
tags: [concept, process, mod/10, flashcard/10]
topic: "RAID Technology — Levels 0/1/3/5/10/50"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# RAID Technology (§10.6.2)

## What RAID does
- **Redundant Array of Independent Disks**: combine disks for performance + fault tolerance; backup-relevant (redundancy ≠ backup, but small-scale data protection)

## RAID levels
| Level | Technique | Min disks | Fault tolerance |
|---|---|---|---|
| **RAID 0** | Striping | 2 | None (any disk loss = data loss) |
| **RAID 1** | Mirroring | 2 | Any 1 disk |
| **RAID 3** | Striping + dedicated parity disk | 3 | 1 disk |
| **RAID 5** | Striping + distributed parity | 3 | 1 disk |
| **RAID 10** | Striping + mirroring | 4 | 1 disk / mirrored pair |
| **RAID 50** | Striping across mirrored arrays (RAID 0 over RAID 1) | 6 | 1 disk per mirrored group |

- **RAID 50 benchmark**: combines striping + mirroring → high performance (RAID 0) + fault tolerance (RAID 1)
- Choosing level: cost, # disks, R/W mix, failure tolerance

## Mnemonics
- 0 = Zero tolerance · 1 = Mirror pair · 3 = dedicated parity · 5 = spread parity · 10 = stripe-mirror · 50 = stripe-of-mirrors

## Cards
Which RAID level offers striping with NO fault tolerance?
?
RAID 0 (minimum 2 disks).

RAID 50 = what combination, minimum disks?
?
Striping across mirrored pairs (RAID 0 over RAID 1); minimum 6 disks.

RAID 3 vs RAID 5 parity placement?
?
RAID 3 = dedicated parity disk; RAID 5 = parity distributed across all disks.

Minimum disks for RAID 10?
?
4 (2 mirrored pairs, striped).
