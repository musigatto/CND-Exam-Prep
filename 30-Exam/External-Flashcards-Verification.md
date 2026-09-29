---
type: exam
module: "ext"
tags: [exam]
topic: "Audit of Quizlet set 617277655 against the 20 module PDFs"
exam_weight: unknown
status: done
unresolved: []
---
# Flashcard Verification Audit

> [!info] Why this file exists
> Provenance only. The study material is [[External-Flashcards-Quizlet]] - 239 cards,
> each carrying its own `_(Mod NN pNN)_` citation, so you never need this file to
> check a fact. This records the 25 cards that did **not** make it into the deck.

## Result

| | Cards |
|---|---:|
| Verified, in the deck | 239 |
| Partially verified, held back in *Revision* | 19 |
| No basis in the courseware, dropped | 2 |
| Redundant repeat of another card, dropped | 4 |
| Contradicted by the courseware | 0 |
| **Original export** | **264** |

## The 19 held back

These are in *Revision* at the end of the deck, untagged so they stay out of your
review sessions. Each one is right about most of itself and wrong or unsupported
about one specific claim.

| Card | Topic | Where the courseware differs |
|---:|---|---|
| 4 | Message Digest Algorithm 5 | Card adds *not published by NIST*. The courseware says nothing about publication. |
| 15 | Firewall Analyzer | Courseware credits *automates threat remediation*; the bandwidth and compliance framing is not there. |
| 17 | SonicWALL firewall | SonicWall is named only as an example vendor. The UTM / VPN / anti-spam list is not in the courseware. |
| 29 | Windows User Account Control (UAC) | UAC is confirmed. The *sandbox mechanism* framing is not part of its definition. |
| 55 | OpenSCAP | Courseware says **SCAP**, the standard. The tool **OpenSCAP** is never named. |
| 66 | Application delivery | MAM is confirmed as *secure, manage, distribute* of enterprise apps. The *application delivery* list is not. |
| 79 | validating parsers using Document Type Definitions (DTD) and XML Schemas in IoT | DTD and XML-schema parser validation is confirmed. The link to the XMPP Bomb attack is not stated. |
| 95 | NIST | The NIST IoT topic is real, but the courseware never mentions **800.160**. |
| 107 | Sandbox feature for Microsoft Edge | Protected Mode / UAC / low integrity level is confirmed. Attributing it to Edge specifically is loose. |
| 132 | changing default password and using strong password | Strong-password guidance is confirmed. That it *prevents* brute force is not stated. |
| 162 | 802.15 | 802.15 is confirmed as the WPAN standard. *Fixed or portable devices* is not in the table. |
| 163 | Context-based signature | Context-based signatures are confirmed. *Cannot open backdoors* applies to undetected signatures, not this type. |
| 167 | tcp.flags==0x00 | The OS-fingerprint filter lost its text to OCR; no literal `tcp.flags==0x00` survives in the courseware. |
| 169 | tcp.flags==0x012 | The full-connect scan is confirmed. The filter value `tcp.flags==0x012` is not in the courseware. |
| 187 | Log analysis | The courseware has **one** tier, *Log analysis and storage*. The card splits it. |
| 188 | Log storage | Same: *Log analysis* and *Log storage* are a single tier, not two. |
| 197 | 1st rule of the First Responder | Courseware calls it the *First Response Rule* and says attempts are *avoided*, not *prevented*. |
| 207 | Disaster Recovery | Confirmed, but the courseware wording is *reduce business downtime and accelerate the restoration*. |
| 215 | ISO 22313:2020 | **The courseware says ISO 22313:2012.** The card's `:2020` is wrong. |

## Two with no basis in the courseware

| Card | Topic | Why |
|---:|---|---|
| 16 | WinGate Proxy Server | WinGate appears in none of the 20 modules. |
| 256 | Dynamic Threat Intelligence | The FireEye DTI service is not in the courseware. Module 20 p44 lists FireEye iSight, a different product. |

## Four redundant repeats

The export had the same fact twice in some cases. The shorter or typo'd copy was
dropped; the fuller one is in the deck. Nothing was lost.

| Card | Topic | Kept instead |
|---:|---|---|
| 42 | `rwx------` | 47, which adds the "useful for programs only one user may use" line |
| 44 | `rwxr-xr-x` | 48, byte-identical to 44 |
| 232 | Risk assessment | 218, which adds the risk-treatment sentence |
| 240 | IoEs' Identification | 236, identical once 240's leading `n this step` was fixed |

Two more terms repeat but are **kept both times**, because the pairs are genuinely
different facts: `Log analysis` (the tier vs. the process) and `Log storage`
(collection vs. the repository that holds it).

## Coverage gap worth knowing

**The deck covers none of Module 01 (Network Attack and Defense Strategies) or
Module 02 (Administrative Network Security).** Not one of the 264 exported cards
came from either. If you are revising those two modules, this deck will not help you.

## How it was checked

The 20 module PDFs are image-only, so the text was extracted with Windows OCR
(`en-US`) across 2,799 pages, then every card was matched by exact normalized
substring against its module and the page re-derived from the corpus. All 264 page
citations were then checked against the real PDF page counts. The first pass had put
35 cards on pages that do not exist; those were corrected here, and 3 cards
downgraded from *unsupported* to *partial* once re-read.
