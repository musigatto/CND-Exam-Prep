---
type: exam
module: "meta"
tags: [exam]
topic: "Official CND exam facts and blueprint domain weights"
exam_weight: high
status: done
unresolved:
  - "Blueprint v4.0 'No. Of Questions' column does not reconcile with 100 x weight%. Not used to derive per-domain counts."
  - "The blueprint weights EXAM DOMAINS, not the 20 courseware modules. Any module -> domain mapping is inference and is not recorded here. Question bank therefore stays at 5 per module."
  - "Blueprint v4.0 excerpt captured from search engine text of the official PDF; domains 7-8 weights and Incident Response weight not captured verbatim. Re-read the PDF before citing."
---
# Official CND Exam Facts

> [!info] Source
> EC-Council official certification page + CND Exam Blueprint v4.0.
> Courseware PDF `Module 01` p13 states only duration/questions and defers passing score to the FAQ.

## Exam format

| Detail | Value | Source |
|--------|-------|--------|
| Exam code | 312-38 | EC-Council official page |
| Title | Certified Network Defender (CND) | EC-Council official page |
| Number of questions | 100 | Official page + Module 01 p13 |
| Duration | 4 hours | Official page + Module 01 p13 |
| Question type | Multiple Choice | EC-Council official page |
| Delivery | EC-Council Exam Portal / Pearson VUE | Module 01 p13 |
| Passing criteria | **Cut score varies by exam form, range 60%–85%** | EC-Council official page |

> [!danger] No fixed pass score
> There is **no** single passing percentage. The cut score is form-dependent (60%–85%).
> Any vault file claiming a fixed `60%` or `70%` is wrong. See [[Mock-Exam-100]].

Courseware wording, `Module 01` p13, exam details table:

```
Exam Title | Exam Code | Availability | Duration | Questions | Passing Score
CND        | 312-38    | EC-Council Exam Portal / VUE | 4 Hours | 100 | Pleas[e see FAQ]
```

## Blueprint v4.0 domain weights

> [!warning] Domains ≠ modules
> The blueprint weights **exam domains**. The courseware is split into 20 modules.
> No official module→domain mapping exists, so the question bank keeps its
> equal 5-per-module distribution rather than inheriting a guess.

| Domain | Weightage |
|--------|-----------|
| Network Defense Management | 10% |
| Network Perimeter Protection | 10% |
| Endpoint Protection | 20% |
| Enterprise Virtual, Cloud, and Wireless Network Protection | 15% |
| Incident Detection | 10% |
| Application and Data Protection | 10% |

Highest-weighted: **Endpoint Protection (20%)** → Windows, Linux, mobile, and IoT endpoint controls.

> [!caution] Partial capture
> Weights above are transcribed from the official v4.0 PDF but only a subset was
> captured verbatim. Treat as a study-priority signal, not an exam-authoritative table,
> until the PDF is re-read. See `unresolved:`.

## How this vault uses it

- Distribution stays **5 questions per module × 20 modules = 100** — see the repo `AGENTS.md`.
- Blueprint weights inform **which domains to study deeper**, not how many questions to write.
- Third-party weight tables are rejected — see [[External-Practice-Questions]].

## Related
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- [[External-Practice-Questions]] — third-party items, kept separate
- [[External-Flashcards-Quizlet]] — 239 SRS cards
