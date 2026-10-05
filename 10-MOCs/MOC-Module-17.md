---
type: moc
module: "17"
tags: [concept, process, policy, bestpractice, mod/17]
topic: "Module 17 — Business Continuity and Disaster Recovery"
exam_weight: unknown
status: done
unresolved:
  - "p11 PHASE 4 OF THE BIA PROCESS IS MISSING. The slice prints Phase 1 (Initiation), Phase 2 (Acquisition of Information), Phase 3 (Analysis of Information), then Phase 5 (Presentation of the BIA Report). No Phase 4 exists in the source. Omitted, not reconstructed."
  - "p36 TILE VS PROSE WORDING DIFFERS. The tile prints 'DR is data-centric' while the prose prints 'recovery is data-centric'; the tile prints 'BR and DC' while the prose prints 'DR and BC'. The prose forms are quoted."
  - "p33 THE ASIS IDENTIFIER PRINTS AS 'ORM. 1.201' WITH ODD SPACING. Quoted as printed."
  - "p31 NO FINRA SOURCE URL IS RECORDED. The tile prints a garbled source line reading 'Snurcp wwwq nra.or' and no clean prose Source line is visible, so no FINRA URL appears anywhere in the notes."
  - "p34 THE FIGURE TILES SHOW BARE LAYOUT NUMBERS '2 3 4 7' next to standard names. Treated as non-evidence; standard titles taken from the prose list."
  - "p29 THE TILE PRINTS THE ISO SOURCE WITH A GARBLED SEPARATOR; the clean p29 prose form 'https://www.iso.org' is used. Recorded."
  - "p3 THE NUMBERED OBJECTIVE COLUMN OMITS LO#01'S NUMBER ENTIRELY while the prose list at the foot prints all four subjects cleanly. The prose list is authoritative."
  - "p16 THE RECOVERY AND RESTORATION SLIDE SENTENCES ARE TRUNCATED in the source; only complete clauses are used."
  - "p21 THE BCP COMMUNICATION-PLAN TILE TEXT IS PARTIALLY GARBLED IN OCR; the p21 prose form is used."
  - "p17 THE RESUMPTION SLIDE AND PROSE DISAGREE ON DETAIL (alternate-site wording); both kept."
  - "SCREENSHOT PAGES ARE NON-EVIDENCE: the p18 primary-site repair figure and the p34 numbered-standards figure. Prose steps and prose titles only; no diagram label was read."
---

[[MOC-Module-16]]

# Module 17 — Business Continuity and Disaster Recovery

> [!abstract] Scope
> **4 LOs** · PDF pp. 4–36 (book pp. 2526–2558) · **36 pages** · 4 notes · 21 cards.
> The smallest module in the courseware — and the densest per page. What BC and DR are and
> how they differ → the **BIA** and its phases → **RTO vs RPO** → the five activities →
> **BCP, DRP, NDRP** and their elements → the **standards** (ISO 22301, 22313, 27031,
> FINRA 4370, ASIS, and the p34–35 list) → module summary.
> **The shape trap:** BC is **business-centric**, DR/recovery is **data-centric** — the
> module states the contrast explicitly and the p36 summary repeats it. Every
> "which-plan" item turns on that axis. The second trap is **RTO vs RPO**: time-down vs
> data-lost, and the module prints both definitions twice (pp13–14 and p26) with
> different wording.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 17.1 | BC and DR concepts                                  | 4–14    | 2526–2536   | 1 |
| LO02 | 17.2 | BC/DR activities                                    | 15–18   | 2537–2540   | 1 |
| LO03 | 17.3 | BCP and DRP                                         | 19–26   | 2541–2548   | 1 |
| LO04 | 17.4 | BC/DR standards                                     | 27–36   | 2549–2558   | 1 |

p36 is the Module Summary and is carried in `17-LO04a`. p2 is the intentionally-blank
page, p1 the module divider, p3 the objective list.

## Technical focus

- **LO01 — concepts.** **BC** = processes and procedures ensuring continuity of critical
  business functions during and after a disaster; the ISO form: **capability to continue
  delivery of products or services at acceptable predefined levels**; **business-centric**,
  operations over IT. Five objectives (p5): maintain continuity · **protect reputation**
  through continuous services · minimise effects via preparedness · **compliance
  benefits** (compliant orgs look reliable) · mitigate risks and financial losses.
  **BCM** (p7) ensures continuity after incidents and owns business recovery, crisis,
  incident, emergency and contingency management; its goals: resilience · effective
  response to natural/man-made/technological disasters · minimise financial loss ·
  evaluate-and-improve via reviews and mock drills. Components: **Crisis management**
  (brand/operations/revenue under crisis) · **Emergency management** (procedures after a
  crisis to **safeguard people from harm**) · **DR as a BCM element** (restore hardware,
  IT assets, communications). **DR** (p9) = **ability to restore business data and
  applications**; **data-centric**, IT infrastructure over business. Three objectives:
  reduce downtime · reduce losses · **recover data damaged by hardware failure**. **BIA**
  (p10) = **systematic process** determining/evaluating interruption effects on critical
  operations; ascertains **recovery time and requirements**; has a planning and an
  exploratory component; ends in a **report**; **analysis tool only — designs and
  implements nothing itself**; included in the BCP. Phases as printed: **Phase 1
  Initiation** (objectives/scope, team) · **Phase 2 Acquisition of Information**
  (interviews, **questionnaire surveys**) · **Phase 3 Analysis of Information**
  (prioritised process list) · **Phase 5 Presentation of the BIA Report** (for DRP
  strategies and BCP formulation) — there is no Phase 4 in the source. **RTO** (p13) =
  **maximum tolerable length of time** a system **can be down**; set by the **process
  owner**; printed examples 45 minutes / 3 hours / 96 hours. **RPO** (p14) = **maximum
  time frame for which data is lost**; acceptable data loss; drives BC/DR/HA goals.
  _(Mod 17 pp4–14)_
  → [[17-LO01a-BC-DR-Concepts-BIA-RTO-RPO]]

- **LO02 — activities.** Five in order (pp15–18): **1. Prevention** (stop the hazard
  harming the org; e.g. **spending restrictions to DRP/BCP-listed items**; preventive
  controls that **deny unauthorised access without availability loss**) · **2. Response**
  (post-disaster needs assessment; **evacuate personnel, shut down systems**;
  notifications, **BCT activation**, initial briefing) · **3. Resumption**
  (**recommencement** at primary **or alternate** location; first decision is
  primary-vs-alternate; large-scale destruction → **emergency operations center**) ·
  **4. Recovery** (resume services on critical apps; restore the site to **stable and
  usable condition**) · **5. Restoration** (repair old site or build new; migrate back
  from recovery site; **primary-site only after physical damage**; ops team **splits in
  two**, both phases often **simultaneous**). _(Mod 17 pp15–18)_
  → [[17-LO02a-BC-DR-Activities]]

- **LO03 — plans.** **BCP** (p19) = **comprehensive document** for resilience allowing
  operations **under adverse or abnormal conditions**, built from inputs and protecting
  personnel/assets. Seven tile-list goals (p20): analyse risks/losses · **enable risk
  management** (predict likelihood, lessen shutdown prospect) · prioritise **safety,
  health, welfare** · minimise infrastructural damage · **restore pre-disaster
  conditions** · maintain **vital documents** (phone numbers, employee/vendor/client
  details) · **training and awareness** with pre-defined communications. **DRP** (p22) =
  built for **specific departments** to recover; four numbered goals: **reduce overall
  risk** (assess critical vulnerabilities first) · **alleviate senior-management
  concerns** (approval smooths enforcement) · **ensure regulatory compliance** ·
  **rapid post-disruption response**. **NDRP** (p23) = **availability, integrity,
  resilience** of network infrastructure; back up **all network services**;
  considerations: follow BC standards · **test and revise often** · prioritise recovery
  objectives · **build Zero Trust architecture**. Good-BCP elements (p24): **risk
  assessment + BIA** · effective response planning · **roles and responsibilities** ·
  **communication** (stakeholder trust) · **testing and training**. **Risk mitigation**
  (p25) = the technique reducing exposure. Good-DRP elements (p26): **RTO** (down-time
  willingness, restart time limit) · **RPO** (data-loss willingness, backup time frame) ·
  **communication plan** (when/how, plus backup channels) · client/stakeholder recovery
  protocols · **asset inventory** · **employee protection and safety** (fire/storm/
  intruder; remote workers take longer tasks). _(Mod 17 pp19–26)_
  → [[17-LO03a-BCP-DRP-and-Elements]]

- **LO04 — standards.** **ISO 22301:2019** (Security and Resilience — BCMS —
  Requirements, p28): implement/maintain/improve a system protecting against,
  reducing, preparing for, responding to and recovering from disruption; **generic**,
  any org or part; `Source: https://www.iso.org`. **ISO 22313:2012** (Societal
  Security — BCMS — Guidance, p29): **guides 22301**, good international practice
  across plan-establish-implement-operate-monitor; **no uniformity implied**, shape to
  legal/regulatory/industry needs. **ISO/IEC 27031:2011** (ICT Readiness for Business
  Continuity, p30): concepts/principles of **IRBC**, any org of any size. **FINRA Rule
  4370** (p31): government-authorized nonprofit; every member keeps a **written BCP**
  for emergency/significant disruption; **customized** but covering **backup/recovery
  and alternate communications** plus alternate staff locations; **registered-principal
  senior manager** approves with **annual review**; **written disclosure** at account
  opening / website / on request; **two emergency contacts** to FINRA (one senior
  principal); **mission-critical systems** incl. all securities-transaction logs. **ASIS
  ORM.1** (as printed, p33): integrated risk-based approach for **sustainability,
  survivability, resilience** of org and supply chain; prevention through recovery;
  ASIS itself is a **volunteer nonprofit with no regulatory, licensing or enforcement
  power**; `Source: www.asisonline.org`. Further titles (pp34–35): **ISO 22320:2018**
  (emergency management, **command and control**) · **ISO 31000:2018** (risk
  management guidelines) · **Guide 73:2009** (risk vocabulary) · **IEC 31010:2019**
  (risk assessment techniques) · **ISO/TS 22317:2021** (BIA guidelines) · **NFPA
  1600** · **NIST SP 800-34 Rev. 1**. _(Mod 17 pp27–36)_
  → [[17-LO04a-BC-DR-Standards-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 17 sits in blueprint domain 8 **Incident Prediction =
  15%** shared with modules 18, 19, 20 — see [[Exam-Facts]]. The bank uses a **flat 5
  per module**.
- Strong question sources, in rough order of yield:
  - **BC business-centric vs DR/recovery data-centric** — the module's master contrast.
  - **RTO (time down) vs RPO (data lost)** — both definitions, twice worded.
  - **The five activities in order** — prevention, response, resumption, recovery,
    restoration.
  - **The BIA**: definition, analysis-tool-only, report use, the printed phases with
    Phase 4 absent.
  - **BCP seven goals and DRP four goals**, especially which list holds training,
    vital documents, pre-disaster conditions (BCP) vs senior-management concerns and
    compliance (DRP).
  - **NDRP**: availability/integrity/resilience + Zero Trust.
  - **The standards table** — number-to-title matching, especially 22301 vs 22313
    (requirements vs guidance) and FINRA's two contacts + annual review.
  - **Trivia-looking items that are printed and therefore fair**: BCT, questionnaire
    surveys, 45-min/3-hour/96-hour RTO examples, mission-critical systems, IRBC,
    the BCP input list.
- Deliberate distractors to expect:
  - **"DR is business-centric"** — BC is; DR is data-centric.
  - **"RTO measures data loss"** — that is RPO; RTO measures down time.
  - **"The BIA designs recovery solutions"** — it is analysis-only.
  - **"Restoration runs at the alternate site"** — restoration is the **primary**
    site, after physical damage only.
  - **"ISO 22313 states requirements"** — 22313 guides; **22301** states requirements.
  - **"ASIS enforces compliance"** — no regulatory, licensing or enforcement power.
  - **"Phase 4 of the BIA is X"** — no Phase 4 is printed; any content for it is
    invented.
  - **"FINRA requires one emergency contact"** — two, one a senior principal.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-17")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/17-business-continuity-and-disaster-recovery-map.canvas|Business Continuity and Disaster Recovery Map]]
- Flow to visualize: **BC vs DR** (definitions → objectives → BCM → emergency
  management) → **BIA** (definition → phases → report) → **RTO vs RPO** → the **five
  activities** (prevention → response → resumption → recovery → restoration) → **BCP**
  (7 goals) → **DRP** (4 goals) → **NDRP** → plan elements + risk mitigation → the
  **standards** (22301 → 22313 → 27031 → FINRA 4370 → ASIS → the p34–35 list).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]] · [[Exam-Facts]]
- Related modules: [[MOC-Module-18]] (Risk Management — the risk assessment this
  module's BIA and mitigation rest on) · [[MOC-Module-16]] (Incident Response — the
  disruptive events this module plans against) · [[MOC-Module-02]] (Administrative
  Network Security — the policy layer the BCP answers to) · [[MOC-Module-19]]
  (Attack Surface — the threat landscape the BCP assumes).

## Unresolved
- **p11 prints no BIA Phase 4** — Phase 1, 2, 3, then 5.
- **p36 tile-vs-prose wording differs** (data-centric subject; BR/DC vs DR/BC).
- **p33 prints the ASIS identifier as `ORM. 1.201`** with odd spacing.
- **No FINRA Source URL is recorded** — the only printed form is garbled.
- **p34 bare layout numbers `2 3 4 7`** are non-evidence.
- **p3 omits LO#01's number** in the numbered column.
- **p16 Recovery/Restoration truncations** — complete clauses only.
- **The p18 primary-site figure and p34 standards figure are non-evidence.**
- **Deliberately not guessed**: BIA Phase 4 · the FINRA URL · the truncated slide
  tails on pp16, 20, 22–24, 26, 34–35 · any diagram label.

## Quick review
How many learning objectives does module 17 have, and what is LO#03's span
?
Four. LO#01 BC and DR concepts · LO#02 BC/DR activities · LO#03 BCP and DRP (pp19–26, book pp2541–2548) · LO#04 BC/DR standards

What is the difference between BC and DR as the module states it
?
BC is a business-centric strategy emphasising operations over IT — processes and procedures ensuring continuity of critical functions, and the ISO capability of delivering products or services at acceptable predefined levels. DR is a data-centric strategy emphasising IT infrastructure and data — the ability to restore business data and applications after a disaster

State RTO and RPO exactly as defined
?
RTO is the maximum tolerable length of time that a computer, system, network, or application can be down after a failure or disaster, established by the process owner. RPO is the maximum time frame for which an organisation loses data after a major IT outage, determining acceptable data loss. Printed examples: 45 minutes, 3 hours, 96 hours

What is a BIA, and what does it explicitly not do
?
A systematic process that determines and evaluates the potential effects of an interruption to critical business operations, ascertaining recovery time and requirements, ending in a report used for DRP strategies and BCP formulation. It is an analysis tool only — it does not itself design or implement recovery solutions

Which BIA phases are printed, and what is missing
?
Phase 1 Initiation, Phase 2 Acquisition of Information, Phase 3 Analysis of Information, Phase 5 Presentation of the BIA Report. No Phase 4 is printed anywhere — any content for it would be invented

The five BC/DR activities in order
?
Prevention (stop the hazard harming the org) → Response (post-disaster needs assessment, evacuate, shut down, BCT activation) → Resumption (recommencement at primary or alternate site) → Recovery (resume services on critical apps, stable usable condition) → Restoration (repair the primary site or build new, migrate back; physical damage only, ops team splits in two)

Which list holds staff training and vital documents — BCP or DRP goals
?
BCP. Its seven goals include providing staff training with pre-defined communications and maintaining vital documents such as telephone, employee, vendor and client details. The DRP's four goals are reduce overall risk, alleviate senior-management concerns, ensure regulatory compliance, and rapid post-disruption response

What does the NDRP ensure, and what architecture does it name
?
Availability, integrity, and resilience of the computer network infrastructure during a disaster, backing up all network services and resources. Considerations include following BC standards, testing and revising often, prioritising recovery objectives, and building Zero Trust architecture

Which standard states requirements and which guides it
?
ISO 22301:2019 states the BCMS requirements (generic, any organisation or part). ISO 22313:2012 guides 22301 with good international practice and implies no uniformity — shape the BCMS to legal, regulatory and industry needs

What does FINRA Rule 4370 require of members
?
A written BCP for emergency or significant business disruption, customised but covering backup/recovery and alternate communications plus alternate staff locations. A registered-principal senior manager approves it with annual review. Written disclosure at account opening, on the website, or mailed on request. Two emergency contacts reported to FINRA, at least one a senior-management registered principal

Why can ASIS never be the answer to an enforcement question
?
ASIS is a volunteer nonprofit professional society with no regulatory, licensing, or enforcement power — it does not enforce compliance and does not list, certify, test, inspect, or approve anything

What does the module summary say BC and recovery respectively centre on
?
BC is business-centric while recovery is data-centric (prose form). DR is the ability to restore data and applications, employed on data centers, servers and infrastructure. Main activities: prevention, response, resumption, recovery, restoration
