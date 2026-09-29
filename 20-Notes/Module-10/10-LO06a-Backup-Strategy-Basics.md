---

type: note
module: "10"
lo: "06"
tags: [process, bestpractice, concept, mod/10, flashcard/10]
topic: "Backup Basics — Definition, Data Loss Causes, Strategy, Media"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Introduction to Data Backup (§10.6.1)

## What it is
- **Data backup** = making a duplicate copy of critical data (physical/paper + computer records)
- Two purposes: **reinstate a system to normal working state** after damage · **recover data/information** following data loss or corruption
- Retrieving lost files = **restoring/recovering files**; backup + retention plan mandatory for all organizations

## Reasons for data loss
| Cause | Examples |
|---|---|
| **Human error** | Accidental/purposeful deletion, misplacement of storage devices, DB administration errors |
| **Crimes** | Stealing or modifying critical data |
| **Natural causes** | Power failures, sudden software changes, hardware damage |
| **Natural disaster** | Floods, earthquakes, fire |

## Benefits
- Access to critical data even during disaster; prevents business loss
- Recovery → business continuity; retrieve data anytime
- Regular scheduled backup = efficiency + avoids severe asset damage

## Data backup strategy/plan (8 steps)
1. Identify the **critical business data**
2. Select the **backup media**
3. Select a **backup technology**
4. Select the **appropriate RAID levels**
5. Select an **appropriate backup method**
6. Select the **backup types**
7. Choose the **right backup solution**
8. Conduct a **recovery drill test**

- Strategy features: data recovery from external devices (servers, hosts, laptops) · must cover natural-disaster recovery · earliest recovery · **lower cost = more financial benefit** · **auto recovery options** (reduce human error)

## Selecting the backup media
| Factor | Meaning |
|---|---|
| **Cost** | Fits budget; media must have more space than the data |
| **Reliability** | Not susceptible to damage/loss |
| **Speed** | Fewer human interactions; completes when machine idle |
| **Availability** | Always available after data loss |
| **Usability** | Easy to use, flexible |

### Media devices
| Media | Capacity | Notes |
|---|---|---|
| **Optical disks** (CD/DVD/Blu-ray) | ~200 GB | Affordable, easy storage/transport; frequent manual disk swaps; slow record/verify |
| **Portable hard drives / USB flash** | no limit | Higher capacity than optical; more expensive; ideal home/small office; faster backups |
| **Tape drives** | no limit | Enterprise-level media; easy store/transport; expensive |

## Cards
Primary purposes of a data backup?
?
Reinstate a system to its normal working state after damage, or recover data/information following data loss or corruption.

Four categories of data-loss causes.
?
Human error · crimes · natural causes (power/software/hardware) · natural disaster.

8-step data backup strategy?
?
Identify critical data → select backup media → backup technology → RAID levels → backup method → backup types → right solution → recovery drill test.

Backup media selection factors?
?
Cost, reliability, speed, availability, usability.
