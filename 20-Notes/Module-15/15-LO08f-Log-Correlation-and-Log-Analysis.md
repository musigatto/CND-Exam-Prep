---
type: note
module: "15"
lo: "08"
tags: [process, concept, bestpractice, port, mod/15]
topic: "Step 5 log correlation (micro/macro, field/rule) and Step 6 log analysis (manual vs automated) plus log-analysis best practices"
exam_weight: unknown
status: done
unresolved:
  - "p140 the page lists SIX inputs for macro-level correlation (rule, vulnerability, profile (fingerprint), anti-port, watch list, geographic location) but only THREE of them get a prose description on p141 - vulnerability, profile (fingerprint) and anti-port. Watch list correlation and geographic location correlation are named with no description anywhere in pp140–141. Nothing is supplied for them."
  - "p143 the section heading and the running prose say 'automated log analysis' while the slide heading is 'Automated Log Analysis' and the slide body says 'In automatic log analysis, all the phases in log analysis are executed sequentially with minimal human interaction'. Both the 'automated' and the 'automatic' wording are as printed and neither is declared correct."
  - "p143 the slide says manual analysis is 'based on experience and knowledge of the EXAMINER' while the prose says 'based on the experience and knowledge of the NETWORK DEFENDER'. Both printed forms are kept."
  - "p144 the slide prints only five best practices; the running prose list prints twelve. The five slide items are a subset of the twelve and are not reprinted separately here. 'Below are some of the best practices' is the page's own hedge, so the twelve are not treated as a closed list."
  - "p140 the phrase 'the correlation of logs is very critical and complicated process' prints without an article; quoted as printed."
---

[[MOC-Module-15]]

# Log Correlation and Log Analysis (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp140–144.

Related: [[15-LO08e-Log-Storage-and-Log-Normalization]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]] ·
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]] ·
[[15-LO07e-Apache-Access-Log-Fields-and-Monitoring]] ·
[[MOC-Module-14]].

## Step 5 — Log Correlation _(Mod 15 p140)_

> "**Log correlation is the process of matching a series of normalized log data to determine a set of
> related events based on a certain set of rules.**"

- "It uses **rule-based correlation, statistical or algorithmic correlation**, and other methods to
  **relate different events to each other**."
- "**When an incident occurs, these correlated logs are analyzed, and the cause for the incident is
  identified.**"
- Input is **normalized** data — correlation sits directly downstream of Step 4.

### Why it is "a very critical and complicated process" _(Mod 15 p140)_

Four reasons, as printed:

1. "**Most logs are written in human-understandable, plain language, while others are scripted in
   cryptic languages with only esoteric system codes.**"
2. "**Some systems have their siloed lenses.** They look at their logs through an **inefficient and
   incomplete filter**." — "a **network IDS looks only for packets and streams**; similarly, an
   **application only looks for sessions, users, and requests**."
3. "**Logs are static; they will not contain all the context of ongoing events.** Therefore, proper
   log analysis is required to understand the **full context of an event**."
4. "**Comparison of the logs of an event from one system with the logs of the same event of another
   system of the same version may not give the same information.**"

### Two types of correlation _(Mod 15 pp140–141)_

| | **Micro-level correlation** | **Macro-level correlation** |
|---|---|---|
| Also known as | "**atomic correlation**" | "**fusion correlation**" |
| Scope | "correlates **fields within a single event or set of events**" | "**pulls in different sources of information** … **to validate and gain intelligence on the event stream**" |
| Precondition | "performed **only when raw event data is normalized**" | — |
| Sub-types | "further divided into **field correlation** and **rule correlation**" | see the six inputs below |

#### Micro-level, 1 — field correlation _(Mod 15 pp140–141)_

> "It is a **mechanism through which tasks of interest can be found within the normalized event
> data**."

**The printed example:** "For example, to search for the events **targeting the web server, focus on
events that have port 80 or 443 as the destination port**."

- Two ways in: **by field value** (the destination-port example) and "**Field correlation is also
  possible through event types**."

#### Micro-level, 2 — rule correlation _(Mod 15 p141)_

> "In rule correlation, **custom rules are used based on stateful behavior, counting, timeout, rule
> reuse, language, the priority of an activity, action to take on the event**, etc."

Seven printed bases: **stateful behavior · counting · timeout · rule reuse · language · priority of
an activity · action to take on the event.**

#### Macro-level — the six inputs _(Mod 15 pp140–141)_

| Input | What the page prints |
|---|---|
| **Rule correlation** | "The rule correlation in **macro-correlation is similar to** rule correlation in **micro-correlation**. **The only difference is that rule correlation in micro-level correlation can be converted to a rule in macro-level correlation.**" |
| **Vulnerability correlation** | "used to **scan system vulnerabilities**, which helps the management in **increasing the security level of their systems**." |
| **Profile (fingerprint) correlation** | "utilizes **banner snatching, OS fingerprints, remote port scans, and vulnerability scans** to collect information. It provides **deep insights about the attackers** and helps in **remediation post an attack**." |
| **Anti-port correlation** | "utilizes **open port information to identify attacks in the slow or low category**." |
| **Watch list correlation** | *named in the list only — no description printed* |
| **Geographic location correlation** | *named in the list only — no description printed* |

---

## Step 6 — Log Analysis _(Mod 15 p142)_

> "**Log analysis is the process of identifying the patterns and anomalies in the correlated log
> data that signifies the activity of any intrusion attempt or policy violation.**"

- Input is **correlated** data — analysis sits directly downstream of Step 5.
- "**An intelligent decision is made based on patterns and anomalies found in log data to identify and
  confirm the incident.**"
- "Logs are meant for **analysis and analytics**. Once the log data is **stored, normalized, and
  correlated in a central location**, it needs to be analyzed."
- It "also **identifies relevant events from the huge cluster of data and ignores the irrelevant
  ones**."
- It "supports in the identification of **failed processes, protocol failures, or network outages**" and
  "helps in **identifying trends** and **upgrading search functionalities and performance**".
- **Labeling:** "a huge amount of log data is analyzed and labeling. Through labeling, it becomes
  easy for network defenders to **monitor different event logs in a distributed and detailed manner
  in one place**."

### What log analysis can facilitate _(Mod 15 p142)_

Seven items, as printed:

1. "Checking whether **internal policies, regulations, and audits** are being followed or not"
2. "**Identifying and resolving security incidents** occurred"
3. "**Troubleshooting systems, computers, or networks**"
4. "**Identifying user behavior**"
5. "Performing **security event forensics in incident investigation**"
6. "Identifying a **change in pattern of logs that may indicate an incident**"
7. "**Enhancing security awareness**"

### The two approaches — manual vs automated _(Mod 15 p143)_

> "The log analysis process is performed using **two approaches**. The first approach is a **manual
> log analysis** and the second one is **automated log analysis**."

| | **Manual log analysis** | **Automated log analysis** |
|---|---|---|
| Who/what | "a **person manually goes through the log data** that is collected, **monitors it**, and tries to **identify any suspicious incidents** happening in the network **without using any software tools**" | "**all the log analysis phases are executed sequentially with minimal human interaction**" |
| Basis | "**investigation and analysis of the retrieved logs based on the experience and knowledge** of the network defender" *(slide: "…knowledge of the examiner")* | — |
| What it does | — | "identifies the **patterns and anomalies in the correlated log data** that signifies the activity of **any intrusion attempt**" |
| Verdict | "**considered as complex as there are different log formats, and only experts can carry it out**" | "**overcomes the difficulties faced in manual log analysis**" … "**highly preferred as it is time- and cost-efficient**" |

**What the page says a manual analyst must bring** _(p143)_: "network defenders should have
**proper knowledge of the system**; they should **check whether every part of the system is
operating normally or not**; and they should **understand what is going to be changed most
recently**."

The trade in one line: **manual = expert-only, format-bound, slow; automated = sequential,
minimal human interaction, time- and cost-efficient.**

## Log analysis best practices _(Mod 15 p144)_

Twelve items, as printed:

1. "Log analysis system should be **synchronized with the NTP server** to avoid **timing differences
   between the systems**."
2. "Log analysis should always be considered as a **proactive security initiative rather than a
   reactive one** as it is **often performed after an incident has occurred**."
3. "**Automate the log analysis process** as it **takes less time and minimizes human
   interaction**."
4. "**Review and analyze the logs at regular intervals**."
5. "**Develop a baseline** to detect **unusual activities/events quickly** when logs are registered."
6. "**Set a strategy to log data.**"
7. "**Set an effective logging format** to detect and gain an understanding of the network from the
   logs."
8. "**Collect the logs at a centralized location, separated from the production environment.**"
9. "**Implement end-to-end logging** to gain a **more holistic view**."
10. "**Correlate data sources** to detect events that cause system malfunctions."
11. "**Use unique identifiers** for debugging, support, and analytics."
12. "**Always perform real-time monitoring**."

Count note: the running prose list prints **twelve** sentences under "Below are some of the best
practices"; the slide condenses it to **five** (items 1–5 above). "some of" is the page's own hedge, so
the twelve are not claimed to be exhaustive.

Item 1 pairs directly with the timestamp challenge on p150–151, and item 8 with
[[15-LO08a-Why-Centralized-Logging]] — see
[[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]].







