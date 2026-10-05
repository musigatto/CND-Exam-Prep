---
type: note
module: "17"
lo: "03"
tags: [process, bestpractice, mod/17]
topic: "BCP, DRP, NDRP goals and elements, risk mitigation, RTO and RPO"
exam_weight: unknown
status: done
unresolved:
  - "p20 prose truncated at 2000 chars: BCP goal detail after Prioritizing safety not fully visible; goals taken from the p20 tile list"
  - "p22 prose truncated at 2000 chars: DRP rapid-response goal sentence cut off after crucial for a DRP"
  - "p23 prose truncated at 2000 chars: NDRP threat-model and backup-plan sentences cut off"
  - "p24 prose truncated at 2000 chars: BCP strategy sentence cut off after procedures and technology, and"
  - "p26 prose truncated at 2000 chars: asset-inventory sentence cut off after Every item in an organizat"
  - "p21 tile text for BCP communication-plan goal partially garbled in OCR; used the p21 prose form"
---
[[MOC-Module-17]]

# BCP, DRP, NDRP and Plan Elements (§17.03)

> **LO#03: Explain Business Continuity Plan (BCP) and Disaster Recovery Plan (DRP)** _(Mod 17 pp19–26)_
> Objective as printed: to explain the BCP and the DRP and their goals. _(Mod 17 p19)_

## Business Continuity Plan (BCP)

- **BCP = comprehensive document** formulated to **ensure resilience against potential threats** and **allow operations to continue under adverse or abnormal conditions**. _(Mod 17 p20)_
- Prepared to help an organization **develop resilience to potential threats, thereby ensure BC**; during a disruption it **protects personnel and assets**; created **using inputs from several stakeholders**. _(Mod 17 p20)_

### BCP goals (tile list, p20)

- **Analyzing potential risks and losses** — analysis of risks impacting business; feeds continuity and recovery strategies; estimates financial losses from interruption of critical functions. _(Mod 17 p20)_
- **Enabling the risk management process** — lessen prospect of complete shutdown; guides recovery and prevention; predicts likelihood of disruptive events, determines extent, provides preventive measures. _(Mod 17 p20)_
- **Prioritizing safety, health, and welfare** of the organization and staff. _(Mod 17 p20)_
- **Minimizing infrastructural damage** in event of a disaster. _(Mod 17 p20)_
- **Restoring business conditions to pre-disaster levels**. _(Mod 17 p20)_
- **Maintaining vital documents and details** such as telephone numbers, employee, vendor, and client details. _(Mod 17 p20)_
- **Providing staff training, building awareness, promoting disaster preparedness** — employees aware of BCP, trained on types/purposes/objectives; includes pre-defined communication plan, contact with emergency services/vendors/media, control of negative information, assurance to stakeholders. _(Mod 17 pp20–21)_

See also: [[MOC-Module-02]] (policy layer the BCP answers to).

## Disaster Recovery Plan (DRP)

- **DRP developed for specific departments** within an organization **to help them recover from a disaster**. _(Mod 17 p22)_
- Developed to **respond to an unexpected disruptive event**; elaborates **preventive mechanisms to reduce disaster effects** to **continue or instantaneously resume critical business functions**. _(Mod 17 p22)_

### DRP goals (numbered 1–4, p22)

1. **Reduce overall organizational risk** — reduces likelihood and impact, increases resilience; conduct **risk assessment to identify critical vulnerabilities** before formulating. _(Mod 17 p22)_
2. **Alleviate concerns of senior management** — goals/scope aligned with senior management expectations; submitted for approval; approval ensures smooth implementation and enforcement. _(Mod 17 p22)_
3. **Ensure compliance with regulations** — minimizes chance of penalties from non-compliance. _(Mod 17 p22)_
4. **Provide rapid response after a disruption** — disaster causes customer dissatisfaction, revenue loss, reputational damage. _(Mod 17 p22)_

## Network Disaster Recovery Plan (NDRP)

- **NDRP ensures availability, integrity, and resilience** of computer network infrastructure during a disaster. _(Mod 17 p23)_
- Goal: **back up all network services and resources** that will run in events/threats such as **natural disasters, cyberattacks, hardware failures, or other unexpected incidents**. _(Mod 17 p23)_
- Factors to consider: **follow BC standards** as foundation; **test and revise often** per network configuration; **prioritize recovery objectives**; **build Zero Trust architecture** (no implicit trust, continual inspection/monitoring, strict access restrictions); **identify risks, build threat models** in advance (incl. external/malicious actors beyond system failure); **develop detailed backup plan**; decide **RTO and RPO for each essential service and data type** before developing strategy. _(Mod 17 p23)_

## Key elements of a good BCP (p24)

- **Risk assessment and business impact analysis** — after determining essential processes, assess risks (pandemics, cyberattacks, power disruptions, natural calamities); prioritize operations, develop mitigation strategy. _(Mod 17 p24)_
- **Planning an effective response** — actions to keep organization operating; covers employees, structures, procedures, technology. _(Mod 17 p24)_
- **Roles and responsibilities** — assigning and documenting roles of key personnel in disruption response. _(Mod 17 p24)_
- **Communication** — essential for coordinating responses, managing impact, minimizing downtime; maintains stakeholder trust. _(Mod 17 p24)_
- **Testing and training** — regularly scheduled tests keep BCP effective; proves employee readiness. _(Mod 17 p24)_

## Risk mitigation (p25)

- **Risk mitigation = technique a corporation uses to reduce exposure** to the many dangers it can encounter; risks can cause significant disruption or monetary loss. _(Mod 17 p25)_

## Elements of a good DRP (p26)

- **Recovery Time Objective (RTO)** — time organization is willing to keep assets down before recovery; time limit for restart of organization and IT services; determines measures and investment. _(Mod 17 p26)_
- **Recovery Point Objective (RPO)** — how much data organization is willing to lose; loss tolerance; determined by backup time frame and possible data-loss amount. _(Mod 17 p26)_
- **Communication plan** — comprehensive plan alerting entire organization; covers when/how to contact staff (workers, vendors, customers) plus backup options if regular means fail. _(Mod 17 p26)_
- **Recovery protocols for clients and stakeholders**. _(Mod 17 p26)_
- **Inventory of organization assets**. _(Mod 17 p26)_
- **Employee protection and safety strategy** for various disasters (fire, storm, intruder); get local employees to safety; remote workers assist with longer tasks. _(Mod 17 p26)_

See also: [[17-LO04a-BC-DR-Standards-and-Module-Summary]] (RTO/RPO reused in NDRP strategy; standards the plans follow).






