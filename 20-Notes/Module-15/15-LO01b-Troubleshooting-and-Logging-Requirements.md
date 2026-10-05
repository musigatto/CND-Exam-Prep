---
type: note
module: "15"
lo: "01"
tags: [concept, process, bestpractice, mod/15]
topic: "troubleshooting, forensics and incident-response uses of logs; logging requirements"
exam_weight: unknown
status: done
unresolved:
  - "p8 the page prints 'Syslog need to be utilized for this purpose' — ungrammatical but kept as printed."
  - "p8 'correlating the activities usi...' is cut off by the page; the sentence ends with 'to correlate the activities using log files.'"
  - "p9 the 'You should be able to' callout prints 'prevent unauthorized access and manipulation to the logs' while the 'Requirements for Logging' list on the same page prints 'Prevent unauthorized access and manipulation of the logs' — both are kept as printed."
  - "p9 the 'You should be able to' callout is a 5-item subset of the 9-item 'Requirements for Logging' list; the extra four items are listed only in the prose list."
---

[[MOC-Module-15]]

# Troubleshooting and Logging Requirements (§15.LO#01b)

> **LO#01: Understand logging concepts** _(Mod 15 p4)_
> Covers pp8–9.

p8 completes the "Logs can help in the following tasks" list opened on p7 → [[15-LO01a-Log-Types-Sources-and-the-Need-for-Logs]].

## Troubleshooting _(Mod 15 p8)_

- The information and messages available in log files **can** be used to troubleshoot a problem
- **But ordinary log files are not enough to troubleshoot network problems** — "**Syslog need to be utilized** for this purpose"
- Syslog records events and **arranges them into log files** → beneficial in monitoring OS activities and troubleshooting issues

## Forensics and analysis _(Mod 15 p8)_

- Logs are a **permanent source of record that cannot be altered through the normal course of actions**
- Stored in **chronological sequence** → they describe **not only what happened but also when and how it happened**
- Sent to another host or a **central log collector**, logs act as a **backup source of evidence** — especially useful if the original copy is suspected to have been tampered
- If the information on the original source is found suspicious, **the separate copy is considered for authentication**
- Logs **support the findings of other evidences** and improve their authenticity when their findings corroborate
- The complete scenario of an event is usually **not dependent on one source of information** but on multiple sources — files and their timestamps, network data, logs, etc.
- Logs may also assist in **rejecting other evidences** suspected to have been tampered by an attacker

## Incident response _(Mod 15 p8)_

- Incident response requires **proper correlation of log events across all devices and assets**
- That correlation determines the **extent and impact** of a network compromise and the **steps required for remediation**
- Caveat: the various security devices in a network **may not have the required correlation capabilities** to give a complete picture of the attacker's activities during an attack
- **Common solution: correlate the activities using log files**

## Logging Requirements _(Mod 15 p9)_

"Before setting the requirements for a logging solution, details such as what to log, where to store the logs, methods for logging, tools required for logging, log format, etc. should be known."

### Before enabling logging capability, you should know _(Mod 15 p9)_

1. **What to log**
2. **Where to store the logs**
3. **Methods for logging**
4. **Tools required for logging**
5. **Log format**

### "You should be able to" _(Mod 15 p9)_

- Perform regular tuning and review of logs
- Synchronize timestamps of all the sources to perform correlation
- Prevent unauthorized access and manipulation to the logs
- Correlate the data sources to identify any malicious activity
- Analyze the security-based events that are to be stored in the event logs

### Requirements for Logging _(Mod 15 p9)_

> "For effective security events logging, you should able to do the following:"

1. **Determine applications and systems** (including those that are outsourced or are on the cloud) on which event logging is enabled
2. **Configure the information system** for providing correct security incidents
3. **Perform regular tuning and review of logs** to minimize the number of **false positives**
4. **Store events in event logs**
5. **Normalize and aggregate** security-related events
6. **Correlate the data sources** to identify any malicious activity
7. **Synchronize timestamps of all the sources** to perform correlation
8. **Prevent unauthorized access and manipulation** of the logs
9. **Analyze security-based events** that are to be stored in the event logs

Requirements feed directly into the log field list and the local/centralized choice → [[15-LO01c-Typical-Log-Format-and-Logging-Approaches]]





