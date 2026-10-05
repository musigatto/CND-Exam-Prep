---
type: note
module: "15"
lo: "06"
tags: [command, concept, tool, mod/15]
topic: "Monitoring and analyzing router logs"
exam_weight: unknown
status: done
unresolved:
  - "p93 the first walkthrough step prints 'shov logging'; 'show logging' is the form printed cleanly on p94 and p95 of the same module. Rendered here as 'show logging'."
  - "p93 the walkthrough step 'In case console logging is enabled, If enabled. this field States the level; otherwise, it displays disabled' is garbled in the source; quoted as printed."
  - "p93 the figure showing router log lines is unreadable beyond the sequence numbers ('002092:' through '002097:') and the mnemonic fragments ('SEC-6-1PACCESSLOGP'). Not reproduced. The same kind of records are reproduced cleanly on pp96–97 - see 15-LO06c-Router-Logging-Configuration-and-Sample-Log."
  - "p93 the figure caption prints 'Logging. to 192.180.2.238'; p94 prints the same address as '192.180.2.238'. Kept as printed - it is NOT corrected to a 192.168.x.x address."
  - "p94 the figure for the 'include' filter is a two-column capture whose columns are interleaved in the text layer ('Searching Logs for Source IP Address', 'Port Number', 'Number packets T ransferred', 'list zes'). Not reproduced; the same example is reprinted far more legibly on p96."
  - "p94/p95 Table 15.13 is captioned 'Number of Fields and its Description' although it lists five fields."
  - "p95 the show logging history capture prints 'O messages ignored, O dropped' and 'SYS-5—CONFIG I'; reproduced as printed (letter O for zero, letter l for a pipe)."
---

[[MOC-Module-15]]

# Monitoring and Analyzing Router Logs (§15.06)

> **LO#06: Discuss log monitoring and analysis on routers** _(Mod 15 p59)_
> Covers pp93–95.

Related: [[15-LO06a-Cisco-Router-Log-Messages-and-Severity]] ·
[[15-LO06c-Router-Logging-Configuration-and-Sample-Log]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO05e-Cisco-ASA-Firewall-Logs]].

## What `show logging` is for _(Mod 15 p93)_

Walkthrough steps, as printed:

1. "`show logging` helps in investigating the state of **syslog error, console logging, event logging,
   and host addresses**."
2. "It helps in finding **to what levels various outputs are set** and **where ultimately output is
   sent**."
3. "In case **syslog logging** is enabled, that implies **logs are saved to UNIX host/syslog server**."
4. "In case **console logging** is enabled, If enabled. this field States the level; otherwise, it
   displays disabled" — printed garbled.
5. "It shows a **minimum severity criteria that is required for a log to be monitored**."
6. "It gives information about **SNMP logging**, whether it is **enabled or not**, messages are logged
   and details about **retransmission interval** also."
7. "It gives **minimum severity criteria that is required for a log to send it to the syslog server**."

> "Use `show logging` command with **`include` filter** to search for specific keywords in the router
> logs." _(Mod 15 pp93–94)_

In the body _(p94)_: "The `show logging` command helps in investigating the state of syslog error,
console logging, event logging, and host addresses. It also shows **configuration parameters and
protocol activity of SNMP logging**. Further, it can display information regarding the **standard
system logging buffer** (only if **`logging buffered`** command is enabled). You can also **configure
the size of the syslog buffer** using the `logging buffered` command. This determines the **number of
system error and debugging messages to be stored in the system logging buffer**."

## Sample output _(Mod 15 p94)_

```text
Router# show logging
Syslog logging: enabled
Console logging: disabled
Monitor logging: level debugging, 266 messages logged
Trap logging: level informational, 266 messages logged
Logging to 192.180.2.238
SNMP logging: disabled, retransmission after 30 seconds
0 messages logged
```

## Table 15.13: Number of Fields and its Description _(Mod 15 p94–p95)_

Columns `Field` · `Description` — reproduced verbatim, five fields against five descriptions.

| Field | Description |
|---|---|
| **Syslog logging** | "In case syslog logging is enabled, it implies that **logs are saved to UNIX host/syslog server**." |
| **Console logging** | "In case console logging is enabled, this field **states the level**; otherwise, it **displays disabled**." |
| **Monitor logging** | "It shows **minimum severity criteria that are required for a log to be monitored**." |
| **Trap logging** | "It gives **minimum severity criteria that are required for a log to send it to the syslog server**." |
| **SNMP logging** | "It gives information about **SNMP logging**, whether it is **enabled or not**, whether messages are **logged**, and details about **retransmission interval** as well." |

Exam distinction to hold on to: **Monitor logging = minimum severity to be *monitored*; Trap logging =
minimum severity to be *sent to the syslog server*.**

## `show logging history` — the history table _(Mod 15 p95)_

> "The `show logging` command can **combine the keywords with search-specific filters** to identify
> relevant information. The **`history`** keyword can be used to fetch information regarding the
> **syslog history table** in the following manner:"

```text
Router# show logging history
Syslog History Table: 1 maximum table entry,
saving level notifications or higher
O messages ignored, O dropped, 15 table entries flushed,
SNMP notifications not enabled
entry number 16: SYS-5—CONFIG I Configured from console by console
timestamp: 1110
```

### Table 15.14: Types of Information and their Description — rows printed on p95

The table continues onto p96; the remaining rows are carried in
[[15-LO06c-Router-Logging-Configuration-and-Sample-Log]].

| Fields | Description |
|---|---|
| **Maximum table entry** | "It represents **how many messages can be stored in the history table**. This is configured by using the **`logging history size`** command." |
| **Saving level notifications or higher** | "It describes the **level up to which the messages can be stored** in the history table. This is configured by using **`logging history size`** command." |
| **Messages ignored** | "It describes **how many messages are not stored** in the history table." |






