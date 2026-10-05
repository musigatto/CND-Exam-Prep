---
type: note
module: "15"
lo: "05"
tags: [tool, command, concept, mod/15]
topic: "Cisco ASA firewall logs"
exam_weight: unknown
status: done
unresolved:
  - "p76/p77 the Cisco Firewall Log Format sample line is damaged in both printings: 'May 06 201B asa 1: ASA -5 - 11008 . User •enabie_i5' executed the •configure term' ceand I.' (p76) and 'May 06 2018 21:27:27 asa 1: * ASA -5 - 11008 : User 'enable 15' executed the 'configure tem' comand o' (p77). The cleaner p77 printing is quoted; neither is corrected."
  - "p79 Table 15.10 prints 10 mnemonics (106015 106016 106017 106018 106020 106021 106022 106023 106100 710003) but only 9 descriptions; the last description is aligned with 106100 and 710003 carries no description on the page. The list is NOT truncated - all ten IDs are legible in the source."
  - "p78/p79 Table 15.10 prints identifiers with a letter l in place of a capital I and with spaces around underscores: 'acl_lD', 'source_lP', 'dest_lP', 'IP _ address', 'interface name', 'est-allowed', 'access source_lP/source_port'. These are kept exactly as printed and are NOT repaired."
  - "p76/p77 the level column prints 'Emergencies (O)' with the letter O, while the surrounding prose prints the range as '0—7'. Both printed forms are kept."
  - "p80 the bullet prints 'shov logging'; 'show logging' is the form printed cleanly on p82 and p83 of the same module. Rendered here as 'show logging'."
  - "p80/p83 the grep example on p80 is unreadable beyond fragments ('Oct 24 2018 08:54:48: src dst inside by access-group \"OUTSIDE\" [OxS–63b8Ã…k, –XÃ¶)'). Reproduced as printed and not completed; the p83 example carries the same message with far less damage."
  - "p80 the figure lists 5 source ports (46855, 46856, 46857, 46863, 46867) while the p83 prose for the same example names only 3 (46857, 46863, 46867). Both are reported as printed; the page does not reconcile them."
---

[[MOC-Module-15]]

# Cisco ASA Firewall Logs (§15.05)

> **LO#05: Discuss log monitoring and analysis on firewalls** _(Mod 15 p59)_
> Covers pp76–83.

Related: the four firewall log sources as a set —
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] · [[15-LO05b-Windows-Defender-Firewall-Logs]] ·
[[15-LO05c-Mac-OS-X-Firewall-Logs]] · [[15-LO05d-Linux-iptables-Logs]] ·
[[15-LO05f-Check-Point-Firewall-Logs]].
Console: [[15-LO06a-Cisco-Router-Log-Messages-and-Severity]] ·
[[15-LO06b-Monitoring-and-Analyzing-Router-Logs]].
Transport: [[15-LO08a-Why-Centralized-Logging]] · [[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]].

## What the ASA provides _(Mod 15 p76)_

> "Cisco ASA provides advanced **application-aware firewall services** with **identity-based access
> control** and **denial of service (DOS) attack protection**."

- "Firewall support multiple levels of logging; it helps to address this issue by **addressing the
  most critical events first**."

## Cisco Firewall Log Format — the four fields _(Mod 15 p76)_

Printed sample line (Figure on p76), as printed — see `unresolved`:

```text
May 06 201B asa 1: ASA -5 - 11008 . User •enabie_i5' executed the •configure term' ceand I.
```

| # | Field | Printed definition |
|---|---|---|
| 1 | **Timestamp** | "The date and time from the firewall clock; the default is **no time stamp**" |
| 2 | **Device ID** | "Firewall's host name, an interface IP address, or an arbitrary text string; the default is **no device-id**" |
| 3 | **Message ID** | "Begins with **`%ASA`, `%PIX`, or `%FWSM`**, followed by **severity level** and **six-digit message number**" |
| 4 | **Message Text** | "Description of the event or condition that generated the message" |

## Cisco ASA logging levels _(Mod 15 p76–p77)_

> "Cisco ASA firewall supports multiple levels of logging, which helps to address the issue at hand by
> **prioritizing the most critical events first**. These levels of logging are typically labeled **0—7**."

**Cumulative, not exclusive** _(p76)_: "The logging severity level set for a specific output will not
only take logs from that configured severity level but also from **all the levels above it**. For
example, if severity level 7—debugging messages has been configured for the console, then level 7 will
not only log all debugging messages but also **emergencies, alerts, critical errors, warnings,
notifications, and informational** messages."

### Short form (p76)

| Levels of Logging | Description |
|---|---|
| Emergencies (O) | System unusable messages |
| Alerts (1) | Immediate action required messages |
| Critical (2) | Critical condition messages |
| Errors (3) | Error condition messages |
| Warnings (4) | Warning condition messages |
| Notifications (5) | Normal but significant messages |
| Informational (6) | Informational messages |
| Debugging (7) | Debugging messages |

### The instruction that matters on the exam _(Mod 15 p77)_

> "Therefore, **always configure the critical severity level** for the log messages because setting a
> higher logging severity level (e.g., **7**) would generate a large amount of log messages, which would
> **disturb CPU and memory usage** on the Cisco ASA firewall."

### Table 15.9: Different Levels of Logging _(Mod 15 p77)_

| Levels of logging | Description |
|---|---|
| Emergencies (O) | System unusable messages |
| Alerts (1) | Messages requiring immediate action; for example, **failover, power supply, basic RIP, address verification**, etc. |
| Critical (2) | Critical condition messages; for example, **denied packets/connections after basic checks, URL filter server problems**, etc. |
| Errors (3) | Error condition messages; for example, **authentication/authorization failures, CPU and memory resource problems, tunnel problems, routing and NTP problems**, etc. |
| Warnings (4) | Warning condition messages; for example, **fragmentation issues, invalid addresses, auto-update errors, CSPF errors**, etc. |
| Notifications (5) | Normal but significant messages; for example, **commands executed by users, configuration events, user and session activity**, etc. |
| Informational (6) | Informational messages; for example, **log, ACL authentication/authorization events, firewall startup, fixup activity**, etc. |
| Debugging (7) | Debugging messages; for example, **debug messages, TCP/UDP request handling**, etc. |

## Cisco Firewall Log Format — two formats _(Mod 15 p77–p78)_

> "Cisco ASA firewall supports **two types of format** for storing log messages: **default** and **EMBLEM**."

### Default log format _(Mod 15 p77–p78)_

"This type of log format comprises the following types of fields."

Figure 15.27: Cisco Firewall Log Format _(p77)_, as printed:

```text
May 06 2018 21:27:27 asa 1: * ASA -5 - 11008 : User 'enable 15' executed the 'configure tem' comand o
```

| Field | Printed definition |
|---|---|
| **Time stamp** _(p77)_ | "It represents the time and date when a log message is generated. It helps in **real-time debugging and management**, so **always add timestamps** parameter to log messages. By default, **no timestamps** are present in the format." |
| **Device ID** _(p78)_ | "It represents firewall's **hostname**, an **interface IP address**, or an **arbitrary text string**. It helps in determining the firewall that produces the log messages. This becomes important when there are **multiple firewalls**. By default, **no device ID** is present in the format." |
| **Message ID** _(p78)_ | "It starts with **`%ASA`, `%PIX`, or `%FWSM`** and is followed by **severity level** and the **six-digit message number**." |
| **Message text/description** _(p78)_ | "It mentions the **event or condition** due to which the log message is generated." |

### EMBLEM log format _(Mod 15 p78)_

> "This type of format is mainly used for **CiscoWorks Resource Manager Essentials syslog analyzer**.
> This format is **similar to Cisco IOS Software syslog format** and used by **UDP syslog servers only**."

## Cisco ASA System Log Messages _(Mod 15 pp78–79)_

> "The following are a few examples of Cisco ASA System log messages:"

**Table 15.10: Examples of Cisco ASA System Log Messages** — columns `Mnemonic` · `Severity` ·
`Description`. Reproduced exactly as printed, including `acl_lD`, `source_lP`, `dest_lP` and
`IP _ address` (see `unresolved`). Mnemonic `4000 nn` is annotated on the page: *"nn" indicates multiple
messages currently 400000-400050*.

### Printed on p78

| Mnemonic | Severity | Description |
|---|---|---|
| `4000 nn` ("nn" indicates multiple messages currently 400000-400050) | 4 | IPS:number string from IP _ address to interface interface name IP address on |
| `106001` | 2 | Inbound TCP connection denied from IP _ address/port to IP _ address/port flags tcp_flags on interface interface _ name |
| `106002` | 2 | Protocol connection denied by outbound list acl_lD src inside address dest outside address |
| `106006` | 2 | Deny inbound UDP from outside_address/outside_port to inside_address/inside_port on interface interface _ name |
| `106007` | 2 | Deny inbound UDP from outside_address/outside_port to inside_address/inside_port due to DNS {Response I Query} |
| `106010` | 3 | Deny inbound protocol src interface_name:dest_address/dest_port dst |
| `106012` | 3 | Deny IP from IP _ address to IP_address, IP options hex |
| `106013` | 3 | Dropping echo request from IP_address to PAT address IP address |
| `106014` | 3 | Deny inbound icmp src interface _ name: IP address dst interface_name: IP _ address (type dec, code dec) |

### Printed on p79

| Mnemonic | Severity | Description |
|---|---|---|
| `106015` | 6 | Deny TCP (no connection) from IP _ address/port to IP _ address/port flags tcp_flags on interface interface_name |
| `106016` | 2 | Deny IP spoof from (IP_address) to IP_address on interface interface name |
| `106017` | 2 | Deny IP due to Land Attack from IP _ address to IP _ address |
| `106018` | 2 | ICMP packet type ICMP_type denied by outbound list acl_lD src inside address dest outside address |
| `106020` | 2 | Deny IP teardrop fragment (size = number, offset = number) from IP address to IP address |
| `106021` | 1 | Deny protocol reverse path check from source_address to dest address on interface interface name |
| `106022` | 1 | Deny protocol connection spoof from source _ address to dest address on interface interface name |
| `106023` | 4 | Deny protocol [interface_name:source_address/source_port] src dst interface_name:dest_address/dest_port [type {string}, code {code}] by access_group acl_lD |
| `106100` | 4 | access-list acl_lD {permitted I denied I est-allowed} protocol interface_name/source_address(source_port) -> interface_name/dest_address(dest_port) hit-cnt number ({first hit I number-second interval}) {TCPI UDP} denied by ACL from access source_lP/source_port to interface_name:dest_lP/service |
| `710003` | 3 | *(no description printed on the page)* |

## Monitoring and analyzing Cisco ASA firewall logs _(Mod 15 p80)_

- "The `show logging` command generates valuable logs that are analyzed to know about the **present
  condition (enabled or disabled)** of the device."
- "It helps in investigating the state of **syslog error, console logging, event logging, monitor
  logging**, etc."
- "Use `show logging` command with the required (**Deny, Outside, Suspicious**, etc.) keywords to find
  the required firewall log messages."
- "**`grep` command, followed by a regular expression, yields optimum results.**"

### Figure: `show logging` output on the ASA _(Mod 15 p82)_

The page prints this figure twice — on p80 as a figure and again as the worked example on p82. The
p82 printing is the cleaner of the two and is given here; the p80 printing differs only in OCR damage
(`Moni tor logging`, `Device I D`, `logg Ing`).

```text
Firewall# show logging
Syslog logging: enabled
Facility: 20
Timestamp logging: disabled
Standby logging: disabled
Debug—trace logging: disabled
Console logging: disabled
Monitor logging: enabled
Buffer logging: level informational,
Trap logging: enabled
Permit—hostdown logging: disabled
History logging: disabled
Device ID: disabled
Mail logging: enabled
ASDM logging: disabled
2 messages logged
```

Reading of that output _(p82)_: "logging is enabled globally, timestamps logging is disabled, and
console logging is also disabled, **may be it would be on production devices**. Information regarding
the total number of logged messages for each configured destination can also be known in similar
manner."

### Example: viewing a log entry of a specified severity by using the `grep` command _(Mod 15 p80)_

Figure caption: "Firewall logging level **Access Denied**".

```text
Firewall# show logging I gr ASA—4
Oct 24 2018 08:54:48: src dst inside by access—group "OUTSIDE" [OxS–63b8Ã…k, –XÃ¶)
Oct 24 2018 src dst inside by access—group "OUTSIDE" [Ox5063b82f, OXO)
Oct 24 2018 08:54:48: Depx.;tcp src dst inside by access—group "OUTSIDE" [Ox5063b82f , xm
```

Figure callouts on p80:

- "Source Address"
- "Destination Address"
- "Source ports (**46855, 46856, 46857, 46863, and 46867**); destination ports (**0, 256, 389, and 443**)"
- "The connection from the machine with the IP address **192.168.208.63** is denied access to **192.168.150.77**"

### What to look for in ASA logs _(Mod 15 p80–p81)_

"Analyzing log files in Cisco ASA reveals various details that are useful for **investigating an
incident**. Cisco ASA firewall generates a **large amount** of logging information, **only a part of
which has importance** and should be analyzed. Before analyzing the firewall logs, the important
information needs to be determined first."

The page's list of important information _(p81)_:

1. Connections accepted by firewall rules
2. Connections rejected by firewall rules
3. User activity
4. Bandwidth usage
5. Address translation audit trail
6. IDS activity
7. Protocol usage
8. Cut-through proxy activity
9. Denied rule rates

## Cisco ASA Command Line Interface _(Mod 15 p81–p82)_

> "Cisco ASA **Command Line Interface (CLI) is the console** where all the available commands are
> executed to know the details of the Cisco ASA log. It includes **command modes**, and some commands
> can be entered only in specific modes."

- "To enter commands that display **confidential information**, a password needs to be entered apart
  from being in a more privileged mode."
- "To enter commands that display **configuration change information**, the user should be in
  **configuration mode**."
- "To enter all lower commands, higher modes need to accessible; for example, a privileged EXEC command
  will enter in **global configuration mode**."
- Prompt prefixes: in **system configuration mode** or **single context mode** the prompt starts with
  the hostname — `hostname:`; "If the user is already inside a **context**, then the prompt will start
  in the following manner:" — `hostname/context`.

> "Cisco ASA CLI supports **four types of access modes**: **user EXEC mode, privileged EXEC mode, global
> configuration mode, and command-specific configuration mode**. Different modes have different prompt
> screens."

### Access modes and prompt screens

| Mode | What it does (printed) | How you get there | Prompt (as printed) |
|---|---|---|---|
| **User EXEC mode** _(p81)_ | "In this mode, **basic adaptive security appliance settings** can be viewed." | — | `hostname>` · `hostname / context>` |
| **Privileged EXEC mode** _(p81)_ | "In this mode, **current settings up to the user privilege level** can be viewed. The user can run **any user EXEC mode command** in privileged EXEC mode, and can also **switch to privileged EXEC mode in user EXEC mode**." | "enter **`enable`** command in user EXEC mode, where a **password** needs to be provided" | `hostname#` · `hostname/context#` |
| **Global configuration mode** _(p82)_ | "This mode **enables changes in the adaptive security appliance configuration**. This mode contains **all** users EXEC, privileged EXEC, and global configuration commands." | "from privileged EXEC mode by entering **`configure terminal`** command" | `hostname (config) #` · `hostname/ context (config) #` |
| **Command-specific configuration mode** _(p82)_ | "This mode includes commands from user EXEC mode, privileged EXEC mode, global configuration mode, and command-specific configuration mode." | — | `hostname (config—if) #` · `hostname/ context (config—if) #` |

### Viewing ASA firewall logging _(Mod 15 p82)_

> "The `show logging` command is used to view Cisco ASA firewall logs. … It also displays the syslog
> message that **begins with `%ASA` followed by the logging level, the message ID, and a brief
> description** of the log message."

The output is the block printed above; p80 prints the same figure as `Firewall* show logging`.

## Filtering `show` command output _(Mod 15 p83)_

> "The `show logging` command can be used with various keywords such as **`include`, `exclude`,
> `begin`, `grep`**, etc. to find the required firewall log messages."

| Keyword | Printed behaviour |
|---|---|
| `include` | "The included keywords **display information that matches the regular expression**" |
| `grep` (without `-v`) | "has the **same action**" |
| `exclude` | "**excludes information** that matches the regular expression" |
| `grep` with `-v` | "has the **same action**" |
| `begin` | "displays the information **beginning the line** that matched the regular expression" |

"Among the various keywords, **`grep` command followed by a regular expression will yield optimum
results**. `grep` command can also be used to **fetch log messages of a specific severity**."

```text
Firewall# show logging I grep ASA—4
Oct 24 2018 08:54:48: %ASA-4-106023: Deny tcp 208. 63/46857 outside: 192 .168 . 168.150.77/443 by access—group dst inside: 192. OXO]
Oct 24 2018 08:54:48: %ASA-4-106023: Deny tcp 208.63/46863 outside: 192 .168 . dst inside: 192 .168.150.77/256 by access—group OXO]
Oct 24 2018 %ASA-4-106023: Deny tcp 208.63/46867 outside: 192 .168 . dst inside: 192 .168.150.77/389 by access—group OXO]
src "OUTSIDE" src "OUTSIDE" src "OUTSIDE" [Ox5063b82f , [Ox5063b82f , [Ox5063b82f ,
```

> "The above example shows information regarding ASA with **severity level 4** where **source ports are
> 46857, 46863, and 46867** and **destination ports are 256, 389, and 443**. It also shows that the IP
> address **192.168.208.63 was denied access to 192.168.150.77**."







