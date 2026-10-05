---
type: note
module: "15"
lo: "04"
tags: [concept, tool, mod/15]
topic: "Mac OS logs and the Console app"
exam_weight: unknown
status: done
unresolved:
  - "p48 Figure 15.12 'Screenshot of Console App' and p49 Figure 15.13 'Screenshot of Mac Window' are GUI captures — treated as NON-EVIDENCE. Nothing was read from either image: not the 'Console (16,956 messages)' count, not the 'Errors and Faults' / 'All Messages' / 'Reports' toolbar labels as chrome, not the sidebar source names (system.log, /Library/Logs, /var/log, apache2), not the 'CIPortraitEffect*' filter values, not the '2018-06-22 14:...' timestamps. The stray picture tokens around Figure 15.12 ('consolel rop', 'console table', 'console.log') were NOT used. Only the running prose on p48–p49 was used."
  - "p48 the callout box prints 'Application malfunctioning /failure, etc.' (spaced slash, trailing 'etc.') while the p48 prose prints 'application malfunctioning/failure'. Both forms are kept as printed; the courseware itself prints both."
  - "p49 prose says 'a list of all Console messages is showed by default' — printed grammatical error, kept as printed."
---

[[MOC-Module-15]]

# Mac Logs and the Console App (§15.LO#04a)

> **LO#04: Discuss log monitoring and analysis on Mac systems** _(Mod 15 p47)_
> Covers pp47–49.

## What LO#04 covers _(Mod 15 p47)_

"The objective of this section is to explain monitoring and analysis of logs in Mac systems. It describes the various Mac logs, **their types, log files and their formats, and how to monitor and analyze them**."

→ types & files → [[15-LO04b-Mac-Types-of-Logs-and-Log-Files]] · format & procedures → [[15-LO04c-Mac-Log-Format-and-System-Logs]]

## What Mac logs are _(Mod 15 p48)_

| Property | As printed on p48 |
|---|---|
| Collection | "Mac OS provides **efficient application programming interfaces (APIs)** for collecting log messages **from all levels of the system**" |
| Storage location | "**a centralized location** either **in memory** or in a **data store on disk**" |
| Purpose | "Mac system logs help in **diagnosis and troubleshooting security issues** with installed applications and services" |
| Format | "stored in the form of **plain text**" |
| Viewer | "can be viewed in **Mac Console app**" |

Contrast: the Linux equivalent (daemon writes to `/var/log`, root-only) → [[MOC-Module-06]] · Windows counterpart → [[15-LO02a-Windows-Logs-and-Event-Viewer]] · Mac endpoint security → [[MOC-Module-07]]

## Activities Mac is configured to log _(Mod 15 p48)_

**"Mac OS is configured manually to log activities"** — the printed callout box:

- **Application malfunctioning /failure, etc.**
- **Installation, file creation/deletion**
- **user privileges escalation**
- **Troubleshooting events**
- **Failed login attempts**

The running prose on the same page spells the list out as "application malfunctioning/failure, **user privileges escalation**, **installation, file creation/deletion**, **troubleshooting events**, and **failed login attempts**".

## The Console app _(Mod 15 pp48–49)_

**Two launch paths, both printed on p48:**

1. `Finder` → `Applications` → `Utilities` → `Console`
2. **Spotlight** — "Press **Command + Space** and then type "**Console**" and press **Enter**"

> "The Console app will appear, which is **similar to Windows Event Viewer**." _(Mod 15 p48)_

**Default view and filtering (p49 prose):**

- "In the current Mac window, **a list of all Console messages is showed by default**."
- "To check error messages, click on "**Errors and Faults**" tab in the toolbar."
- "A particular error message can also be searched by using the **search box**."

→ Console is the Mac equivalent of [[15-LO02a-Windows-Logs-and-Event-Viewer]]; the same log corpus is shipped off-box by [[15-LO08a-Why-Centralized-Logging]]





