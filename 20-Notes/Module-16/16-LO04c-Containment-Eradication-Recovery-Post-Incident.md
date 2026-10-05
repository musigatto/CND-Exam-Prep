---
type: note
module: "16"
lo: "04"
tags: [process, bestpractice, mod/16]
topic: "incident containment, eradication, recovery, post-incident activities"
exam_weight: unknown
status: done
unresolved:
  - "p44 containment-strategy flow diagram is garbled OCR layout (Externd Support Inputs, Retwired?, Provkie Initial Resgnse, Assigwd) — box labels not transcribed, layout treated as non-evidence"
  - "p44 backup line OCR-garbled (Use a system o backup for further investigation) — quoted in essence only, exact wording uncertain"
  - "p47 eradication flow and p48 recovery flow are garbled OCR layouts — decision-box labels not transcribed, treated as non-evidence"
  - "p51 Figure 16.4 post-incident flow box names listed from figure layout only — running prose does not expand the five activities individually"
---

[[MOC-Module-16]]

# Containment, Eradication, Recovery, Post-Incident (§16.04)

> **LO#04: Describe the incident handling and response process** _(Mod 16 p44)_
> Covers pp44–51. Triage precedes this: [[16-LO04b-Triage-Classification-and-Notification]].

## Containment — limit scope, cut losses

- **Containment = controlling the effect of the incident immediately after its occurrence**; at this phase **evidence is collected and sent to the forensics department**. IRT role: **reduce magnitude/complexity, prevent further damage**; aim: **reduce losses/damages by mitigating vulnerabilities**. _(Mod 16 p44)_
- Compromised systems/networks/workstations — IRT decides: **shut down the system vs disconnect the network vs continue operations to monitor activity**; response **depends on type and magnitude** of the incident. _(Mod 16 p44)_
- Common containment techniques, in printed order: _(Mod 16 pp44–45)_
  1. **Disable specific system services temporarily** — reduce impact, keep operating.
  2. **Remove computer from network** when an unknown vulnerability affects it, until rectified.
  3. **Change passwords, disable the account** — and change passwords on **all systems interacting** with the affected system.
  4. **Complete backups of the infected system** — back up data to reduce damage during IR; keep a system backup for further investigation.
- **Temporary shutdown**: only if **no alternate options** — limits damage, buys analysis time. **System restoration**: replace recovered computers with a **trusted, clean backup**; first **identify sources (vulnerabilities, threats, access paths) and patch everything** before restoring. _(Mod 16 p45)_
- **Low profile** on network-based attacks: **do not tip off the intruder** — they may hit other systems and/or **erase everything to eliminate traceability**. Keep standard procedures: **IDS plus latest antivirus and anti-spam**. _(Mod 16 p45)_
- Containment strategy purpose: **control attack effects, restore normal state, ensure business continuity**. Key considerations: _(Mod 16 pp45–46)_
  - **Compromised code** — breach/intrusion risk; a minor mistake replicates it further.
  - **Safe storage** — data where intrusion cannot affect/alter it.
  - **Acquiring logs** — all system and router logs **before, during, and after** the incident.
  - **Identify risk factors** if operations continue; **inform admins/owners** of latest threats.
  - **Strong password policy** after IR; **maintain records** of every action; timely **auditing and monitoring**.
- Without guidelines: malware **spreads like wildfire**, haphazard response, network/systems/business/reputation down; stopgap actions cost money and time. Standing guidelines: **dedicated technical-expert team (first responder)**; **secure the affected area**, review identification-phase info; **honeypots as invisible traps**; **documented procedures** for management, IRT, administrators. _(Mod 16 p46)_
- p44 containment-strategy flow (technical/management/legal task assignment) is layout-only — not transcribed. _(Mod 16 p44)_

## Eradication — remove root cause, close vectors

- **Eradication = eliminating root cause (vulnerabilities, weaknesses, misconfigurations) from affected systems**; close all attack vectors to prevent recurrence. Countermeasures, in printed order: _(Mod 16 p47)_
  1. **Update antivirus** with new malware signatures and patterns.
  2. **Install latest patches** on systems and network devices.
  3. **Independent security audits**; check **policy compliance**, update obsolete policies/procedures.
  4. **Disable unnecessary services**.
  5. **Change passwords** of all compromised systems, accounts, network devices.
  6. **Eliminate access paths and exploits**.
  7. Install updated OS/software/services **only after removing traces of attack**.
  8. **Rebuild** affected systems, servers, databases, networks.
  9. **Validate effectiveness** of all corrective steps/countermeasures.
- p47 eradication decision flow (determine cause → check similar systems → recovery/escalation) is layout-only — not transcribed. _(Mod 16 p47)_

## Recovery — restore clean, restart, validate

- **Recovery = restoring lost data from backup media** after the cause is eliminated; **verify the backup is free of malware/attack vectors before restoring**. Duration depends on **extent of the breach**. Techniques: **network perimeter security, tightening user ID credentials, effective patch management, renewed file/software versions, rebuilding systems**. After recovery, **restart all withheld processes and services**. _(Mod 16 p48)_
- Decide **restore existing system vs complete rebuild** from backup. Two recovery steps: _(Mod 16 p48)_
  1. **Determine course of action** — strategies per impact; select per **resources, criticality, cost-benefit analysis**.
  2. **Monitor and validate** — no traces of cause, normal operation, **integrity of restored backup data**; regular **vulnerability assessments and penetration testing**; watch for **back doors**.
- Recovery-stage actions: **rebuild with a new OS**; **restore user data from trusted backups**; **examine protection and detection methods**; **examine security patches before installation, enable system logging**; determine backup integrity by **reading its data and verifying it** before restoring; **verify success/normal condition** after installing the backup; monitor via **network loggers, system log files, potential back doors**. _(Mod 16 p49)_
- p48 recovery flow (cause eliminated → data lost → restore from backup → restart services) is layout-only — not transcribed. _(Mod 16 p48)_

## Post-incident — learn, harden, document

- After eradication: activities that **improve response against future attacks** — discuss **limitations/problems faced**, eliminate them; **evaluate/improve IR effectiveness**; assess **lags in security posture, settings, configurations**; suggest **measures and security products**, review policies; **meetings with staff and stakeholders** on lessons learned; **update policies, procedures, posture, settings, configurations**; write an incident document (**details, vulnerabilities exploited, response measures, results, response pitfalls, communication/management drawbacks**); **document every IR step plus lessons learned**; **communicate updates to clients, customers, management, stakeholders**. _(Mod 16 p50)_
- Figure 16.4 (p51) shows the overall post-incident process flow — layout non-evidence; box names per the figure: Incident Documentation, Incident Impact Assessment, Review and Revise Policies, Close the Investigation, Incident Disclosure. _(Mod 16 pp50–51)_





