---
type: note
module: "16"
lo: "04"
tags: [process, mod/16]
topic: "incident triage, classification, prioritization, notification"
exam_weight: unknown
status: done
unresolved:
  - "p37-p38/p41: triage (Fig 16.2) and notification (Fig 16.3) flow diagrams treated as non-evidence; prose only."
  - "p37: line 'Incident Falls Outside Purview' and 'Other Organizational Departments' appear as diagram fragments; meaning taken from p39 prose instead."
  - "p40: sentence fragment 'members of an IRT' opens the page (truncated); not quoted."
---

[[MOC-Module-16]]

# Triage, Classification, and Notification (§16.04)

> **LO#04: Describe the incident handling and response process** _(Mod 16 p37)_
> Covers pp37–43. Follows [[16-LO04a-IR-Vision-Preparation-and-Recording]] (vision, preparation, recording).

## Triage — three steps

- Triage = **incident analysis and validation, incident classification, incident prioritization** _(Mod 16 p37)_
- IRT assesses details, **correlates indicators with logs and system files** to validate and determine impacted systems, networks, devices, applications; then **classifies by type**; then the **IRT manager prioritizes high, medium, low** — **high first** _(Mod 16 p37)_
- Classification methods: compare standard criteria **before and after** the incident — **network performance, system behavior, logs, event correlation, data packets, network traffic, files, applications** _(Mod 16 p37)_
- By impacted resource / source of compromise / tools used: **endpoint, network, malware, application, browser** incidents _(Mod 16 p37)_
- Prioritization depends on **severity of impact and effect on business**; classification also weighs **nature of incident, criticality of systems, number of systems, legal and regulatory requirements**; outside IRT purview → **contact other organizational departments** _(Mod 16 p37)_

## Analysis and validation

- Analyze indicators to verify **security incident vs hardware/software error**; evaluate **each indication for legitimacy**; find **sources of indicators**, examine **security solutions**, verify **system and device logs**, identify **incident and vectors** _(Mod 16 p38)_
- Accurate indication **does not necessarily mean** an incident occurred; e.g. **web server crash, modification of sensitive files** can be **human errors** _(Mod 16 p38)_
- Outcome: **IRT handles it, register with no further action, or pass to other teams** _(Mod 16 p38)_
- Validation determines **attack details: type, vectors, duration, source, evidence**; and **affected resources and data, systems, networks, servers, services; business impact; types of losses** — feeds classification and prioritization _(Mod 16 p38)_

## Classification

- Depends on **potential targets and severity of impact**; purpose is gathering all required information to determine **category, time to resolve, other criteria**; IRT **evaluates details and correlates with indicators** _(Mod 16 pp38–39)_
- Classify by **severity, affected resources, attack methodology**; factors _(Mod 16 p39)_:
  - **Nature of the incident**
  - **Criticality of the systems impacted**
  - **Number of systems impacted**
  - **Legal and regulatory requirements**
- Outside purview → **contact other organizational departments** _(Mod 16 p39)_
- Advantages of effective classification _(Mod 16 p39)_:
  - Every incident **correctly forwarded** to respective department
  - **Faster response** via correct routing
  - Aids an effective **knowledge base**
  - **Increased customer satisfaction**

## Prioritization

- **Most critical decision** in IR; **never first-come, first-served**; determines the **sequential order** of response _(Mod 16 p39)_
- Prioritize **highest business impact** so business services continue with **minimal financial losses**; depends on **severity of impact, importance of compromised resources, disrupted operations, losses incurred** _(Mod 16 p39)_
- Responder sorts **compromised elements by business-continuity importance**, assigns a team by evaluating **impact + detection/containment methods**; also manages **IR staff and resources**; assigns **priority level, predefined criteria and requirement, urgency in restoring** the resource _(Mod 16 p39)_
- Benefits: minimize **business disruption, financial and reputational loss**; reduce time on **containment, eradication, recovery**; easier **task scheduling and status reporting** to stakeholders/customers _(Mod 16 pp39–40)_
- Categorization with **common terminology** communicates events across departments; enables focus on incidents needing more attention _(Mod 16 pp39–40)_
- Two basic elements _(Mod 16 p40)_:
  1. **Impact** — severity for the organization; measured by **number of systems impacted** → idle employees → lost productivity
  2. **Urgency** — usually defined by the **SLA**; resolve at the earliest opportunity
- Both generally have three levels: **high, medium, low**; relative importance varies by organization _(Mod 16 p40)_

## Notification

- Incidents communicated to **internal and external stakeholders**; coordination **reduces impact**; keep **IRT members** informed of process, results, responsibilities _(Mod 16 p41)_
- Responders communicate **severity to management/authorized persons** to get **approvals** for IR procedures; first communication includes **first report, initial assessment processes, detection methods, impacted resources, management strategy** _(Mod 16 pp41–42)_
- Discuss with a **legal representative** to file suit against perpetrators; after approval, communicate relevant matters to **necessary stakeholders**; **all employees/stakeholders must report** suspected breaches to the IRT; IRT lead discusses breach with **core team + organization members** _(Mod 16 p42)_
- **External party** gets only part of the situation and only **after management approval**, when external support is needed; after control/mitigation, disseminate **details and lessons learned** via organization and media for awareness _(Mod 16 p42)_
- Response strategy depends on **circumstances**; plan weighs **political, technical, legal, business** factors _(Mod 16 p42)_
- Resource factors for investigation _(Mod 16 p42)_:
  - **Forensic duplication** of related systems; **criminal referral**; **civil litigation**
  - What is the **range of impact**; how **sensitive** is compromised/stolen info; **who are attackers**; is **public aware**; what **access level** gained; attacker **skills**; total **downtime** (system + user); total **loss in dollars**
  - Initial-response information is key to strategy choice; **reinvestigate details before selecting** strategy
- IRT notification and planning duties _(Mod 16 p43)_:
  - **Notifying management**: IRT notifies management of the incident **and its effects**
  - **Communicating**: obtain **documented management approval** first; **do not hide** info; inform **likely-affected people**
  - **Disclosing details**: seek **approval for disclosure**; certain stakeholders need the details; if **denied, proceed with IR procedure** anyway
  - **External support**: check whether needed before in-depth investigation; if yes, **contact external agencies**; then **IRT + management proceed** with handling and response plan






