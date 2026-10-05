---
type: note
module: "15"
lo: "02"
tags: [process, tool, mod/15]
topic: "filtering Event Viewer logs, the three log-entry types, audit policy"
exam_weight: unknown
status: done
unresolved:
  - "p32 prints 'Click 0K' for the OK button of the Filter Current Log dialog (digit zero); rendered here as OK."
  - "p34 prints the system-log example 'Start/stop of services' where the same list on p29 of this LO prints 'Starting and stopping of services'; both variants exist in the source and the p34 wording is used here."
  - "p33 (Figure 15.9) and p31/p32 (Figures 15.7, 15.8) are GUI captures of the Filter Current Log dialog and Event Viewer — only the prose steps are used, nothing is read out of the pictures."
  - "p35 lists the five audit-policy actions as Table 15.4 ('Actions to Enable Local (or Group) Policy for an Audit Policy') but the table itself is not printed in the slice — the five list items are reproduced."
  - "p32 the filter event-level options printed are Critical, Warning, Verbose, Error and Information — 'Critical' and 'Verbose' appear here although they are not among the five severity levels listed elsewhere in this module; not reconciled."
---

[[MOC-Module-15]]

# Filtering and Examining Event Log Entries (§15.LO#02e)

> **LO#02: Discuss log monitoring and analysis on Windows systems** _(Mod 15 p14)_
> Covers pp31–35.

## Preview Pane — the last two items _(Mod 15 p31)_

| Item | Definition as printed |
|---|---|
| **Task category** | **Primarily used in case of a security log** that **classifies an event based on the event source** |
| **Computer** | The **name assigned to the computer where the event occurred** |

## Filtering / Finding Events in Event Viewer _(Mod 15 p31)_

- The **Filter feature helps in targeting the information that may be required for investigation**
- Event Viewer lets you **save specific filters for future use** through the **Create Custom View** feature
- The filter feature **allows the removal of clutter** from the event log display and **limits the data displayed in a single log**
- **Each log can be independently configured with different filter properties**

### Steps to create a filter _(Mod 15 pp31–32)_

1. **Select the log** that needs to be filtered
2. Click on the **`Filter Current Log`** option available under the **Action pane**
3. The **`Filter Current Log` dialog box** will appear
4. **Specify a time period**, if the approximate time when the events occurred is known
5. **Event levels** can be specified from the available options — **Critical, Warning, Verbose, Error, and Information**. **If no option is specified, all event levels will be returned**
6. **Specific event IDs** can be mentioned in the defined format; **specific event sources** can be selected; similarly **specific keywords, users, or computers** can be searched
7. Click **OK** to close the `Filter Current log` dialog box
8. **After applying the filter**, the Event Viewer **will show the log with matching properties**

### Finding an event _(Mod 15 p33)_

1. Click on **Find** option available under the **Action pane**
2. **Type the information that needs to be found** and then click **Find Next**
3. Click **Close**, when search is complete

## Examining Event Log Entries _(Mod 15 p34)_

> "Event Viewer displays **three types of event log entries**."

### 1. System log entries

- Contains events logged by **Windows system components**
- Contains information about **system changes** such as **device driver installations**, etc.
- To view: open Event Viewer → select **System** log from the **Windows logs** section in the **console tree** → a list of system events appears in the details pane → select the specific event whose details need to be viewed

**Examples of system log records** _(Mod 15 p34)_:

1. Changes to the OS
2. Changes to the hardware configuration
3. Device driver installation
4. Service pack update/installation
5. Software and hardware installations
6. Start/stop of services
7. System shutdown/restart
8. Log-on failures
9. Alteration of machine information
10. Printing jobs

### 2. Application log entries

- Contains events logged by **applications or programs**
- To view: open Event Viewer → select **Application** log from the **Windows logs** section in the console tree → a list of application events appears in the details pane → select the specific event whose details need to be viewed

**Examples of application log records** _(Mod 15 p34)_:

1. Installation and removal of a particular software package
2. Confirmation/refutation of virus infection
3. Startup and shutdown of firewall
4. Detection of hacking attempts

### 3. Security log entries

> "The security log is the **mother of all logs in forensic terms**." · "Unfortunately, **security logging is turned off by default**." _(Mod 15 p35)_

To view: open Event Viewer → select **Security** log from the **Windows logs** section in the console tree → a list of security events appears in the details pane → select the specific event whose details need to be viewed

**Examples of security log records** _(Mod 15 p35)_:

1. **Log-ons**
2. **Log-offs**
3. **Attempted connections**
4. **Policy changes**

### Table 15.4 — actions to enable local (or group) policy for an audit policy _(Mod 15 p35)_

"To support later investigations, enabling **local (or group) policy for audit policy** is recommended, with some of the following actions **at the minimum**":

1. **Audit account log-on events**
2. **Audit account management**
3. **Audit log-on events**
4. **Audit policy change**
5. **Audit privilege use**

## Where to go next

- What each of these entry fields means → [[15-LO02c-Windows-Event-Log-Types-and-Entries]]
- The viewing procedure and the rationale → [[15-LO02d-Monitoring-and-Analyzing-Windows-Logs]]
- Scaling this to many hosts → [[15-LO08e-Log-Storage-and-Log-Normalization]]






