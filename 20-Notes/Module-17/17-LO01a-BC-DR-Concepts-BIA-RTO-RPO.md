---
type: note
module: "17"
lo: "01"
tags: [process, mod/17]
topic: "BC vs DR, BCM, BIA phases, RTO vs RPO"
exam_weight: unknown
status: done
unresolved:
  - "p11 Phase 4 of BIA process not present in slice text (Phase 1, 2, 3 then Phase 5); omitted, not reconstructed"
  - "p11 Phase 3 third objective truncated as printed (recovery time frame to recover function and restore orga...); quoted in truncated form"
  - "p10 BIA body detail truncated (certain compo...); used slide sentence only for prioritised funding point"
  - "p5/p7 body prose truncated mid-sentence; used slide bullets plus complete prose sentences only"
---
[[MOC-Module-17]]

# BC/DR Concepts, BIA, RTO vs RPO (§17.01)

> **LO#01: Introduction to Business Continuity (BC) and Disaster Recovery (DR) concepts**
> Covers pp4–14. _(Mod 17 pp4–14)_

Terms introduced in this section: business continuity, disaster recovery, business continuity management (BCM), business impact analysis (BIA), recovery time objective (RTO), recovery point objective (RPO). _(Mod 17 p4)_

## Business continuity (BC)

- **Processes and procedures to ensure continuity of critical business functions during and after a disaster.** Integrated, corporate-wide process and set of activities to ensure **Information Availability**. _(Mod 17 p5)_
- ISO: **capability of the organization to continue the delivery of services or products at acceptable predefined levels following a disaster.** _(Mod 17 p5)_
- **Business-centric strategy** — emphasis on maintaining business operations over IT infrastructure. _(Mod 17 p5)_
- Comprehensive, enterprise-wide process; coordinated actions; aims to **reduce downtime** following disruption. _(Mod 17 p5)_

### Objectives of BC

- **Maintain continuity** of operations during and after a disruptive incident. _(Mod 17 p5)_
- **Protect reputation** by providing continuous services. _(Mod 17 pp5–6)_
- **Minimise effects** by promoting disaster preparedness. _(Mod 17 p5)_
- **Provide compliance benefits** — compliant organisations perceived as reliable by stakeholders. _(Mod 17 pp5–6)_
- **Mitigate business risks and minimise financial losses** — resilient network plus robust backup avoids breach risk and mitigates disaster losses. _(Mod 17 pp5–6)_

Related: [[MOC-Module-02]] (policy layer BCP answers to).

## Business continuity management (BCM)

- Process that **ensures continuity of operations after disruptive incidents**; framework to anticipate risks and internal/external threats. _(Mod 17 p7)_
- Responsible for **business recovery, crisis management, incident management, emergency management, contingency management**. _(Mod 17 p7)_
- Components named in slice:
  - **Crisis management (CM)** — respond under crisis, minimise damage to brand, operations, revenue; senior-management delay causes overlap of CM and BC plans/responsibilities. _(Mod 17 p7)_
  - **Emergency management** — procedures and actions after a crisis to **safeguard people from harm**. _(Mod 17 p8)_
  - **DR** (as BCM element) — plan to restore support systems (**hardware, IT assets, communications**) to **reduce downtime** and accelerate restoration. _(Mod 17 p8)_
- BCM involves: **identify potential threats, analyse possible impacts, build organisational resilience**; **update overall BCP** from training, exercises, reviews; **manage recovery of applications and continuation of activities** on disruption. _(Mod 17 pp7–8)_

### BCM goals

- **Ensure organisational resilience** to disruptive incidents and disasters. _(Mod 17 p7)_
- **Equip organisation to respond effectively** to natural, man-made, and technological disasters; protect business interests. _(Mod 17 pp7–8)_
- **Minimise financial losses** and other negative impact from disruption. _(Mod 17 pp7–8)_
- **Evaluate and improve resilience** to future disruptions (document reviews, mock drills). _(Mod 17 pp7–8)_

## Disaster recovery (DR)

- **Ability to restore business data and applications after a disaster**; set of procedures/policies to recover critical technology infrastructure. _(Mod 17 p9)_
- Covers **recovery of systems and people** rebuilding data centres, servers, other damaged infrastructure. _(Mod 17 p9)_
- **Data-centric strategy** — emphasis on restoring IT infrastructure and data (contrast BC business-centric). _(Mod 17 p9)_

### Objectives of DR

- **Reduce downtime** during and after a disaster; longer recovery worsens brand damage, dissatisfaction, revenue loss. _(Mod 17 p9)_
- **Reduce losses** accrued during and after a disaster. _(Mod 17 p9)_
- **Recover data damaged due to hardware failure**. _(Mod 17 p9)_

Contrast: BC = keep business functions running; DR = restore data/systems. See [[MOC-Module-16]] (incident/disruptive events DR plans against).

## Business impact analysis (BIA)

- **Systematic process** determining/evaluating **potential effects of interruption to critical business operations** from disaster, accident, or emergency. _(Mod 17 p10)_
- **Ascertains recovery time and recovery requirements** for various disaster scenarios. _(Mod 17 p10)_
- Interruption sources listed: labour disputes, supplier failure, political turmoil, terrorist attacks, natural or man-made disasters, cyberattacks, utility failures. _(Mod 17 p10)_
- Has **planning component** (risk-reduction strategies) and **exploratory component** (identifies vulnerabilities); results in a **report** describing risks and impacts on critical assets/business operations. _(Mod 17 p10)_
- Assumption: every component depends on all others, but **some components more crucial** — they get **larger funding** and **prioritised recovery**. _(Mod 17 p10)_
- **Analysis tool only — does not itself design or implement recovery solutions.** _(Mod 17 p10)_
- Included in the BCP. _(Mod 17 p10)_

### BIA process (multi-phase; no fixed guidelines)

- **Phase 1: Initiation** — on senior-management approval. Step 1: describe BIA **objectives and scope**. Step 2: **form BIA project team** (recruit internally or outsource). _(Mod 17 p11)_
- **Phase 2: Acquisition of Information** — interviews and **questionnaire surveys**; questionnaire = targeted questions assessing interruption effects and identifying critical assets; information reviewed, documented, re-evaluated for accuracy, summarised in **tables, schedules, diagrams**. _(Mod 17 p11)_
- **Phase 3: Analysis of Information** — evaluated manually or by computer; objectives: **prioritised list of processes/functions** (most important top); **technology and personnel** needed for optimal operations; **recovery time frame** to recover the function (as printed, truncated). _(Mod 17 p11)_
- **Phase 5: Presentation of the BIA Report to the Management** — final report submitted for decision-making; management uses it for **DRP strategies and BCP formulation**; BIA examines **RPOs and RTOs**, serving as **starting point for DR strategy**. _(Mod 17 p12)_

Related: [[MOC-Module-18]] (risk assessment BIA rests on).

## RTO vs RPO

| Term | Printed definition | Detail from slice |
|---|---|---|
| RTO | **Maximum tolerable length of time** a computer, system, network, or application **can be down** after failure/disaster. _(Mod 17 p13)_ | Established by **process owner during BIA**; measures time to return to pre-disaster levels; defines interruption extent and **revenue loss**; crucial to DRP; slide expresses in **minutes**, body in **seconds, minutes, hours, or days**; e.g. **45 minutes** means restart within 45 minutes or risk irreparable loss. _(Mod 17 p13)_ |
| RPO | **Maximum time frame for which an organisation loses data** after a major IT outage. _(Mod 17 p14)_ | Determines **acceptable data loss**; sets goals for **BC, DR, high availability (HA)**; crucial to DRP; expressed in **seconds, minutes, hours, or days**, measured from hosting-services-unavailable time; determines **minimum backup frequency**; e.g. **3-hourly backups** for 3-hour RPO, **96-hour interval** media for 4-day RPO. _(Mod 17 p14)_ |








