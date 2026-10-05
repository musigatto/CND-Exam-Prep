---
type: note
module: "15"
lo: "06"
tags: [concept, protocol, tool, mod/15]
topic: "Cisco router log messages and severity"
exam_weight: unknown
status: done
unresolved:
  - "p90 Table 15.11 prints 10 mnemonics (IPACCESLOGDP, IPACCESLOGNP, IPACCESLOGP, IPACCESLOGRL, IPACCESLOGRP, IPACCESLOGS, TOOMANY, IPACCESLOGP, IPACCESLOGDP, IPACCESLOGNP) against 10 descriptions; the pairings are sequential and unambiguous, but the page duplicates IPACCESLOGP, IPACCESLOGDP and IPACCESLOGNP as rows 8-10. Reproduced as printed."
  - "p90/p91 the %SEC-4-TOOMANY description is damaged in the phrase between 'access' and 'log messages' / 'log buffers': p90 prints 'access 1st log messages' and 'no access ISt log buffers', p91 reprints it as 'access first log messages' and 'no access first log buffers'. The real word is not readable and is NOT reconstructed; the p91 reading is quoted."
  - "p90 the format line prints as 'seq no: timestamp: : description' with a doubled colon; reproduced as printed."
  - "p90 the seq no definition prints as 'This field represents stamps log messages with a sequence number'; quoted as printed."
  - "p90 'service timestamps log [datetime I log]' — the pipe separator is printed as the letter I; kept as printed."
  - "p90/p91 the mnemonic strings print with a digit 1 in place of a capital I in the body text ('lPACCESLOGDP', '%SEC-6-lPACCESLOGP'). The Table 15.11 spellings with capital I are used and both forms are reported."
  - "p91 Table 15.12 prints the level column value for Emergencies as the letter 'o'; the surrounding prose prints 'O to 7'. Both printed forms are kept."
  - "p91/p92 Table 15.12 prints the UNIX syslog names with a space ('LOG EMERG', 'LOG ALERT', ...); the underscores are not supplied."
---

[[MOC-Module-15]]

# Cisco Router Log Messages and Severity (§15.06)

> **LO#06: Discuss log monitoring and analysis on routers** _(Mod 15 p59)_
> Covers pp89–92.

"The objective of this section is to explain how to monitor and analyze router logs. Specifically, it
demonstrates how to monitor and analyze **Cisco router logs**." _(Mod 15 p89)_

Related: [[15-LO06b-Monitoring-and-Analyzing-Router-Logs]] ·
[[15-LO06c-Router-Logging-Configuration-and-Sample-Log]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]].
Same syslog severity ladder on a firewall: [[15-LO05e-Cisco-ASA-Firewall-Logs]].

## Two things router logs do *not* have _(Mod 15 p90)_

> "Router log messages **do not contain numerical identifiers** that assist in identifying the messages."

> "They include a **maximum of 80 characters** and a **percent sign (%)**, followed by an **optional
> sequence number or timestamp information** (if configured)."

## Router log message format _(Mod 15 p90)_

```text
seq no: timestamp: : description
```

| Field | Printed definition | Shown only if |
|---|---|---|
| `seq no` | "This field represents stamps log messages with a **sequence number**." | "the **`service sequence-numbers`** global configuration command is configured" |
| `timestamp` | "This field represents the **date and time** of the message on which it is generated. The date and time is in the **`mm/dd hh:mm:ss`**, **`hh:mm:ss` (short uptime)**, or **`d h` (long uptime)** format." | "the **`service timestamps log [datetime I log]`** global configuration command is configured" |
| `facility` | "This field represents the **facility**. It may be a **hardware device, a protocol, or a module**. It **determines the source and the reason** why the message is generated." | — |
| `severity` | "This field represents the **severity level** of the message from **O to 7**." | — |
| `MNEMONIC` | "It is a **text string that describes the message uniquely**." | — |
| `description` | "This field represents **detailed information** regarding the event generated." | — |

## Table 15.11: Examples of Cisco Router Log Mnemonics _(Mod 15 pp90–91)_

Printed as "Router Log Messages that are Most Useful When Analyzing Security-Related Incidents".
Reproduced exactly, including the printed duplication of rows 8–10 (see `unresolved`).

| Mnemonic | Severity | Description |
|---|---|---|
| `%SEC-6-IPACCESLOGDP` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGNP` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGP` | 6 | "A packet matching the log criteria for the given access list has been detected (**TCP OR UDP**)" |
| `%SEC-6-IPACCESLOGRL` | 6 | "**Some packet-matching logs were missed** because the access first log messages were **rate limited**, or no access first log **buffers** were available" |
| `%SEC-6-IPACCESLOGRP` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGS` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-4-TOOMANY` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGP` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGDP` | 6 | "A packet matching the log criteria for the given access list has been detected" |
| `%SEC-6-IPACCESLOGNP` | 6 | "A packet matching the log criteria for the given access list has been detected" |

Reading the structure: `%SEC` = facility, the digit = severity, the trailing string = mnemonic. Note
the anomaly the page prints — `%SEC-4-TOOMANY` carries severity **6** in the Severity column although
its mnemonic reads `4`. Reproduced as printed.

## Table 15.12: Severity levels of Cisco Router Logs _(Mod 15 pp91–92)_

> "Log messages in Cisco routers are categorized into **eight severity levels ranging from O to 7**.
> Each severity level is given a **number** and its corresponding **name** and **UNIX syslog
> definitions**. **The lower severity number represents a higher severity and vice-versa.**"

The table is split across pp91–92; columns `Level` · `Level name` · `Syslog definition` · `Description`.

| Level | Level name | Syslog definition | Description |
|---|---|---|---|
| `o` | Emergencies | `LOG EMERG` | System unusable |
| `1` | Alerts | `LOG ALERT` | Immediate action needed |
| `2` | Critical | `LOG CRIT` | Critical conditions |
| `3` | Errors | `LOG ERR` | Error conditions |
| `4` | Warnings | `LOG WARNING` | Warning conditions |
| `5` | Notifications | `LOG NOTICE` | Normal but significant |
| `6` | Informational | `LOG INFO` | Informational messages |
| `7` | Debugging | `LOG DEBUG` | Debugging messages |

The page prints **Notifications** (plural) and **Debugging** — not `Notice` and `Debug`. The syslog
definitions printed are `LOG NOTICE` and `LOG DEBUG`; keep the two spellings apart.

### What each band actually carries _(Mod 15 p92)_

- "**Messages between warning and emergency levels are designated as error messages** that represent
  **software and hardware malfunctions**."
- "**Interface up or down transition messages, system restart messages**, and other informational
  messages are shown as **notifications**."
- "**Information messages represent reload requests, low-process stack messages**, etc."
- "**Debug-level messages represent outputs provided by the debug commands**."






