---
type: note
module: "16"
lo: "03"
tags: [concept, process, bestpractice, mod/16]
topic: "avoid FUD, initial assessment, incident and severity types"
exam_weight: unknown
status: done
unresolved:
  - "p16 True Negative prints as 'An alarm is raised when no attack is detected. Non-malicious files are rejected successfully' — internally contradictory; quoted verbatim, not interpreted."
  - "p17 body truncated: 'Note down all actions performed during the occurrence of t...' — remainder not in slice."
  - "p18 body truncated: false negatives 'may lead to a cybersecu...' — remainder not in slice."
---

[[MOC-Module-16]]

# Avoid FUD, Initial Assessment, Severity and Types (§16.03)

> **LO#03: Discuss do's and don'ts in first response** _(Mod 16 p14)_
> Covers pp14–19. Sibling: [[16-LO03b-Communicate-Contain-Collect-Dos-and-Donts]].

## LO context _(Mod 16 p14)_

- **Misleading / inappropriate first-response steps** can place the organization in **undesired situations** — due to **lack of knowledge or skills** for first response.
- Objective of section: discuss **Do's and Don'ts** to **avoid undesired situations**.

## Avoid FUD _(Mod 16 p15)_

- Slide rule: if you discover an incident — **do not panic**; **do not perform actions that damage evidence integrity**; **escalate and consult management or the in-house computer forensics investigation team quickly**.
- **FUD = Fear, Uncertainty, and Doubt** — not new; any incident creates **fear and anxiety**; decisions made in **fear/anxiety worsen the situation**.
- Small companies often have **no IRT** → first responders **lack confidence**.
- First response in fear/uncertainty can **forego important, resourceful information**, **mislead the investigation team**, **delay identifying why the incident occurred**.
- A panicking decision can **affect evidence quality** → first responder should be **confident**; if unsure, **consult top management, the information security team, or the in-house IRT**.

## Initial assessment _(Mod 16 pp16–17)_

- On any indication of a security incident:
  - **Check actual incident vs false positive.**
  - **Identify category and severity.**
- Assessment determines: **source of the incident**; **false positive vs actual incident**; **severity** → drives **immediate actions** and **minimizes risk**.

## Alert-based incident types _(Mod 16 pp16–18)_

| Type | Printed meaning |
|---|---|
| False Positive | **Alarm raised when no attack occurred**; non-malicious activities identified as dangerous _(Mod 16 p16)_ — e.g. brute-force alert that was only an **authenticated user retrying login** _(Mod 16 p18)_ |
| True Positive | **Alarm raised when an actual attack occurred**; actual malicious event identified → **act immediately to stop it continuing** _(Mod 16 pp16–18)_ |
| False Negative | **No alarm raised when an actual attack occurred**; malicious activities not recognized; caused by **rules not defined properly** _(Mod 16 pp16–18)_ |
| True Negative | As printed: **"An alarm is raised when no attack is detected. Non-malicious files are rejected successfully"** _(Mod 16 p16)_ — see `unresolved` |

## CND categories of incidents _(Mod 16 p16)_

| Category | Description as printed |
|---|---|
| Unauthorized Access | Attacker gains **unauthorized access to system resources** |
| Denial of Service (DOS) | Attack causing **unavailability of services for authorized network users** |
| Malicious Code | **Malware (virus, worm, Trojan horse, keyloggers, spywares, rootkits, backdoors)** infecting OS and/or applications |
| Improper Usage | Individuals using system resources **against acceptable usage policies** |
| Scans/Probes/Attempted Access | Attacker activity to **identify open ports, protocols, or services** for later exploitation |
| Multiple Component | Incident encompassing **two or more** of the above types |

## Severity levels — examples _(Mod 16 p17)_

- **Low-level** (least severe, less priority): **loss of personal password; unsuccessful scans and probes; request to review security logs; presence of any computer virus or worms; failure to download antivirus signatures; suspected sharing of org accounts; minor breaches of acceptable usage policy**.
- **Medium-level** (more serious than low): **in-active external/internal unauthorized access; violation of special access to a computer or computing facility; unauthorized storing and processing data; localized worm/virus outbreak; virus/worms of comparatively larger intensity; breach of acceptable usage policy**.
- **High-level** (highest priority, handle **immediately**): **Denial-of-Service attacks; suspected computer break-in; virus/worms of highest intensity, e.g. Trojan or back door; changes to system hardware, firmware, or software without authentication; destruction of property exceeding $100,000; personal theft exceeding $100,000 and illegal electronic fund transfer or download/sale**.

## Severity levels — determinants _(Mod 16 p19)_

- Determined by: **impact of the incident** (extent of damage/impact); **criticality of the service** (dependency of other services on affected service); **confidentiality of the information** (sensitivity of info in affected service); **probability of spread** (rate other systems/services are affected).
- Determines **urgency of handling, level of expertise required, extent of response**.

| Level | Printed criteria |
|---|---|
| High | **High probability of affecting a large number of systems/services**; impact may lead to **financial crisis**; affects **major functioning and operations** |
| Medium | Could affect **at least half** of systems/services; affects a **non-critical** system/service; **disrupts normal working**; **tendency to propagate** |
| Low | Affects **only a few** systems/services; **low probability** of affecting functional/operational aspects; **will not propagate** |






