---
type: note
module: "15"
lo: "02"
tags: [process, tool, mod/15]
topic: "monitoring and analyzing Windows event logs in Event Viewer"
exam_weight: unknown
status: done
unresolved:
  - "p27 is entirely a GUI capture (Figure 15.5, 'Various Windows Event Types') — no body prose on the page, and nothing has been read out of the picture."
  - "p28/p30 print the same three viewing steps twice with slightly different wording; the fuller p30 wording is used and p28 is noted."
  - "p28 prints 'User responsible and who logged on to the computer at the instance Of the event' with the OCR capital O; rendered here as 'instance of the event'."
  - "p28 prints 'Task Category: Primarily used in case of security log'; p30/p31 print 'a security log that classifies an event based o on the event source' (broken line) — the p31 wording is not used here because p31 belongs to the next slice."
  - "p29 lists the audit-policy actions the page calls the minimum; the list itself is carried in the next slice, which covers p35 and Table 15.4."
---

[[MOC-Module-15]]

# Monitoring and Analyzing Windows Logs (§15.LO#02d)

> **LO#02: Discuss log monitoring and analysis on Windows systems** _(Mod 15 p14)_
> Covers pp27–30.

## Why these logs are monitored _(Mod 15 p29)_

Windows event logs:

- include critical information such as **log-on failures, log tampering, failed attempts to access files**
- **warn regarding upcoming system issues** and **protect the system from unexpected disasters**
- may also describe **an attempt made by a user to compromise the system** or an **unsanctioned configuration change**

> "Thus, these event logs need to be monitored and analyzed to **identify network vulnerabilities, security breaches, and threat intruders**."

- They enable the network defender to **protect the network against internal threats and vulnerabilities** _(Mod 15 p30)_
- **"The most common way to monitor and analyze Windows event logs is to use the Windows Event Viewer"** _(Mod 15 p30)_

## Viewing Events in Event Viewer _(Mod 15 p30)_

1. **Open Windows Event Viewer** by clicking the **Start icon** and then typing `Event Viewer` in the search box
2. Once Event Viewer opens, **click on the required log file from the console tree** — a list of events appears in the **details pane**
3. In the details pane, **clicking on any specific event** reveals its **description and header information** in the **Preview pane**

The same three steps are printed on p28 in this wording _(Mod 15 p28)_:

1. Open Event Viewer, **click the required log you want to view**
2. In the details pane, **click the event that you want to view**
3. **Description and header information is displayed in the Preview Pane**

### What the Preview Pane shows _(Mod 15 p30)_

| Item | Definition as printed |
|---|---|
| **Log name** | The **type of Windows log** |
| **Source** | The **cause responsible for the event**, raised by **either an individual, or a system, or a program** |
| **Event ID** | The **type of event that occurred** |
| **Level** | Event level type — **divided into five types: Error, Warning, Information, Success Audit, and Failure Audit** |
| **User** | User responsible and **who logged on to the computer at the instance of the event** |
| **Logged** | The **timestamp of the event** |

The p30 list continues on p31 with **Task category** and **Computer** → [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]

## Finding Events in a Log _(Mod 15 p28)_

- The **Filter** feature in Event Viewer **allows the removal of clutter from the event log display**
- **Each log can be independently configured with different filter properties**
- Use the **Filter** and **Find** features in Event Viewer, **under the Actions pane**
- **After applying the filter**, the Event Viewer **shows the log with matching properties**

The filter-creation steps and the log-entry categories → [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]

## The security log — the forensic core _(Mod 15 p29)_

> "The security log is the **mother of all logs in forensic terms**."

- **Log-ons, log-offs, attempted connections, and policy changes** are all reflected in the event contained therein
- "Unfortunately, **security logging is turned off by default**. It **needs to be enabled by the group or local policy** to be useful"
- To support later investigations, **enabling local (or group) policy for audit policy is recommended**, with some actions **at the minimum** — listed in Table 15.4 → [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]

## Where to go next

- What each log type records → [[15-LO02c-Windows-Event-Log-Types-and-Entries]]
- Filter dialog steps, the three entry types, security-log examples → [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]
- Windows Defender Firewall logs from the same Event Viewer → [[15-LO05b-Windows-Defender-Firewall-Logs]]
- Why the same discipline applies network-wide → [[15-LO08a-Why-Centralized-Logging]]






