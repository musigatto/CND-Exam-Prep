---
type: exam
module: "meta"
tags: [exam]
topic: "Official CND exam facts and blueprint domain weights"
exam_weight: high
status: done
unresolved:
  - "Blueprint v4.0 prints 'No. Of Questions = 5' for EVERY domain (8 x 5 = 40), which contradicts the 100-question exam. The Weightage column is the reliable one; the question-count column appears to be a leftover from an earlier exam length. Distribution below is derived from Weightage."
  - "Handbook p18 says 'clicking on the selected response(s)'. The '(s)' leaves open whether multi-select items exist. EC-Council does not state single-answer-only anywhere in the handbook. Treat as unresolved."
  - "The downloaded handbook file is named CND-Handbook-v6.1.pdf but its internal footer reads 'CND Candidate Handbook v6.3'."
  - "Blueprint v4.0 page 1 extracted text says 'CND Exam Blueprint v3.0' while the document title says v4.0."
---
# Official CND Exam Facts

> [!info] Sources — both official, both downloaded and read
> - **CND Exam Blueprint v4.0** — `cert.eccouncil.org/wp-content/uploads/2024/04/CND-Exam-Blueprint-v4.pdf`
> - **CND Candidate Handbook** — `cert.eccouncil.org/images/doc/CND-Handbook-v6.1.pdf`
>
> Third-party restatements of these facts live in [[External-Practice-Questions]] and are
> **not** authoritative. Where they differ from the tables here, these tables win.

## Exam format

| Detail | Value | Source |
|--------|-------|--------|
| Exam code | 312-38 | Blueprint header |
| Title | Certified Network Defender (CND) | Blueprint header |
| Number of questions | 100 | Handbook p7, p46; Module 01 p13 |
| Duration | 4 hours | Handbook p7, p46; Module 01 p13 |
| Question format | Multiple choice, "clicking on the selected response(s)" | Handbook p18 |
| Delivery | EC-Council Exam Portal / Pearson VUE | Module 01 p13 |
| Credential | ANAB-accredited | Handbook p7, p46 |

Courseware wording, `Module 01` p13:

```
Exam Title | Exam Code | Availability | Duration | Questions | Passing Score
CND        | 312-38    | EC-Council Exam Portal / VUE | 4 Hours | 100 | Pleas[e see FAQ]
```

> [!danger] No fixed pass score — now confirmed officially
> - Handbook p65 §1.6: "**Passing Criteria** shall mean passing criteria for an EC-Council
>   certification exam **which may vary from exam to exam**."
> - Handbook p19: a panel "will answer and rate all items to deduce a **minimum passing or cut
>   score**. **Scores vary from one exam to another** due to the score dependence on the items
>   pool difficulty."
> - EC-Council's certification page states the cut score **ranges 60%–85%** by exam form.
>
> **Never hardcode 60% or 70% as a pass mark.** See [[Mock-Exam-100]].

You may mark questions and review them before ending the test (Handbook p46).

## Blueprint v4.0 — official domain weights

| # | Domain | Weightage | Questions implied by weight |
|---|--------|-----------|------------------------------|
| 1 | Network Defense Management | 10% | 10 |
| 2 | Network Perimeter Protection | 10% | 10 |
| 3 | Endpoint Protection | **20%** | 20 |
| 4 | Application and Data Protection | 10% | 10 |
| 5 | Enterprise Virtual, Cloud, and Wireless Network Protection | 15% | 15 |
| 6 | Incident Detection | 10% | 10 |
| 7 | Incident Response | 10% | 10 |
| 8 | Incident Prediction | 15% | 15 |
| | **Total** | **100%** | **100** |

Highest-weighted: **Endpoint Protection, 20%** — Windows, Linux, mobile and IoT endpoint controls.
Then Enterprise Virtual/Cloud/Wireless and Incident Prediction at 15% each.

## Module → domain mapping (from the blueprint, not inferred)

The blueprint's **sub-domain labels are the courseware module names**, so this mapping is read
directly off the PDF rather than guessed:

| Domain | Courseware modules |
|--------|--------------------|
| Network Defense Management | 01 Network Attack and Defense Strategies · 02 Administrative Network Security · 03 Technical Network Security |
| Network Perimeter Protection | 04 Network Perimeter Security |
| Endpoint Protection | 05 Windows · 06 Linux · 07 Mobile · 08 IoT |
| Application and Data Protection | 09 Administrative Application Security · 10 Data Security |
| Enterprise Virtual, Cloud, and Wireless | 11 Enterprise Virtual · 12 Enterprise Cloud · 13 Enterprise Wireless |
| Incident Detection | 14 Network Traffic Monitoring · 15 Network Logs Monitoring |
| Incident Response | 16 Incident Response and Forensic Investigation |
| Incident Prediction | 17 BC/DR · 18 Risk Management · 19 Attack Surface · 20 Threat Intelligence |

3+1+4+2+3+2+1+4 = 20 modules. ✔

Weights are **not** divisible per module (10% over 3 modules is 3.33% each), so a strict
per-module split is impossible. The vault therefore uses **5 questions per module** as a flat
approximation — see the repo `AGENTS.md`.

## Exam item confidentiality — no real dumps exist

Handbook p61–p65 makes exam items protected confidential information, forbids reverse
engineering them, and defines a formal **Exam Item Evaluation** challenge process. Consequence:
**no website can legitimately be selling real 312-38 items.** Every third-party question set is a
simulation. See [[External-Practice-Questions]] for the sources tried and their defects.

## Related
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- [[External-Practice-Questions]] — third-party items, kept separate
- [[External-Flashcards-Quizlet]] — 239 SRS cards
