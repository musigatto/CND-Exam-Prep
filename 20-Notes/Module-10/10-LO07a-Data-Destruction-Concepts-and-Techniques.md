---

type: note
module: "10"
lo: "07"
tags: [process, command, tool, mod/10, flashcard/10]
topic: "Data Destruction Concepts and Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Destruction Concepts (§10.7.1)

## What it is
- **Data destruction** = process of destroying stored data (tapes, hard disks, electronic media) so it is **completely unreadable** and cannot be accessed/used for unauthorized purposes
- Main purpose: **restrict unauthorized disclosure** via proper disposal/destruction of devices, equipment, computers, media storing sensitive data
- Deleted ≠ gone: simple deletion leaves data recoverable on the hard drive/memory chip

## Security benefits
- Protects customer/employee sensitive info from cybercriminals
- **Avoids hefty fines** — security breach can lead to penalties

## Forms of data destruction
Delete / Reformat · Wipe · Overwriting data · Erasure · **Degaussing** · Physical destruction · Electronic shredding · Solid-state shredding

## Data destruction policy
- Ensures data on unused tapes, hard disks, electronic media is deleted/destroyed → unreadable, inaccessible
- Per device:
  - **Mobile phones** (iPhone/Android/Blackberry): **hard reset or cold reset** → restore factory defaults
  - **CDs, DVDs, Blu-rays, tape drives**: **physically destroy** the optical/tape media
  - **Hard drives + flash**: overwrite using **Darik's Boot and Nuke (DBAN), Wipe**, etc.

## Techniques
| Technique | vs what attack | Description |
|---|---|---|
| **Clearing** | Keyboard attack | Clears all user-addressable storage spaces; not recoverable via data/disk/file recovery tools; **not** for damaged/non-rewritable media. Methods: **overwriting · wiping · erasure** |
| **Purging** | **Laboratory attack** (signal-processing recovery tools) | Removes data permanently by strong magnetic fields. Methods: **degaussing · Secure Erase firmware command** |
| **Destroying** | — | Physically destroys storage medium. Methods: **disintegration, incineration, pulverizing, melting, shredding**; best for sensitive data |
| **Disposal** | — | Eliminates **non-confidential** information without data destruction; no impact on org goals/finances/individuals |

### Technique details
- **Overwriting**: write new data over old; multiple passes for strong security
- **Wiping**: clear device data so it can't be read; device reusable, keeps capacity
- **Erasure**: delete all data off-lease/reuse hard drives
- **Degaussing**: high-powered magnets disrupt magnetic field — magnetic media only (**not** optical CDs/DVDs); typically makes HDD inoperable; can damage nearby devices
- **Shredding**: breaks media into pieces **≤ 2 mm**; for data-center/stockpiles of old drives

## Card
What is data destruction and its main purpose?
?
Destroying stored data into an unreadable form so it can't be accessed/exploited; purpose = restrict unauthorized disclosure via proper disposal/destruction of media.

Name the 4 data destruction techniques.
?
Clearing · Purging · Destroying · Disposal.

Clearing protects against which attack? Purging?
?
Clearing vs keyboard/simple recovery attacks; purging vs laboratory (signal-processing) attacks.

Degaussing applies to which media and what side-effect?
?
Magnetic media only (not optical CD/DVD); typically makes the HDD inoperable and can damage nearby devices.

Shredding requirement for destroyed pieces?
?
Pieces no larger than 2 mm.
