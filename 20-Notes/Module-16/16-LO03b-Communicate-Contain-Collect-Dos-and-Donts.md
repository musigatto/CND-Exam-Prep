---
type: note
module: "16"
lo: "03"
tags: [process, bestpractice, mod/16]
topic: "communicate, contain, control access, collect, record, don'ts"
exam_weight: unknown
status: done
unresolved:
  - "p23 body truncated: 'maintain a record of the services and appli...' — remainder not in slice."
---

[[MOC-Module-16]]

# Communicate, Contain, Collect — Do's and Don'ts (§16.03)

> **LO#03: Discuss do's and don'ts in first response** _(Mod 16 p20)_
> Covers pp20–27. Sibling: [[16-LO03a-Avoid-FUD-Assessment-Severity-and-Types]].

## Communicate the incident _(Mod 16 p20)_

- On suspected incident: **quickly identify who must be contacted inside and/or outside** the organization; **communicate the breach to the in-house IRT or Management** — quick response **minimizes extent of damage**.
- IRP includes **procedures and point of contact**: **clear idea of who to contact**; contact team/person must be an **expert in handling the incident**; a **dedicated team for contacting any external IR team**; contact via **phone, SMS, or e-mail** for immediate communication.

## Contain the damage _(Mod 16 p21)_

- **Disconnect vs stay connected** must be **decided by the forensic examiner or IR team** — both have adverse side effects:
  - **Disconnecting** during an attack → investigator **may not find evidence** that would have been found if connected.
  - **Staying connected** → attack may proceed and **cause further harm** to the network.
- **Coordinate with the forensic investigation team** to find evidence while ensuring **no further harm**.
- Common containment actions: **prioritizing components**; **identifying sensitive data, hardware, software**; **do not notify all employees**; **distinguish offline vs online handling**; **determine areas more likely to be attacked** and prevent further attacks; **build a new system** with all services/requirements plus **new administrative and service account passwords**.

## Control access to suspected devices _(Mod 16 p22)_

- **Secure the compromised device physically** — it is **potential evidence**; **keep under observation** until a forensics expert arrives; **do not tamper**.
- **Secure all supporting devices/media** found near it: **mobiles, CDs, DVDs, flash media, cables** — leaving any behind **can change the course of the investigation**.
- **Control access by lock and key** — no other user/employee access; **if premises can be locked down, lock them** until the forensic team arrives.

## Collect and prepare device information _(Mod 16 p23)_

- **Note down all information** related to the suspected device — helps the investigator; **document changes from incident until forensic team arrival**; if system is on, note everything gathered.
- Fields to record: **who, what, when and how the problem was discovered; IP address; system time; system name; services or applications running; any other relevant information about the crime**.
- Why: **who/what/when/how** aids initial findings; **IP addresses of all affected machines** must be recorded and such machines **not connected to the network to avoid data replication**; **system time** lets the investigator track changes across the timeframe; **running services/applications** can be the incident cause.

## Record your actions _(Mod 16 p24)_

- **Note down all actions** upon discovering the incident — for **actual attacks and false positives**; record **date/time of action** and **witnesses supporting the action**.
- Logs must be **descriptive** and in **chronological series** — non-chronological order **confuses the investigator**; **no speculations, only facts**.
- Courseware example — weak: receiving popups after the attack; ideal: **"Unknown popups were displayed on a Google Chrome browser for thirty minutes after the incident occurred."**
- Also note **serial/part number** of any affected network device or external drive; record **statements of affected users**.

## Refrain from investigating yourself _(Mod 16 p25)_

- **Do not start the investigation too early.** Even located evidence becomes **no longer admissible in court** if collected by a non-expert.
- Improper collection can **lose or destroy** evidence; worst case the responder faces **direct legal punishment / legal action by the organization** for tampering.
- Even if the cause seems known, **do not proceed alone** — **wait until authorized by the forensic team or management**; only an **expert collecting in a forensically sound manner** produces court-accepted evidence.

## Do not change device state _(Mod 16 p26)_

- **ON stays ON; OFF stays OFF** — changing state **may destroy valuable evidence**.
- **Restart/shutdown force internal changes**, making investigation difficult; leave the system **in the same state as when the incident occurred** until the forensic investigator advises.

## Disable virus protection _(Mod 16 p27)_

- **Antivirus can access files or change time/date stamps during automated scanning** and can **automatically delete suspected files, hacking tools** on the device — adverse effects on the investigation.
- It may **delete or change the state of evidence** and **remove files offering potential evidence** → experts advise the first responder to **disable virus protection as soon as they encounter an incident**.






