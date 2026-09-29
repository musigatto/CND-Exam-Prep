---

type: note
module: "10"
lo: "06"
tags: [concept, mod/10, flashcard/10]
topic: "SAN vs NAS Storage"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# SAN and NAS Storage (§10.6.3)

## NAS (Network-Attached Storage)
- File-level storage appliance on the LAN; serves files via **CIFS/SMB** and **NFS**
- Types:
  | Type | Typical Capacity / Role |
  |---|---|
  | High-end / enterprise | TB-scale, multi-protocol, clustered |
  | Mid-market | ~100 TB class, rackmount |
  | Low-end / desktop | ~8 TB class, consumer |
- Advantages: centralized backup, easy add nodes, auto-backup to NAS, granular rights

## SAN (Storage Area Network)
- Block-level network between servers & storage (FC/iSCSI); appears as local disk to apps
- Strengths: high IOPS, low latency, server virtualization friendly, sophisticated backup integration

| | NAS | SAN |
|---|---|---|
| Granularity | File-level (CIFS/NFS) | Block-level (FC/iSCSI) |
| Best for | File sharing, small scale | DBs, virtualization, high performance |
| Cost | Lower entry | Higher |

## Cards
NAS = which protocol layer and example file protocols?
?
File-level; CIFS/SMB and NFS.

SAN serves data at what level?
?
Block-level (Fibre Channel / iSCSI); presented as raw disk to servers.

Typical NAS capacity split high-end/mid-market/low-end?
?
Enterprise (TB-scale, clustered) · mid-market (~100 TB) · desktop/low-end (~8 TB).
