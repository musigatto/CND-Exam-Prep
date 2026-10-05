---
type: note
module: "15"
lo: "08"
tags: [concept, process, protocol, mod/15]
topic: "The 7-step centralized process; Step 1 log collection and Step 2 log transmission"
exam_weight: unknown
status: done
unresolved:
  - "p121-p122 the page defines all seven phases but only p123 and p124 give the detailed walkthroughs of Step 1 and Step 2. Steps 3-7 definitions here are the p122 one-line definitions only; their detail is in 15-LO08e and 15-LO08f."
  - "p124 the figure list of transport mechanisms prints 'HIT p' between 'Encrypted Syslog' and 'HTTPS'; the surrounding prose heading is 'HTTP/HTTPS'. The five bullet glyphs in the figure also do not match the eight printed items - the figure's list is reproduced as printed, not reordered to match the glyph count."
  - "p124 the prose has no separate detail section for SNMP or for FTP/SCP, although both are printed in the mechanism list. Only syslog UDP, syslog TCP, encrypted syslog, HTTP/HTTPS and SOAP over HTTP are described."
  - "p123 the figure is a labelled log-source diagram whose labels OCR as 'Anti-VirLE', 'push/P-uu', 'Anti rus', 'os', 'F-Wpervisor', 'sysk*' and 'SNMP (RFC 5343, VI, v2c, v3)'. Only the clean, readable labels are reproduced below; the damaged tokens are listed verbatim and not repaired."
  - "p123 the figure prints 'sysk* (RFC 5424)' and 'SNMP (RFC 5343, VI, v2c, v3)'. The RFC numbers are quoted as printed; 'VI' is not a standard SNMP version token and is not corrected."
  - "p126 (outside this slice) refers to the standard syslog port without printing a number. No port number is available for syslog UDP or syslog TCP from pp121–124."
---

[[MOC-Module-15]]

# Log Collection and Log Transmission (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp121–124.

Related: [[15-LO08a-Why-Centralized-Logging]] ·
[[15-LO08b-Centralized-Logging-Infrastructure]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO08e-Log-Storage-and-Log-Normalization]] ·
[[15-LO08f-Log-Correlation-and-Log-Analysis]] ·
[[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]] ·
[[MOC-Module-14]].

## The centralized process, all seven steps _(Mod 15 p121–122)_

"In centralized logging, logging, monitoring, and analysis of logs are performed through a **series
of steps**." The figure (15.32) prints the order:

| # | Step | Definition (p121–122) |
|---|---|---|
| 1 | **Log Collection** | "the process of **collecting log messages from the various sources to the database in a central location**" _(p121)_ |
| 2 | **Log Transmission** | "To store the logs in a centralized location, they are **transmitted through different transport mechanisms** such as **syslog UDP, syslog TCP, encrypted syslog**, etc." _(p122)_ |
| 3 | **Log Storage** | "All the log files collected from various devices are stored in **central repository/databases**. Stored databases can be **retrieved in structured way** when needed." _(p122)_ |
| 4 | **Normalization** | "the process of **accepting logs from heterogeneous sources with different formats and converting them into a common format**" _(p122)_ |
| 5 | **Log Correlation** | "the process of **matching a series of normalized log data to determine a set of related events based on a certain set of rules**" _(p122)_ |
| 6 | **Log Analysis** | "the process of **identifying the patterns and anomalies in the correlated log data** that signifies any intrusion attempt or policy violation activity" _(p122)_ |
| 7 | **Alerting and Reporting** | "An alerting system **generates alerts and sends a report to the user** if any suspicious event is observed in the logs or **calculated matrices**" _(p122)_ |

Note on the order: **normalize before correlate** — correlation is defined over *normalized* data.
And **analyse after correlate** — analysis is defined over *correlated* data. Steps 4 → 5 → 6 are a
strict chain.

p122 also notes: "**A detailed explanation of each phase of this process is described in the upcoming
slides.**"

---

## Step 1 — Log Collection _(Mod 15 p123)_

> "**Log collection is the process of collecting log messages from the various sources to the
> database in a central location.**"

### Who produces log messages _(Mod 15 p123)_

- "**Various security systems** such as **antimalware tools, proxies, firewall, authentication
  servers, routers, switches**, etc. generate log messages."
- "**Even OS and web applications** generate a wide range of log messages."

What those messages cover, as printed: "**user IDs, system activities, timestamps, successful or
unsuccessful access attempts, configuration changes, network address and protocols, file access
activities**, etc."

### Who performs it _(Mod 15 p123)_

- "The process of collecting these log messages from various log sources and **collating them to a
  central database** is known as **log collection**. This operation is performed by a **log
  collector**."
- "**The transmission between the log collector and a central log server is encrypted to avoid
  eavesdropping.**"

### Log-source figure labels _(Mod 15 p123)_

Printed labels of the "Step 1: Log Collection" figure, readable ones: **Switch · Firewall · NIDS ·
Portal · HIDS · WAF · Anti-virus · Anti-virus · HIDS · Mobile · LOG COLLECTION** — plus the
transport callouts `sysk* (RFC 5424)` and `SNMP (RFC 5343, VI, v2c, v3)`.

Damaged tokens, quoted as printed and **not** repaired: `Anti-VirLÃ‰` · `push/P•uu` · `Anti rus` ·
`os` · `F-Wpervisor` · `sysk*`.

### Advantages of central log collection _(Mod 15 p123)_

| Advantage | Printed definition |
|---|---|
| **Redundancy** | "Log messages are kept in **more than one location**." |
| **Store and forward** | "If the log collector **loses connection** to the central log server while forwarding the log messages to it, it will **store those log messages and forward them when the connection is reestablished**. This prevents possible data loss." |
| **Authentication** | "The log collector **not only verifies the sender as a trusted source** but also **the server** to whom it is sending log messages." |
| **Privacy** | "The transmission between the log collector and log server is kept private through **data encryption**." |

Four advantages, and note the two-way nature of **Authentication** — both ends are verified.

---

## Step 2 — Log Transmission _(Mod 15 p124)_

> "**A process of moving log messages to a central location is known as log transport.** An
> **efficient and reliable mechanism** should be used to transmit log messages."

### Transport mechanisms _(Mod 15 p124)_

Printed list, as the figure prints it:

- Syslog UDP
- syslog TCP
- Encrypted Syslog
- `HIT p`
- HTTPS
- SOAP over HTTP
- SNMP
- **File transfer protocols such as FTP or SCP**

### What an efficient transport must preserve _(Mod 15 p124)_

- "Maintain **integrity, availability, and confidentiality** of log data"
- "Maintain **log format and meaning**"
- "Represent **all the events correctly with perfect timings and event sequence**"

The third is the one people drop: **correct sequence**, not just correct content.

### Mechanism detail _(Mod 15 p124)_

| Mechanism | Printed behaviour |
|---|---|
| **Syslog UDP** | "Syslog **User Datagram Protocol** is **faster** at transferring log data compared to TCP. This is because it **does not wait for the server to confirm** whether information is received or not. Despite this weakness, this is **one of the most popular log transport mechanisms**." |
| **Syslog TCP** | "Syslog **Transmission Control Protocol** first **establishes a connection** to the server and then transmits the data to it. Once the data is transmitted, it **waits for the server to confirm receipt of information through an acknowledgment message**. It also has **flow control capabilities**." |
| **Encrypted syslog** | "**Syslog is a clear-text protocol.** Encrypted syslog was introduced to make sure the transmitted log data was encrypted; this makes transport of logs **over TCP/UDP secure**." |
| **HTTP/HTTPS** | "can be used in transferring log data between devices and can also be used to **send and receive files** based on TCP/IP protocols." |
| **SOAP over HTTP** | "The **Simple Object Access Protocol** is another messaging protocol, and it is also **used for transmitting syslog**. This process is done over an **HTTP payload as HTTP is an application protocol**." |

The UDP/TCP trade-off in one line: **UDP is faster and unacknowledged; TCP connects first, waits for
an acknowledgment, and has flow control**. Encrypted syslog exists because **syslog is clear-text**.







