---
type: note
module: "15"
lo: "02"
tags: [concept, tool, mod/15]
topic: "Windows event logs, Event Viewer, registry-based log configuration"
exam_weight: unknown
status: done
unresolved:
  - "p15 the registry key is only legible inside the capture as 'I-IKEY LOCAL l..og>' / 'I-IKEY LOCAL Log>' — the full key path is not readable in the body text and has not been reconstructed."
  - "p15 prints the registry value name as 'DisplayNamelD'; the l/I ambiguity in the OCR is unresolved. It is written here as DisplayNameID, taken from the printed string, not from outside knowledge."
---

[[MOC-Module-15]]

# Windows Logs and Event Viewer (§15.LO#02a)

> **LO#02: Discuss log monitoring and analysis on Windows systems** _(Mod 15 p14)_
> Covers pp14–15.

## LO#02 scope _(Mod 15 p14)_

> "The objective of this section is to explain monitoring and analysis of logs in Windows systems. It describes Windows event logs, their types, and how to monitor and analyze them."

## What the section covers _(Mod 15 p15)_

- The **Windows OS tracks various events, activities, and functions through logs**
- **Windows event logs, consisting of a header and a series of event records**, provide a **standard, centralized way** for applications (and the OS) to record important **software and hardware events**
- **Windows Event log audit configurations** (i.e. **log retention, log size**, etc.) are **recorded based on the registry key**

## Windows Logs _(Mod 15 p15)_

- The **Windows event logging service** *collects events from multiple sources* and keeps them in a **single location known as Windows event log**
- These logs act as the **primary source of evidence** for all important **actions/activities** on a Windows system
- The log holds **system, security, and application notifications** that are **monitored and analyzed by network defenders to detect issues in the system**
- It provides a **standard, centralized way** for applications (and the OS) to record important software and hardware events
- It uses a **structured data format** that simplifies the process of **searching and filtering** for a particular type of log
- The files are viewed through **Event Viewer**, which the page calls "**the programming interface that facilitates analysis of these logs**"

### What one log entry carries _(Mod 15 p15)_

| Part of the entry | Per the p15 prose |
|---|---|
| **Event time** | when the event occurred |
| **Event source** | the source that caused the event |
| **Event type** | **Information · Warning · Error · Success Audit · Failure Audit** |
| **Event ID** | the ID for the event type |

### Registry-based configuration _(Mod 15 p15)_

Audit configurations — **log retention, log size**, etc. — are **recorded based on a registry key** under `HKEY_LOCAL_MACHINE`:

- That key **comprises various subkeys, which are known as logs**
- **Each log includes registry values** such as `CustomSD`, `DisplayNameFile`, `DisplayNameID`, `File`, `MaxSize`, etc., **which can be configured as per requirement**

## Where to go next

- On-disk file format of those logs → [[15-LO02b-Windows-Event-Log-File-Format]]
- Log types and the fields of a log entry → [[15-LO02c-Windows-Event-Log-Types-and-Entries]]
- Filtering and examining entries → [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]
- Generic log-format conventions → [[15-LO01c-Typical-Log-Format-and-Logging-Approaches]]
- Windows as an endpoint → [[MOC-Module-05]]





