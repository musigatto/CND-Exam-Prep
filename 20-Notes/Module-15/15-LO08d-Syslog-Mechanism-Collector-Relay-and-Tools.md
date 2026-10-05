---
type: note
module: "15"
lo: "08"
tags: [protocol, concept, tool, port, mod/15]
topic: "Syslog, its components, roles, layers, message format, PRI, severity, and tools"
exam_weight: unknown
status: done
unresolved:
  - "p126 the page says the syslog listener uses 'UDP port, which is the standard syslog port' and that 'a TCP port can be used for this purpose' - but NO port NUMBER is printed anywhere in pp125–134. No number is supplied here."
  - "p131 Table 15.21 'Values of Severity' prints the eight level ABBREVIATIONS (Emerg, Alert, Crit, Error, Warn, Notice, Info, Debug) and their descriptions, but the numeric level column printed beside them was not recoverable from the module OCR. The 0-7 numbering is NOT asserted here. The spelled-out names are given only where they appear inside a printed description."
  - "p130-p131 Table 15.20 'Values of Facilities' prints codes 1-12 on p130 and 13, 14, 15, 16-23 on p131, but thirteen facility names are printed before the p131 continuation. Code 0 is not present, so the name-to-code alignment is off by one and cannot be fixed from the page. Both rows are reproduced as printed, in printed order, with no reassignment."
  - "p130 the example syslog message is a callout diagram. The OCR returns the callout labels and the message tokens interleaved, and the delimiters did not survive: no '<', '>' brackets and no version digit are legible. The token stream is reproduced verbatim in OCR reading order and NOT reconstructed."
  - "p130 example message tokens print as 'ID47' and 'BOM'su zoot'; p125's version of the same example prints as '1047' and \"BCX'su root'\". Neither is repaired to the other. 'zoot', 'Eor' (for 'for'), 'ionvick' and 'BCX' are quoted as printed."
  - "p125 Figure 15.37 prints the format string as 'TIMESTAMP HOSTNAME TAG MESSAGEID STRUCTURED-DATA MSG' while p129's Figure 15.37 prints 'TIMESTAMP HOSTNAME TAG MESSAGED STRUCTURED-DATA MSG'. 'MESSAGED' is quoted as printed and not corrected to 'MESSAGEID'."
  - "p133 figure URL prints 'https.//www.whatsupgold.com' with a bullet/dot where the colon belongs. Quoted as printed. The p134 prose prints the same host cleanly as 'Source: www.whatsupgold.com'."
  - "p133 figure URL prints 'https://www.sysbg-ng.com' ('sysbg' for 'syslog'). Quoted as printed. The p134 prose prints 'Source: www.syslog-ng.com'."
  - "p133 figure URL prints 'https://www.fastvue.c0' with a digit zero for the 'o' of 'co'. Quoted as printed. The p134 prose prints 'Source: www.fastvue.co'."
  - "p133 the page contradicts itself on two tool sources: the figure gives Kiwi Syslog Server as 'https://www.kiwisyslog.com' but the prose says 'Source: www.solarwinds.com'; the figure gives SNMPSoft Sys-log Watcher as 'https://www.netadmintools.com' but the prose says 'Source: www.ezfive.com'. Both printed forms are recorded; neither is declared correct."
  - "p133 the figure labels the tool 'Syslog-NG' and the prose calls it 'syslog-ng'; the figure labels it 'SNMPSoft Sys-log Watcher' and the prose 'SNMPSoft Syslog Watcher'. Both printed spellings kept."
  - "p133 NxLog is the only tool in the figure with no legible URL; the p134 prose gives 'Source: https://nxlog.co'."
  - "p125 figure labels OCR as 'Devices Svsbg Men.s Ent to Syslog' and 'S.bq Server'; p126 labels include 'IPS Syslog Server' and 'IDS -J Other devices Router Firewall 1 Syslog Server Switch Firewall 2'. These diagram labels are not reproduced - p126 and p128 are figure-only pages."
---

[[MOC-Module-15]]

# Syslog Mechanism, Collector, Relay and Tools (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp125–134.

Related: [[15-LO08c-Log-Collection-and-Log-Transmission]] ·
[[15-LO08b-Centralized-Logging-Infrastructure]] ·
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] ·
[[15-LO05e-Cisco-ASA-Firewall-Logs]] ·
[[15-LO05f-Check-Point-Firewall-Logs]] ·
[[15-LO06b-Monitoring-and-Analyzing-Router-Logs]] ·
[[15-LO08e-Log-Storage-and-Log-Normalization]] ·
[[MOC-Module-04]].

## What syslog is _(Mod 15 p125)_

> "**Syslog is a data logging service** that enables network devices such as **routers, switches,
> firewalls, printers, web-servers**, etc. to **send and store logging of events and information on
> a logging server**."

> "**System Logging Protocol (syslog) is a standard for data logging service**; network devices use
> to **forward log messages to a server across an IP network**."

- "**Logging server is a dedicated server called syslog server** and **events send are called
  syslog messages**."
- "Syslog stores **consolidate logs from multiple devices into a Single location**."
- "A **syslog server** is a **central repository** that stores logs from various network devices. It
  consolidates logs from multiple devices (**switches, firewall, routers, and others**) into a
  single location."
- "**Events logged in IDS and IPS are also sent to the syslog server** using internet protocols such
  as **TCP, UDP, HTTP, HTTPS, SNMP**, etc."

A syslog server "**provides centralized log management**" and "**generates alerts when any suspicious
activity is generated or when prenotified events occur**" _(Mod 15 p126)_.

## Components of a syslog server _(Mod 15 p125–127)_

The page lists three components — **Syslog listener · Database · Management and filtering
software** — and then gives each its own description.

### 1. Syslog listener _(Mod 15 p126)_

> "A syslog listener **gathers the log messages that are sent by the devices over the network using
> UDP port**, which is the standard syslog port **but does not provide an acknowledgment message**
> when receiving the log messages. **Therefore, a TCP port can be used for this purpose.**"

> "Syslog also **listens to the data sent over different ports such as HTTP and HTTPS** as it works
> on a **layered architecture**."

**No port number is printed.** The trade-off is the reason: UDP gives no acknowledgment, so a TCP
port is offered as the alternative.

### 2. Database _(Mod 15 p126–127)_

> "Syslog database is **the place where all the log messages that are being sent to the syslog
> server are stored**. The information may include **system activities, unsuccessful attempted
> events, devices that are connected to the network**, etc. This information is **indexed and can
> be retrieved when necessary**."

### 3. Management and filtering software _(Mod 15 p127)_

> "Log messages contain a wide range of information, and **to extract important information from it
> will be a time-consuming task**. Therefore, the syslog server takes the help of **management and
> filtering software**."

- "This software **filters the messages** and **provides notification to network defender about
  detected errors**."
- Example: "it **filters and displays all critical log messages related to the firewall**."
- "It also uses **negative filter rules** to avoid notifications regarding certain types of entries."

The **negative filter** is the tool for silencing a known-noisy event class.

## Different roles in syslog _(Mod 15 p127)_

| Role | Printed definition |
|---|---|
| **Originator** | "The entity that **generates** the syslog message." May be a **router, switch, or a firewall**. The data generated "could be regarding the **activities in an OS, connection of external devices to the network, installation of third-party applications in a system**, etc." |
| **Relay** | "An entity that **receives the messages from the originator and forwards them** either to **syslog relay or syslog collector** in the network. **There may be multiple syslog relays in a network.**" |
| **Collector** | "The entity that **receives the information of the event in the server in a syslog format**." The format "may be of any kind and is **specified by the standard server**". |

**Collector = syslog server.** The page is explicit: "**The syslog collector is often referred to as
syslog server.**"

**Why a relay exists** _(p127)_: if a company has a branch office at another location and that
branch's log files are also to be stored at the centralized location, "it may not be done in one
direct step. In such a case, the log data is sent to a central machine **through syslog relay**."

Path: `Originator → Syslog Relay → Syslog Collector`. Same two-level shape as p120's "first level of
distributed log servers transfer logs to second-level centralized log servers".

## Different layers of syslog _(Mod 15 p128–129)_

> "According to the syslog standard, there are **three different layers**—**syslog transport layer,
> syslog application layer, and syslog content layer**."

| Layer | Printed role | Contents |
|---|---|---|
| **syslog content** | "includes the **actual information kept within** the log messages" | "those **devices that generate log messages** that are to be sent to the syslog server. It contains the **actual message** that is to be sent, including **audit record, events record**, etc." _(p128)_ |
| **syslog application** | "**interprets, routes, and stores** the log messages" | "manages **generation, interpretation, routing, and storage** of syslog messages. This layer consists of the **originator** (generates the messages), **collector** (collects the messages sent by the originator), and **relay** (collects from the originator and forwards to syslog collector or another syslog relay)." _(p129)_ |
| **syslog transport** | "**transmits the log data/messages over the network**" | "**transport sender** (sends the log messages to a specific transport protocol) and a **transport receiver** (receives the log messages from the specific transport protocol)." _(p129)_ |

**Framing** _(p129)_ — the transport layer technique: "In the transport layer, the **'framing'**
technique is used. In this technique, **assembling of all log messages at the source side and
dissembling of those log messages at the receiver side** is done. **Each message in this process is
described as a frame.**"

Content → application → transport. **The roles (originator/relay/collector) live in the application
layer**, not the transport layer.

## Syslog message format _(Mod 15 p129–132)_

> "The log events and information that are sent are called **syslog messages**. Syslog messages
> include important information that provides deep insights about **when, where, and why** a specific
> log message was generated."

### Two message-format standards _(Mod 15 p129)_

| Standard | Printed status |
|---|---|
| **RFC3164** | "an **old format introduced in 2001**. This was the **standard BSD format**." |
| **RFC5424** | "the **new standard format that is currently in use**; it was **introduced in 2009 to overcome the problems of RFC3164**." |

### The three components of RFC5424 _(Mod 15 p129)_

| Component | Printed definition |
|---|---|
| **Header** | "This field comprises subfields for **priority, version, timestamp, hostname, application, process ID, and message ID**." |
| **Structured data** | "It contains **data blocks in the `key=value` format**." |
| **Message** | "It **should be UTF-8 encoded** and it **contains a description of the event generated**." |

The printed format string, Figure 15.37 _(Mod 15 p125, p129)_:

```
TIMESTAMP HOSTNAME TAG MESSAGED STRUCTURED-DATA MSG
```

(p125 prints the same figure with `MESSAGEID` in the fourth slot: `TIMESTAMP HOSTNAME TAG MESSAGEID
STRUCTURED-DATA MSG`.)

### Example of a syslog message _(Mod 15 p130, Figure 15.38)_

Printed **callout labels**: `Tag` · `Structured-Data version` · `Syslog Timestamp` · `priority
Number` · `Host Name` · `Message ID`.

Printed **message tokens**, in the order the page's OCR yields them — the `<` `>` brackets, the
version digit and the seconds digits did not survive and are **not** reconstructed:

```
15   2018-10-11T22:14:   .003Z   mymachine.   example   .   com   su   ID47   -   BOM'su   zoot   failed   Eor   ionvick   on   /dev/pts/8
```

The p125 figure of the same example prints a second rendering of the tokens: `su` · `mymachine` ·
`t` · `1047` · `-` · `BCX'su` · `root'` · `failed for Ionvick on /dev/pts/8`.

## Calculation of the priority value _(Mod 15 p130)_

> "**Priority value, which is also known as PRI**, is used to represent the **facility and severity**
> of the message. **Facility provides information about the sender of the message**, and **severity
> represents the importance of the message**."

- "The priority value is **present at the beginning of the message** and is **enclosed in `<` and
  `>`**."
- "The priority value **exists between O and 191** and is calculated by the formula:"

```
Priority value = (facility value x 8) + severity value
```

- "**If the PRI value of an event is low, then the priority of that event is high.**"

The inverse convention is the one to watch: **low number = high priority**.

### Table 15.20 — Values of Facilities _(Mod 15 p130–131)_

Reproduced as printed, in printed order. **The p130 block prints thirteen names against twelve
codes; no name is reassigned to a code here.**

| Numerical code (p130) | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Facility (printed) | Kernel messages | User-level messages | Mail system | System daemons | Security/authorization messages | Messages generated by syslogd | Line printer subsystem | Network news subsystem | UNIX-to-UNIX copy (UUCP) subsystem | Clock daemon | Security/authorization messages | TP daemon | NTP subsystem |

| Numerical code (p131) | 13 | 14 | 15 | 16—23 |
|---|---|---|---|---|
| Facility (printed) | Log audit | Log alert | Clock daemon | Locally used facilities (`loca10`—`loca17`) |

Two names repeat in the printed list: **Security/authorization messages** and **Clock daemon**.

### Table 15.21 — Values of Severity _(Mod 15 p131)_

Reproduced exactly as printed. The numeric level column printed beside these abbreviations was not
recoverable from the module OCR, and the spelled-out level names are given **only** where the page
itself prints them inside a description.

| Level (as printed) | Description (as printed) |
|---|---|
| **Emerg** | Emergency system is unusable |
| **Alert** | Action must be taken immediately |
| **Crit** | Critical conditions |
| **Error** | Error conditions |
| **Warn** | Warning conditions |
| **Notice** | Normal but significant condition |
| **Info** | Informational |
| **Debug** | Debug-level messages |

### Header _(Mod 15 p131)_

> "According to the standard message format, the header must contain **7-bit ASCII character set in
> the 8-bit field**. It is the **metadata** of the event logs. It consists of **identifying
> information** of a syslog message such as a **timestamp, hostname, or an IP address**."

- "The header part of the syslog message consists of a **timestamp and the hostname or IP address**."
- "If the system in which the message is generated **does not contain a hostname**, then the message
  header will contain **IP address** in its part."
- "The timestamp in the header is a **combination of date and time at which the message was
  generated**. The format of the timestamp is **in the local time, in the `Mmm dd hh:mm:ss`
  format**."

### Message, and the three TAG fields _(Mod 15 p131–132)_

> "The **MSG** part contains a **TAG field** (which represents the **name of the program** that has
> generated the message) and a **CONTENT field** (which includes the **details of the message
> itself**). The TAG field of the message is further divided into **three fields**."

| Field | Printed definition |
|---|---|
| **APP-NAME** | "used to **identify the originator of the message**. If the system cannot provide the information, then **NIL value** is assigned to the message. No value is assigned if the information is not available for that device." |
| **PROCID** | "used to **identify the process name or process ID**. When a process is not available, then **PROCID is set to NIL value**." |
| **MSGID** | "used to **identify the type of message sent**." |

**PROCID and the discontinuity rule** _(p131–132)_:

> "**A change in PROCID indicates that there is a discontinuity in syslog reporting.** However, it is
> **not reliable for a restarted process** as such a process is assigned the previous process ID."

**MSGID values** _(p132)_:

- Messages **coming out from a UDP port** → MSGID **`UDPOUT`**
- Messages **going in** → MSGID **`UDPIN`**
- "**Messages with the same MSGID should reflect events of the same semantics.**"
- "**MSGID is a string**, and its main purpose is to **filter the messages that are passing over the
  relay and collector**."

## Syslog tools _(Mod 15 p133–134)_

"The following are few syslog server tools."

### Figure URLs vs prose `Source:` values _(Mod 15 p133–134)_

Both printed forms are recorded. **Two of the eight contradict each other between the figure and
the prose.**

| Tool (figure label, p133) | URL printed in figure (p133) | `Source:` printed in prose (p133–134) |
|---|---|---|
| Kiwi Syslog Server | `https://www.kiwisyslog.com` | `www.solarwinds.com` _(p133)_ |
| Splunk Light | `https://www.splunk.com` | `www.splunk.com` _(p133)_ |
| WhatsUp Gold | `https•.//www.whatsupgold.com` | `www.whatsupgold.com` _(p134)_ |
| Syslog-NG | `https://www.sysbg-ng.com` | `www.syslog-ng.com` _(p134)_ |
| SNMPSoft Sys-log Watcher | `https://www.netadmintools.com` | `www.ezfive.com` _(p133)_ |
| Visual Syslog Server | `https://www.github.com` | `www.github.com` _(p133)_ |
| Fastvue Syslog | `https://www.fastvue.c0` | `www.fastvue.co` _(p134)_ |
| NxLog | *(not legible in figure)* | `https://nxlog.co` _(p134)_ |

OCR damage, quoted as printed and not repaired: `https•.//` (bullet for the colon), `sysbg-ng`
(for `syslog-ng`), `fastvue.c0` (digit zero for `o`). **NxLog is the only tool whose prose source
carries an `https://` scheme.**

### What each tool does _(Mod 15 p133–134)_

**Kiwi Syslog Server** — "provides **centralized and simplified log message management** across
network devices and servers. It allows managing **syslog messages, SNMP traps, and Windows event
logs**."

**SNMPSoft Syslog Watcher** — "for Windows that **collects, parses, stores, analyzes, and explains
syslog messages** to professional network administrators and helps improve the **stability and
reliability of the network**."

**Splunk Light** — "automates **log search and analysis**, as well as **server and network
monitoring**. It **centrally collects and indexes all the log data** including **syslogs, event,
web, and IIS logs** regardless of format or location. It **builds dashboards** around security
compliance, clickstream data, and website transaction failures. Splunk Light also **maximizes
uptime** of network, operational, and e-commerce servers through **real-time alerts**."

**Visual Syslog Server** — "for Windows is useful when **setting up routers and systems based on
Unix/Linux**. It provides **live messages view**, switches to a new received message, **color
highlighting**, **message filtering**, **customizable notifications and actions**, etc."

**WhatsUp Gold Syslog Server** — "**collects and stores syslog messages**, thereby providing a
**reliable central repository for log data**."

**Fastvue Syslog** — "can **detect incoming syslog data** and **automatically log the messages to
organized text files**. It **automatically zips logs older than 30 days (configurable)** and moves
them to an archive folder, **reducing disk space requirements**. It provides **automatic `SHA256`
hash file for each log for validation**. It allows **forwarding syslog messages to other syslog
servers**."

**syslog-ng** — "**collects logs from any source, processes them in real time, and delivers them to
a wide variety of destinations**. It allows to **flexibly collect, parse, classify, rewrite, and
correlate** logs from across the infrastructure and **store or route them to log analysis tools**."

**NxLog** — "log collection technology is **compatible with most SIEM and log analytics products**,
and can handle data sources. It provides **Windows log collection capabilities, secured and reliable
collection and transfer, remote deployment of configuration changes and monitoring agents**, supports
**agent-less and agent-based log collection modes**, support for a **wide range of data formats and
protocols**, etc."







