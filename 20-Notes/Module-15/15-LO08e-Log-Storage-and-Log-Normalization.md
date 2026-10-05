---
type: note
module: "15"
lo: "08"
tags: [process, concept, mod/15]
topic: "Step 3 log storage (duration, volume, access) and Step 4 log normalization (CEE, regex, common fields)"
exam_weight: unknown
status: done
unresolved:
  - "p137/p138/p139 print the SAME firewall event stream three times and the OCR returns a different corrupted form of the address tokens each time: p137 'srcipz10.10.O.1 srcpo 10240 ... dstip-10.16.1.1', p138 'srcip=lo.lo.o.l ... dstip=10.16.1.I', p139 'srcip=10.O.O.1 ... dstip=IO.16.I.I'. All three are quoted as printed and NOT repaired. The clean values that the pages do print are the normalized-table figures: 10.0.0.1 / 10240 / 10.16.1.1 / 111."
  - "p138 the two parsing regexes in Figure 15.39 are truncated and unbalanced as printed: 'IP=\"dstip\\=(\\d{1,3}\\\\d{1,3})\\d{' and 'Source Port=\"srcport\\=(\\d{I,5})\"'. Quoted as printed; the class '{I,5}' is not corrected to a digit range."
  - "p139 Figure 15.40 (the 'bad event') prints the normalized column headers Event Name / Source IP / Source Port / Destination IP / Destination Port but the recovered values are only '10.0.0.1', '10.16.1.1' and '111'. No value is printed opposite Event Name or opposite Source Port on that page, so the bad-event row is not filled in from Figure 15.39."
  - "p139 the header labels OCR as 'Source Destination Desti nation' interleaved with the real column headers, so the diagram's label-to-column mapping is not recoverable."
  - "p135 the three storage-decision headings print in the slide as 'Storage Duration', 'Ways of Accessing the Logs' and 'Volume of Data to Be Stored', but the running prose discusses them in the order storage duration, volume of the data, way of accessing. Both orders are given; neither is declared the canonical one."
  - "p136 the page prints 'It should able to handle data growth over time.' - the missing 'be' is as printed and is not corrected."
  - "p138 the page names 'Common Event Expression (CEE)' only in this one place; no CEE schema, field set or standard number is printed anywhere in pp135–139."
---

[[MOC-Module-15]]

# Log Storage and Log Normalization (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp135–139.

Related: [[15-LO08c-Log-Collection-and-Log-Transmission]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO08f-Log-Correlation-and-Log-Analysis]] ·
[[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]] ·
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]] ·
[[MOC-Module-14]].

## Step 3 — Log Storage (position in the chain) _(Mod 15 p135)_

> "**After log collection and log transmission**, the log data has to be **stored in a particular
> place for analysis and auditing in the future**."

- "The log files collected from various devices, like **antimalware tools, proxies, firewall,
  authentication servers, routers, and switches**, should be **stored in a central
  repository/database**."
- Slide: "All the logs files collected from various devices are stored in a **central
  repository/database**"; "Log messages are **stored and retrieved from databases in a structured
  way**."
- Slide: "The storage requirements for log data selected based on its **size, importance,
  accessibility**".

Three factors to keep in mind while deciding log storage (slide headings, p135): **Storage Duration ·
Ways of Accessing the Logs · Volume of Data to Be Stored**.

## Storage duration _(Mod 15 p135)_

> "**Storage duration: The duration of time for which the data is stored is known as storage
> duration.** Storage duration for logs can be different. It **depends on the type of log** that is
> being stored."

Two storage systems result — the split is **long-term vs short-term**, not "hot vs cold":

| | **Cloud storage** | **Distributed storage system** |
|---|---|---|
| Log type | "**long-term log** and does **not need instant analysis**" → stored in the cloud | "**short-term log**" → stored in distributed storage |
| Slide wording | "logs that **require to be analyzed later are archived** and can be stored on the cloud, which **costs less for large amounts of data**" | "logs required to be **analyzed frequently** or to be **stored for a shorter period of time** are stored in a **distributed storage system**" |
| Purpose | "used to **archive and store long duration logs**" | "used to **archive and store short-duration logs that need to be analyzed frequently**" |
| Cost | "**flexible and relatively cheap for a large amount of data**" | "requires **physical equipment** and **occupies more amount of space, which is not cost-efficient**" |
| Security | "provides **encrypted storage** that keeps the logs **secure during data transfer**" | *(not stated on p135)* |
| Layout | "**data is arranged in an indexed form**" | *(not stated on p135)* |

## Volume of the data to be stored _(Mod 15 p135–136)_

- "The log data produced by **each device may vary in memory** as different devices produce different
  amounts of data."
- "Therefore, **different systems are used for applications that generate different amounts of
  logs**."
- "The generation of log data **depends upon the number of servers** on which the application is
  running."
- "A storage system that is used for storing logs should be **highly scalable** and must be able to
  **function properly even with a large amount of data**. It should able to handle **data growth over
  time**." _(p136)_

## Way of accessing the logs _(Mod 15 p136)_

- "The storage system for storing the log data is to be selected based upon the **frequency and ease
  of access**."
- "If the network defender wants to **access the log data quickly**, then **distributed storage
  system or local storage** is a better option."
- "**By default, the log viewer shows the log data, including syslog.** The individual logs can be
  found by **searching manually**."
- "If **access to these files is difficult and does not fulfill monitoring purpose**, then **some
  storage systems cannot be used for real-time analysis**."

---

## Step 4 — Log Normalization _(Mod 15 p137–138)_

> "**Log normalization is the process of accepting logs from heterogeneous sources with different
> formats and converting them into a common format.**"

### Why it is needed — every device writes its own shape _(Mod 15 p137)_

"The various devices and applications produce log data in **their own default format**."

| Source | Fields the page prints |
|---|---|
| **Web proxy logs** | "**source IP address, URL, status code, browser name, and version**, etc." |
| **Antispam logs** | "**sender and destination email addresses, source IP address, source domain, spam score**, etc." |
| **Firewall logs** | "**source and destination IP addresses and ports, protocol**, etc." |

> "**Collecting all this data in its different formats and then arranging and indexing it is a
> difficult task. Therefore, log normalization is needed to rectify this problem.**" _(p138)_

- "It is performed **regardless of the source and protocol used (i.e., syslog, SNMP, database,
  etc.)**." _(p138)_
- "**It forms an important step in log correlation.**" _(p138)_

### Mechanism — CEE and the regular expression _(Mod 15 p137–138)_

- "During normalization, **raw log data is collected from different sources** and **proper parsing
  expression is used to normalize the data**."
- "**According to Common Event Expression (CEE)**, the logs are **mapped with a standard scheme or
  framework to parse the data**."
- "**Most of the log analysis systems use a regular expression to parse the data.**"
- Outcome: "Log messages are **converted into a more meaningful, predictable, and consistent piece of
  information** after normalization."

### Steps involved _(Mod 15 p137–138)_

1. "The **log collector** collects logs from various sources."
2. "**Source type** is identified based on the event."
3. "**Parser is loaded, and regex is set** to identify the fields in the event."
4. "**Normalization is performed**, and the logs are categorized."
5. "**Aggregation and filtering** are applied."
6. "The above is **repeated for each event**."

Note the loop: steps 2–5 are **per event**, not per source.

### Worked example — Figure 15.39, "good event" _(Mod 15 p138)_

Prose framing: "The below diagram represents the normalization process of a good event, where **all
normalized fields are highlighted in green**."

**Raw event stream, as printed on p138:**

```
Feb 1 access-list 12 event-connection proto=udp srcip=lo.lo.o.l srcport=10240 dstip=10.16.1.I dstport=lll
```

**Parsing expressions carried on the diagram, as printed (both truncated/unbalanced):**

```
IP="dstip\=(\d{1,3}\\d{1,3})\d{
Source Port="srcport\=(\d{I,5})"
```

So the mapping is **`key=value` in the raw stream → regex extraction → one normalized column per
field**.

**Normalized row printed under `Normalization` → `Normalized Event`:**

| Event Name | Source IP | Source Port | Destination IP | Destination Port |
|---|---|---|---|---|
| Connection Rejected | `10.0.0.1` | `10240` | `10.16.1.1` | `111` |

The p137 slide prints the same figure and the same four values (`10.0.0.1` · `10240` ·
`10.16.1.1` · `111`, the last leg OCR'd as `10.16.11`), with the event stream rendered a third way:
`Feb 1 access- list 12 event. 11 Connection rejected I I proto=udp | 1 srcipz10.10.O.1 srcpo 10240 I I
dstip-10.16.1.1 I dstport=lll I`.

### Worked example — Figure 15.40, "bad event" _(Mod 15 p139)_

> "The below diagram represents the normalization process of a bad event, where **red highlighted
> fields could not be normalized because the parser missed some regex**."

**Raw event stream, as printed on p139:**

```
Feb 1 01:00:00 access-list 12 event-Connection rejected proto=udp srcip=10.O.O.1 srcport=10240 dstip=IO.16.I.I dstport=l I I
```

**Normalized columns printed on p139:** `Event Name` · `Source IP` · `Source Port` ·
`Destination IP` · `Destination Port`.

**Recovered values printed on p139:** `10.0.0.1` · `10.16.1.1` · `111`. **No value prints opposite
`Event Name` or opposite `Source Port` on that page**, so the bad-event row is left unfilled.

Failure mode, verbatim: **"the parser missed some regex"** → those fields stay red and never become
normalized columns. This is why a normalizer's regex coverage is a security control, not a
formatting nicety.

### Fields common to event normalization _(Mod 15 p139)_

"The following fields are **common** and should be considered for event normalization."

| Field | Printed purpose |
|---|---|
| **Source and destination IP addresses** | "This field is used for **log correlation**." |
| **Source and destination ports** | "This field describes **which services are accessed or going to be accessed**." |
| **Taxonomy** | "It **categorizes the meaning of log message**." |
| **Timestamps** | "There are **two types of timestamps**: one describes the time when a specific log message was **generated** and the other describes the time when the log message **reached the logging system**." |
| **User information** | "This field describes **username, command, directory location**, etc." |
| **Priority** | "This field describes the **priority of a specific message**." |

Two things worth memorising: **IP is the correlation field** (it is why field correlation in Step 5
works at all), and **"generated" vs "reached the logging system"** is the distinction the centralized
logging challenges on p150–151 attack when host clocks disagree — see
[[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]].






Steps 2–5 run **per event**, not per source.


