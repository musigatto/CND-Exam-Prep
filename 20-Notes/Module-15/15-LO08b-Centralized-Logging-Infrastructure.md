---
type: note
module: "15"
lo: "08"
tags: [concept, process, mod/15]
topic: "The three tiers of a centralized log management infrastructure"
exam_weight: unknown
status: done
unresolved:
  - "p119 the architecture figure prints the collection-server box as 'Cdkction Server' and the storage list as 'MY SQL'. Quoted as printed where the diagram labels are reproduced; the surrounding prose on p120 uses 'collection servers' and 'Oracle, MS SQL, etc.'"
  - "p119 the architecture figure interleaves the tier names with the pipeline stage labels (LOG COLLECTION, LOG NORMALIZATION, LOG CORRELATION, LOG TRANSPORT, LOG STORAGE). The figure's box-to-stage assignment is a layout artefact of the OCR and is not asserted here; the pipeline stage order is given on p121 instead."
  - "p120 the 'Clock daemon' and 'Security/authorization messages' facility names appear elsewhere in the module; they are not tier names. The three tier names on p119/p120 are only: log generator, log analysis and storage, log monitoring."
---

[[MOC-Module-15]]

# Centralized Logging Infrastructure (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp119–120.

Related: [[15-LO08a-Why-Centralized-Logging]] ·
[[15-LO08c-Log-Collection-and-Log-Transmission]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO08e-Log-Storage-and-Log-Normalization]] ·
[[15-LO08f-Log-Correlation-and-Log-Analysis]] ·
[[MOC-Module-04]].

## What a log management infrastructure is _(Mod 15 p119)_

> "A log management infrastructure is a **combination of hardware, software, networks, and media**
> that **generate, transport, store, analyze, and report log data**."

- "**More than one log management infrastructures can exist in an organization.**"
- "**Log management architecture generally consists of three different tiers.**"

That "generally" is the only hedge the page offers — the three tiers are the norm, not a rule.

## The three tiers _(Mod 15 p119–120)_

| Tier | Printed name | One line |
|---|---|---|
| 1 | **Log generation / generator** | the host that produces the log messages |
| 2 | **Log analysis and storage** | one or more log servers that collect the log data; also called **collection servers** or **aggregators** |
| 3 | **Log monitoring** | consoles that monitor and review the log data and the outputs of log analysis; produce reports |

### Tier 1 — Log generation / generator _(Mod 15 p120)_

> "This tier consists of **the host that produces the log messages**. Some hosts use **logging client
> applications or services** to transfer their logs to log servers, while others prefer to do the
> same through other means. In some cases, the generator of the data may be a **router, switch or a
> firewall, application, database**, etc."

p119's figure names the generator sources as: **Firewall · Database · Endpoint · File server · Email
Management Server · Routers · Switches · IPS/IDS**.

### Tier 2 — Log analysis and storage _(Mod 15 p120)_

> "This tier consists of **one or more log servers that collect log data from the hosts**. The log
> data can be sent either **in real-time or in batches based on the schedule** to the log server. The
> log servers that are able to collect log data are also called **collection servers or
> aggregators**. They use **different protocols to collect the logs such as syslog, SNMP**, etc. Log
> messages can be stored **either in collection servers or on separate database servers**."

Real-time vs batched — that is the scheduling decision the tier-2 host makes.

### Tier 3 — Log monitoring _(Mod 15 p120)_

> "The third tier consists of **consoles** that monitor and review the log data as well as the
> **outputs of log analysis**. These consoles are used to **produce reports**. They may also **manage
> log servers and clients**. One can also **limit console user privileges to required functions and
> data sources**."

The last sentence is the access-control point: console privileges can be scoped down to the
functions and data sources a user actually needs.

## The architecture figure _(Mod 15 p119)_

Labels printed in the figure, as a list (the figure is a diagram; only its printed labels are
reproduced):

| Figure block | Labels printed |
|---|---|
| **Log Generator** | Firewall · Database · Endpoint · File server · Email Management Server · Routers · Switches · IPS/IDS |
| **Log Analysis and Storage** | `Cdkction Server` · `Storage Server` |
| **Pipeline stages** | `LOG COLLECTION` · `LOG NORMALIZATION` · `LOG CORRELATION` · `LOG TRANSPORT` |
| **LOG TRANSPORT** | Syslog · SOAP over HTTP · SNMP · FTP or SCP |
| **LOG STORAGE** | Oracle · MS SQL · `MY SQL` · PostgreSQL |
| **Log Monitoring** | (monitoring tier) |

Three names to carry away from the transport row: **syslog**, **SOAP over HTTP**, **SNMP**, plus
**FTP or SCP** as file transfer. The pipeline stage order is given properly on p121 — see
[[15-LO08c-Log-Collection-and-Log-Transmission]].

## Tier-2 configuration variants _(Mod 15 p120)_

> "**The second tier, that is, log analysis and storage, can differ in complexity and structure.**"

**Simplest:** "a **log server is managing all log analysis and storage functions**."

Three complex configurations, as printed:

1. "**Numerous log servers where each one performing a specific operation** such as log collection,
   log analysis, long-term storage, etc."
2. "**Numerous log servers and each one is analyzing and storing logs for a few log generators**"
3. "**Two levels of log servers**, where the **first level of distributed log servers transfer logs
   to second-level centralized log servers**"

Configuration 3 is the one that reappears later as the **relay** concept in syslog — see
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]].






