---
type: note
module: "16"
lo: "01"
tags: [concept, process, mod/16]
topic: "incident response concept, IRT roles, IR plan"
exam_weight: unknown
status: done
unresolved:
  - "p6 role label prints `CND Representative` beside the employee-issues (HR) definition; p7 prose calls the same function `HR Representative` — kept both forms as printed"
  - "p9 bullets render as `e`/`o` glyphs and the Components-of-IRP list is truncated across the page break — items quoted in printed order without reconstruction"
---

[[MOC-Module-16]]

# IR Concept, IRT Roles and IR Plan (§16.01)

> **LO#01: Understand the concept of incident response** _(Mod 16 pp4–9)_
> Covers pp4–9.

## IR concept _(Mod 16 p5)_

- **IR = process of taking organized and careful steps** when reacting to a security incident; sequence begins with **first identifying and reporting** an incident.
- IR processes **differ organization to organization** per business and operating environment.
- **Systematic approach** adopted to handle incidents with **minimal damage, recovery time, and costs**; during response, known: network vulnerability that caused the attack, who initiated it, kind of devices/files affected.

## Goals of IR _(Mod 16 p5)_

- Detect if an incident occurred and whether **actual incident vs false positive**
- **Maintain or restore Business Continuity**
- **Reduce impact** of an incident
- **Analyze cause** of an incident
- **Prevent future** attacks/incidents
- **Improve security and incident response**
- **Prosecute illegal activity**

## Advantages of IR _(Mod 16 p5)_

- Equips org with **safe procedures** to follow when an incident occurs
- **Saves time and effort** otherwise wasted fixing an encountered incident
- Learn from past experiences, **recover from losses more quickly**
- **Skills and technologies determined in advance**
- Saves org from **legal consequences** of a severe incident
- Determine **similar patterns** across incidents, handle them more efficiently

## IRT definition _(Mod 16 pp5–7)_

- **IRT = group of specialized people** who collectively **respond, remediate, mitigate, recover, and communicate** the impact of computer security breaches; works on an **incident response plan**.
- Maintaining a separate team is costly → orgs generally use current **employees expert in their fields + a few dedicated members**: net/sys admins, managers, stakeholders, employees, SOC analysts.

## IRT roles and responsibilities _(Mod 16 pp6–8)_

| Role | What the page says |
|---|---|
| Management | Top-most authoritative decision makers, single or group; **first entity to learn about an incident**; decide steps once confirmed |
| Information Security Team | Skills to **detect and analyze**; identify **nature, category, scope** |
| IT Staff | Sys/net admins; detect via **network traffic, system logs, service packages and patches**; report to management/IRT; **execute first response step** to avoid further damage |
| Physical Security Staff | Handle physical incidents; can be **first responders** to one; report **fire, theft, damage, unauthorized access** |
| Attorney | Legal advisor; ensures collected **evidence is admissible** in court; helps recover **financial loss** |
| HR Representative | Involved when an **internal employee** is in the incident; gives best solution for dealing with that employee |
| PR Specialist | Primary contact for **media**; updates website info, monitors coverage; stakeholder communication: **Board, Foundation personnel, Donors, Suppliers/vendors** |
| Financial Auditor | **Assesses financial loss**; accounts for all losses; reports **financial imbalance** in org account |
| IR Officer | **Oversees all IR activities**; executive-level (e.g. CISO); every IRT action reported to IR Officer → management |
| IR Manager | Technical expert in security + incident management; handles incident from **management and technical** view; responsible for **incident analysts'** actions; reports to IR Officer |
| IR Assessment Team | **Prioritizes** incidents by **amount of loss**; reps from **IT, security, application support, other business areas**; decides **classifications and severity** |
| IR Custodians | Technical experts / app support reps; key in **application incidents**; create an **action framework** shared with management |

## IR plan _(Mod 16 p9)_

- **IR plan determines future course of action** for establishing, managing, strengthening IR capabilities.
- Plan should: address **mission and vision** · meet **IR initiative goals** · comply with **senior management approval** statement · include **strategies to achieve set goals and timelines** · organized approach · identify **IR key performance indicators** for future reference · statement of **interoperability** · add value to other org processes · **efficient use of all resources** · strengthen security.
- **IRP = set of guidelines** created by the IRT **before** handling incidents, for dedicated formal response; contains elements for effective execution + response instructions for detected incidents; reflects company **size, structure, functions**; identifies required **resources**.
- IRP should include: **aim** · **objectives and approaches** · **methodology** · **standards to assess IR efficiency** · **observing current status** of IR.
- Components of an IRP: **name and contact info of the IRT** · **system details (data flow / network diagrams)** · **complete process for recording and handling** an incident · **report to Information Security and Policy (ISP), who appoints a security analyst** · **respond in a timely manner**.







