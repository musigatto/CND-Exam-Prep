---
type: note
module: "10"
lo: "06"
tags: [concept, process, mod/10]
topic: "Backup Methods, Types, and Locations"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Backup Types & Methods (§10.6.4)

## Backup types
| Type | Captures | Restore speed | Notes |
|---|---|---|---|
| **Full** | All data | Fastest (tape set) | Baseline; most storage/time |
| **Incremental** | Changes since last full **or incremental** | Slower (chain) | Smallest; restore requires full + each incremental |
| **Differential** | Changes since last **full** | Medium | Restore = full + latest differential |

## Methods / techniques
- **Synchronous vs asynchronous** replication (data/mirror) — RPO/RTO trade-offs
- **Snapshot** — point-in-time copy, near-instant
- **Continuous data protection (CDP)** — captures every change continuously

## Locations
| Location | Speed | Safety | Use |
|---|---|---|---|
| Local tape/disk | fast | poor (co-located) | quick restores |
| NAS/SAN | fast | better | central backup |
| External disk (USB) | medium | medium | removable |
| **Cloud/off-site** | slow | best | disaster recovery |

## Mnemonics
- **FID**: Full → Incremental → Differential (per backup run type)

## Cards
Q:: Difference between incremental and differential backup?
A:: Incremental backs up changes since last full OR incremental; differential backs up all changes since the last full backup.
#flashcard
Q:: Which type makes the restore longest (needs most media)?
A:: Incremental restores (must replay full + every incremental since).
#flashcard
Q:: What is a snapshot?
A:: A near-instant point-in-time copy of data used for quick rollback/recovery.
#flashcard