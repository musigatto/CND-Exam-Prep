---
type: note
module: "15"
lo: "01"
tags: [concept, protocol, tool, mod/15]
topic: "log definition, four logging types, log sources, need of logs"
exam_weight: unknown
status: done
unresolved:
  - "p5 figure caption prints 'Log — Switch Log'; the em dash is treated as OCR noise and the caption is rendered 'switch log'."
  - "p5 'Clint n.' is OCR garbage from inside the example-of-log figure — not reproduced."
  - "p5 the four logging types are given only as a prose sentence; no table is printed."
  - "p6 prints 'client—server model' with an em dash; rendered here as 'client-server model'."
  - "p6 prints 'System Logging Protocol (syslog)' as the expansion of syslog — kept exactly as printed, not corrected."
  - "p6 sentence printed as 'The, the log sources need to be configured based on the features ...' — the duplicated word is rendered once."
  - "p7 'Logs can help in the following tasks' prints only 'System monitoring' before the page break; the remaining tasks continue on p8 in [[15-LO01b-Troubleshooting-and-Logging-Requirements]]."
---

[[MOC-Module-15]]

# Log Types, Sources and the Need for Logs (§15.LO#01a)

> **LO#01: Understand logging concepts** _(Mod 15 p4)_
> Covers pp4–7.

## Definition

- **Log** — "a collection of information/data on events generated in the form of **audit trail** by the various components of information system such as network, applications, operating system (OS), service, etc." _(Mod 15 p5)_
- **Logging** — "the process of recording and storing logs of the events that occur in the network." An important source that helps detect **flaws or problems as well as network attacks, frauds, and inappropriate uses of data** _(Mod 15 p5)_
- A log "can provide an indication that something may have gone wrong" — it helps defenders analyze and detect issues _(Mod 15 p5)_
- **Not every log reports faults.** Transaction logs, firewall logs and IPS/IDS logs **simply store records of specific events** (page example: deletion of a record from the database) _(Mod 15 p5)_
- **Correlation creates the meaning.** A single log is low-value; when logs from multiple devices are collected, correlated and analyzed by **SIEM** systems "something meaningful is generated" _(Mod 15 p5)_
  - Page example: combine the **transaction log** (a record entry by a user) with the **firewall log** (network activity from an IP address registered by the same user) → **verify the authenticity of that user** _(Mod 15 p5)_

## Four types of logging _(Mod 15 p5)_

> "Generally, there are four types of logging."

| Type | Focus |
|---|---|
| **Security logging** | Identifying and **responding** to security-related activity — threats, viruses, malware, data loss. Records user login, unauthorized access to resources, etc. |
| **Operational logging** | **System-processing activities**. Informs the defender of failures and potentially actionable conditions; facilitates service provisioning and financial decisions |
| **Compliance logging** | **A part of security logging** — regulations are developed to enhance the security of systems and data |
| **Application debug logging** | For **application/system developers, not system administrators**. Can be disabled and enabled in a production system based on circumstantial requirements |

## Log sources _(Mod 15 p6)_

**A log source refers to a data source that builds an event log.**

- Almost every device or application has logging capability; **every security system generates logs in some form or another**
- Printed examples of log sources: **Windows logs, client and file server logs, router logs, firewall logs, and database logs**

### Two transfer mechanisms

| Mechanism | How records move | Printed detail |
|---|---|---|
| **Push-based** | the system/application either **saves records on the local disk** or **sends them over the network** | if sent over the network, a **log collector** is needed. The two main push-based protocols: **System Logging Protocol (syslog)** and **Simple Network Management Protocol (SNMP)** → [[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] |
| **Pull-based** | a system or application **pulls** the log records from a log source | works on the **client-server model**; the device usually stores log data in a **proprietary format**. Page example: **Check Point provides OPSEC C library** to pull logs from a Check Point device |

### Configuring log sources

- Log source configuration "is not an easy task" — first identify the **hosts and host components** that will participate in the log management infrastructure, based on standard rules and policies
- **A single log file includes information from multiple sources** — e.g. an OS log holds data not only from the OS itself but from various other security programs
- Once the source is determined, specify the **types of events** to be logged by each source **and the features of data** to be logged for each event
- **Granularity varies.** Some log sources provide granular configuration options; others provide none. In sources with **no granularity, logging is either enabled or disabled, without any control over the kind of data that can be logged**
- Required sources must collect important information **in required formats and locations** and store it **for a long period of time**

## Need of Logs _(Mod 15 p7)_

Printed list, verbatim:

- To **identify security incidents**
- To **monitor policy violations**
- To **identify fraudulent activity**
- To **identify operational and long-term problems**
- To **establish baselines**
- To **ensure compliance with laws, rules, and regulations**

Why the page says this matters:

- Logs are needed to understand the events occurring on the network — purposes range "from performance to threat identification"
- A good source of **forensic information**; helps understand **"what happened"** after a security incident
- Proper analysis yields **actionable information** → detecting/monitoring potential security breaches, internal misuse of information, operational and long-term issues
- Validates whether the end-user followed all documented protocols → detects fraudulent activity and policy violations
- Also: internal investigations, security auditing and forensic analysis, determination of operational trends, implementation of baselines
- Provides information about **what, how, and why** a particular security intrusion occurred → aids recovery and mitigation
- Ensures compliance with laws, rules and regulations for **storing and analyzing** log data; acts as an **audit trail**

### Tasks logs help with

- **System monitoring** _(Mod 15 p7)_ — detailed information about the transactions occurring across the environment; facilitates constant system monitoring and helps determine **errors, anomalies, and suspicious system activities**; helps respond as early as possible
- The task list **continues on p8** → [[15-LO01b-Troubleshooting-and-Logging-Requirements]]

Next: format and approaches → [[15-LO01c-Typical-Log-Format-and-Logging-Approaches]] · why centralize → [[15-LO08a-Why-Centralized-Logging]]




