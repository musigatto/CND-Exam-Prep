---
type: note
module: "16"
lo: "04"
tags: [process, bestpractice, mod/16]
topic: "IR vision, preparation, and incident recording"
exam_weight: unknown
status: done
unresolved:
  - "p29/p32/p34-p35: IR overview, preparation, and recording flow diagrams treated as non-evidence; diagram-only tile/sidebar labels not read out."
  - "p35: courseware prints 'preempted questionnaire'; quoted verbatim, not corrected."
  - "p33: infrastructure bullet list OCR interleaves 'Page 2425' mid-list; order of the 8 items as printed is uncertain."
---

[[MOC-Module-16]]

# IR Vision, Preparation, and Recording (§16.04)

> **LO#04: Describe the incident handling and response process** _(Mod 16 p28)_
> Covers pp28–36. See also [[16-LO04b-Triage-Classification-and-Notification]] for the next steps (triage, classification, prioritization, notification).

## IR process ground rules (prose only)

- IR process **varies across organizations** per business and operating environment; a **pre-defined framework** is used to build a sound response _(Mod 16 p29)_
- Each IR process defines rules such as _(Mod 16 p29)_:
  - **Restore the normal state** of the system in the **shortest possible time**
  - **Minimize impact** on other systems
  - **Avoid further incidents**
  - **Identify the root cause** and rectify it in a short time
  - **Assess impact and damage**; recover corrupted or deleted data
  - **Update security policies and procedures** as needed
  - **Collect evidence** to support the investigation to follow

## Determining the need for IR

- Cyber-attacks increased in **number, diversity, damage, disruption**; can gather personal and business sensitive data → effective, timely response necessary _(Mod 16 pp29–30)_
- Need determined by: **current security scenario, risk perception, business advantages, legal compliance requirements, other organizational policies, previous incidents**, among other factors _(Mod 16 p30)_
- IR allows **preventive activities based on risk assessments** but **cannot prevent all** incidents _(Mod 16 p30)_
- IR necessary for: **detecting incidents, reducing loss and destruction, mitigating exploited weaknesses, restoring IT services** _(Mod 16 p30)_
- **Inputs, complaints, queries from all stakeholders** in business processes affect the decision _(Mod 16 p30)_
- Initiators: **IRT development project team, executive manager, head of information security department**, or any person **exclusively designated by management** _(Mod 16 p30)_

## Purposes of IR management and process

- **Protect systems** — high security plus special access controls on all resources is costly/constrained; best strategy is **quickly detect and recover**; efficient IR keeps **critical business operations** running before, during, after _(Mod 16 p30)_
- **Protect personnel** — swift IR ensures **no physical damage** to human resources from workplace incidents _(Mod 16 p30)_
- **Efficiently use resources** — technical and managerial resources always **limited**; respond as quickly as possible; gained information helps **prevent or better handle future incidents** _(Mod 16 p30)_
- **Address legal issues** — compliance with laws such as **HIPAA** and **FISMA**; stay safe against **legal and public liabilities**; per **US Department of Justice**, illegal to use **certain monitoring techniques**; procedures must guarantee **non-violation of legal statutes** _(Mod 16 p30)_

## IR vision

- Vision = **purpose and scope** of planned IR capabilities; instructions to **detect, manage, respond**; defines **areas of responsibility** and procedures; documentation plus **preventive actions** against potential threats to the information system _(Mod 16 p31)_
- IR plan covers _(Mod 16 p31)_:
  - How does **information pass** to appropriate personnel
  - How should an incident be **assessed**
  - Incident **containment and response strategy**
  - How should **systems and resources be restored**
  - **Documentation** of the incident
  - **Preservation of evidence**
  - How should the incident be **reported** to appropriate personnel
- Key elements of the vision statement _(Mod 16 p31)_:
  - What IR capability is it aiming to **protect**
  - Short- and **long-term goals of the IRT**
  - **Services** the IRT will offer
  - How IR capabilities ensure **business continuity**
  - Required **resources**, cost justified with effective **return-on-investment**
- **Communicate the vision to all stakeholders**; publish in an **easily accessible repository after appropriate approvals** _(Mod 16 p31)_

## Preparation phase

- **Initial phase**: establishment and **training of the IRT**, acquiring all **necessary tools and resources**; readiness **prior to** the incident event _(Mod 16 p32)_
- Establishing defense/controls per threats on _(Mod 16 p32)_:
  - **Open systems** vulnerable to attacks
  - **Secured systems with no IR**
  - Systems dealing with incidents **to be secured**
- Developing methods to deal with incidents _(Mod 16 p32)_:
  - **Measures** for different situations by staff
  - **Contact information**
  - Keeping information from **neighboring organizations**
  - **Assigning people** to the IR effort
  - Determining **risk levels and limits**
- Acquiring resources and people: **monetary resources** for hardware, software, training, special analysis/forensics equipment; examples **PDAs, safe vaults, IDS software, database server software** _(Mod 16 p32)_
- Infrastructure supporting IR: incorporate mechanisms into processes via **overall business strategy** _(Mod 16 p33)_:
  - Line of **authority and management** in place
  - Defenses/controls **matching network resources**
  - IR procedures **followed effectively**
  - Resources with **proper finances**
  - **Contact details** maintained
  - **Evidence of IRs stored**
  - **Legal issues** addressed
- System administrator responsibilities for preparation _(Mod 16 p33)_:
  - Ensuring **password policies**; **disabling default accounts**
  - Configuring appropriate **security mechanisms**
  - Executing/enabling **system logging and auditing**
  - **Patch management**; ensuring **proper backups**
  - Ensuring **integrity of file systems**; identifying **abnormal behavior**

## Incident recording and assignment

- Recorded by **IT support** raising a ticket after a user/employee finds **abnormal change or indicators**; also via **SIEM, IDS, antivirus, integrity checking software**; some incidents **clearly noticeable** _(Mod 16 p34)_
- Recorded on _(Mod 16 pp34–35)_:
  - **IDS and firewall alarm** on anomalous data packets
  - **Antivirus alert** during scanning
  - Repeated **unsuccessful login attempts** in system/network logs
  - Data **unexpectedly corrupted or deleted**; **unusual system crashes**
  - Attacker/intruder **damage to systems** holding important network data
  - **Audit logs** / system and security log files show **suspicious activity**
  - Staff member identifies **unusual/suspicious activity**, policy-violating content on a colleague's computer, **phishing emails**, **website defacement**, **non-working-hours** unauthorized access, **social engineering attempts**
- Handling flow _(Mod 16 pp35–36)_:
  1. Employee **calls IT support**; support records call, triages with the **"preempted questionnaire"** based on incident type
  2. Suspected security incident → **assigned to IR team via ticketing system**
  3. Help desk **interviews victim/reporter** (more details; whether triggers accessed accidentally) to assess incident type
  4. Help desk sends report plus interview details to the **incident handler**, who assigns a **first responder** for analysis and validation
  5. First responder analyzes **compromised systems, network, databases, devices**; **lists compromised elements** (systems, applications, services, devices); updates handler via same ticketing system
  6. Check against **previous incidents** — match → **reopen previously closed incident**; else **create record** (security alerts, indicators, IT department info)
  7. Validated incident → **IRT assigned**; IRT takes over with **judgement and critical reasoning**, structured approach
  8. IR team manager **classifies and prioritizes high, medium, low**; attend **high first**, then medium, then low






