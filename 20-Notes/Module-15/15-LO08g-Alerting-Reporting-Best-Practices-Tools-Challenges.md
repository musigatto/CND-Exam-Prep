---
type: note
module: "15"
lo: "08"
tags: [process, tool, bestpractice, threat, mod/15]
topic: "Step 7 alerting and reporting, centralized logging best practices, CLM tools, centralized logging challenges, and the p152 Module Summary"
exam_weight: unknown
status: done
unresolved:
  - "p152 the Module Summary slide enumerates EIGHT steps - 'log collection, log transmission, log storage, log normalization, log correlation, log analysis, alerting, and reporting' - but the body numbers SEVEN: p135 = Step 3 Log Storage, p137 = Step 4 Log Normalization, p140 = Step 5 Log Correlation, p142 = Step 6 Log Analysis, p145 = Step 7 'Alerting and Reporting' (one step, heading printed singular). The summary splits Step 7 into 'alerting' and 'reporting'. Both printed forms are kept and the difference is NOT reconciled; see the '## Module summary' section."
  - "p152 the summary slide says 'Centralized logging, monitoring, and analysis are done through a series of steps' whereas p121 (recorded in 15-LO08c) prints 'In centralized logging, logging, monitoring, and analysis of logs are performed through a series of steps'. The summary drops 'logging' from the triad. Both quoted; p121 is outside this slice."
  - "p152 the summary prints 'log normalization' as step 4; the p121-p122 process figure prints step 4 as bare 'Normalization' and the p137 section heading prints 'Step 4: Log Normalization'. Three printed wordings, all kept."
  - "p152 the summary uses the abbreviation 'CLM' ('local logging and CLM concepts') and never expands it. No expansion is supplied here."
  - "p145 the section heading OCRs as 'Step Z: Alerting and Reporting' in the running prose (the slide heading prints 'Step 7: Alerting and Reporting'). Rendered as Step 7, matching the slide heading; the OCR form 'Step Z' is recorded here."
  - "p148 the printed 'Source:' caption for XpoLog reads 'http://www.xplg.com' ('xplg', not 'xpolog' and not 'xplog'). Quoted exactly as printed and not corrected. The p147 figure tile prints the tool name as 'Xpolog' with 'http://www.xpolog.com'; both printed forms are kept."
  - "p148 the printed 'Source:' caption for LogRhythm is 'http://logrhythm.com' (http, no www, no trailing slash) while the p147 figure tile prints 'http://'ogrhythm.com'. Both printed forms are kept."
  - "p147 the printed 'Source:' caption under Logmatic is 'https://www.datadoghq.com' - a DataDog URL under the Logmatic heading. Reproduced exactly as printed; it is NOT assumed to be a typo for logmatic.io. The p147 figure tile separately prints 'Logmatic https://logmatic.io'."
  - "p147 the figure tile grid prints twelve names - Splunk, Logmatic, Logstash, Sumo Logic, Papertrail, LogRhythm, Retrace, Logentries, Graylog, Xpolog, LOGalyze, Loggly - but the running prose describes only ten. LOGalyze and Logentries appear in the figure ONLY and have no description anywhere in pp147–149. Figure tiles are treated as screenshot non-evidence, so neither is given a capability here."
  - "p150 three slide bullets under 'Centralized Logging Challenges' have NO prose elaboration anywhere in pp150–151: 'Managing the available resources with continuously increasing log data', 'With the changing threat landscape, it is difficult to monitor using existing capabilities', and 'Difficulty in determining the purpose and importance of data sources'. Only their printed wording is available."
  - "p150-p151 the prose introduces four sub-items under 'Challenges in log generation and storage' (many log sources, inconsistent log content, inconsistent timestamps, inconsistent log formats) but the slide prints only three bullets. Both lists are given; neither is aligned to the other."
  - "p151 prints 'an incorrect timestamps could display that event M occurred 30 s before event N' - the singular/plural slip is as printed. The event letters M and N are the page's own."
---

[[MOC-Module-15]]

# Alerting, Reporting, Best Practices, Tools, Challenges and Module Summary (§15.08)

> **LO#08: Discuss centralized log monitoring and analysis** _(Mod 15 p3)_
> Covers pp145–152 (p152 = Module Summary).

Related: [[15-LO08f-Log-Correlation-and-Log-Analysis]] ·
[[15-LO08e-Log-Storage-and-Log-Normalization]] ·
[[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] ·
[[15-LO08c-Log-Collection-and-Log-Transmission]] ·
[[15-LO02d-Monitoring-and-Analyzing-Windows-Logs]] ·
[[15-LO07e-Apache-Access-Log-Fields-and-Monitoring]] ·
[[MOC-Module-14]] ·
[[MOC-Module-16]].

## Step 7 — Alerting and Reporting _(Mod 15 p145)_

> "**An alerting system in a centralized logging application alerts the user if any suspicious event
> is observed in the logs or calculated matrices.**"

- "It is necessary that a **centralized logging system should have an alerting system** that
  **monitors logs for any changes** and **send a notification if any abnormalities detected**."
- "The notification may take place in **many ways (email, desk tickets, etc.)**; however, the
  **respective staff should be informed in due time**, so that they can **take precautionary measures
  to prevent the breach**."
- Benefit: "gives a **360-degree view of the activities that are going on in the network**", and
  helps the organization "**improve its security**".

### Purpose of the alerting system _(Mod 15 p145)_

Two purposes, as printed on the slide: **Error reporting · Monitoring**.

Detecting and alerting is where this module hands over to incident response — see
[[MOC-Module-16]].

## Centralized logging best practices _(Mod 15 p146)_

Nine items, as printed:

1. "Ensure that the **logging feature is enabled on the devices that are connected to the
   network**."
2. "**Administrator should be able to quickly handover the authority to security professionals** to
   give access to them **at the time of an emergency**."
3. "**Consult the legal department** when developing policies regarding **storage, retrieval,
   analysis, etc.** of the log files."
4. "Ensure **safe transmission and storage of the logs** in the network."
5. "Consider **all sources of logs** in the network and **collect appropriate logs**."
6. "The data that is stored should be **accessible when investigating an incident**.
   **Authentication and security should not be compromised** in the process of making the data
   available."
7. "**Maintain a consistent structure of the logs** that are being stored."
8. "**Set the severity levels for the alerts.**"
9. "**Indexing and storing incident logs is a must** for future reference and **performing
   correlation using that data**."

Slide bullets print items 1, 3, 4 and 5 — **items 2, 6, 7, 8 and 9 appear in the prose only**.

## Centralized logging / log management (CLM) tools _(Mod 15 pp147–149)_

"Below are some **CLM tools** that can be used for centralized logging."

`Source:` captions are reproduced **exactly as printed**.

| Tool | Printed `Source:` | What the page says it does |
|---|---|---|
| **Splunk** _(p147)_ | `https://www.splunk.com` | "**aggregates and analyzes log data**. It provides insights to **quickly detect and respond to internal and external attacks** and simplify threat management. It helps teams gain **organization-wide visibility and security intelligence** for **continuous monitoring, incident response, security operations**, and provides executives a **window into business risk**." |
| **Logmatic** _(p147)_ | `https://www.datadoghq.com` | "a **log analyzer tool** that **automatically detects unexpected behavior** that would have **previously taken days to find using traditional log-processing tools**. It provides **very granular information** that **reduces the bug fix time**." |
| **Logstash** _(p147)_ | `https://www.elastic.co` | "an **open-source, server-side data processing pipeline** that **ingests data from a multitude of sources, simultaneously transforms it**, and then sends it to the preferred "**stash**." It ingests from "**logs, metrics, web applications, data stores, and various AWS services, all in continuous, streaming fashion**." |
| **Sumo Logic** _(p148)_ | `https://www.sumologic.com` | "a **suite of applications and integrations**" used to tackle "**common cloud infrastructure challenges such as log management, real-time monitoring, resolving user experience issues, and performance issues for major cloud platforms**." Can "**analyze and correlate AWS CloudFront data with the origin data/other data sets**" and "improve availability and end-user experience while **enforcing rigorous security controls**." |
| **Papertrail** _(p148)_ | `https://papertrailapp.com` | "log management tools for **search, live tail, flexible system groups, team-wide access**, and **integration with popular communication platforms such as PagerDuty and Slack**". Works with "**syslog, text log files, Apache, MySQL, Ruby on Rails, Windows events, Tomcat, routers, firewalls**, etc." |
| **LogRhythm** _(p148)_ | `http://logrhythm.com` | "an **end-to-end platform** that is designed by security experts … delivers **patented, high-performance, distributed, and highly available processing of machine and forensic data** received from **data collectors, system monitors, and network monitors** and then transforms it into a **contextualized form**." |
| **Retrace** _(p148)_ | `https://stackify.com` | "an **application performance monitoring solution** designed for developers to **improve code, which in turn improves performance and fixes hidden exceptions**. It gives developers **all the application insights they need in one place**." |
| **Graylog** _(p148)_ | `https://www.graylog.org` | "designed for **log collection, storage, enrichment, and analysis**. It offers simplicity in **searching, exploring, and visualizing data**, which means **no expensive training or tool experts are required**. Performs **speed analysis** … simpler **administration and infrastructure management**." |
| **XpoLog** _(pp148–149)_ | `http://www.xplg.com` | "used to **discover errors and problems in log data**. XpoLog **filters the search results and uses a complex search syntax**, which results in a **summary table of events and transactions**, including insights for further investigation. It allows **creation of custom rules in a predefined layer and it automatically layers the auto-detected layer. This way, all rules are covered in the search.**" |
| **Loggly** _(p149)_ | `https://www.loggly.com` | "**Loggly 3.0 charts** provides a variety of ways to **quickly visualize data**, and its **dashboards helps organize this data in the most useful ways for detecting and understanding the problems that arise in software and infrastructure**." |

**The auto-layering behaviour is the one mechanism the page singles out** _(pp148–149)_: XpoLog
creates custom rules **in a predefined layer**, and **automatically layers the auto-detected layer**,
so that "**all rules are covered in the search**". Note this sentence **straddles the p148/p149 page
break** — the object of "allows creation of custom rules" is not printed until p149.

Two names in the p147 figure grid — **Logentries** and **LOGalyze** — carry **no description
anywhere in pp147–149**. See `unresolved:`.

> **Evidence note.** p147's product grid, p148's Sumo Logic block and the product tiles are treated
> as **screenshot / product-page non-evidence**. Only the numbered steps, the running prose and the
> printed `Source:` captions above are taken from them; no value, dashboard figure, price or UI label
> is read out of any image.

## Centralized logging challenges _(Mod 15 pp150–151)_

> "Organizations face various log management-related challenges that are categorized into **three
> parts**: first, **challenges in generation and storage of logs** due to their **variety and
> prevalence**; second, **challenges in maintaining confidentiality, integrity, and availability of
> logs**; and finally, **challenges in identifying skilled people for performing log analysis**."

### 1 — Challenges in log generation and storage _(Mod 15 p150)_

"Various hosts, OSes, security system, and applications generate and store **a variety of log files**,
which makes log management a complex process."

**(a) Many log sources** — "**Multiple log sources are present on many hosts throughout the
organization**, and **a single log source may produce several logs**." Example: "a **web application
may store network-related activities in one log and authentication-related activities in another
log**."

**(b) Inconsistent log content** — "A **single log source records a specific portion of information**
in its log entries such as **host IP addresses, usernames**, etc." and, "for maintaining efficiency",
each source "**store[s] only that portion of the information that is most important to them**".

> "It becomes **difficult to connect events generated by different log sources** as log entries
> recorded by one log source may be different from the log entries recorded by another log source, and
> they would **hardly have any common values**."

Printed illustration: "**log source A may record username but not the host IP address whereas log
source B may record host IP address but not the username.**"

**(c) Inconsistent timestamps** — the page's own callout:

> "**The timestamp of every log is set using its internal clock.** (If the host's clock is incorrect,
> then it makes it difficult to analyze the logs and even more complicated when the logs are
> collected from multiple hosts)" _(p150)_

> "It becomes **difficult to analyze the logs and even more complicated when the logs are collected
> from multiple hosts if the host's clock is set incorrectly**. For example, **an incorrect timestamps
> could display that event M occurred 30 s before event N. However, in reality, event M may have
> occurred 1 min after event N.**" _(pp150–151)_

**30 s vs 1 min, and in the opposite direction** — an incorrect timestamp does not merely add noise,
it **inverts the causal order of two events**. This is the same "generated vs reached the logging
system" pair the normalizer splits on p139, and the reason p144 makes "synchronized with the NTP
server" best practice #1.

**(d) Inconsistent log formats** — "**databases, tab-separated or comma-separated text files, XML
files, and binary files**. Some logs use **standard** formats, and others use **proprietary**
formats. Some are **developed to store locally**, while others are **developed for transmission to
another system**. This **complicates the process of log review**."

Remedy, as printed: "organizations need to adopt **automated techniques for converting logs with
different formats into a standard format**." — i.e. Step 4 normalization is the answer to challenge
1(d).

### 2 — Challenges in protecting the log _(Mod 15 p151)_

- "Log entries should be **secured against any breach of confidentiality or integrity**."
- "Logs **collect critical and sensitive information such as login credentials, emails**, etc.
  **intentionally and unintentionally**." → raises "**security and privacy concerns for both, the
  persons that are going to perform the log review and to others that may access logs by authorized
  or unauthorized methods**."
- If not secured, logs "are **susceptible to alteration and destruction**. This leads to a variety of
  security issues such as **permitting malicious activities without any warnings and alerts,
  exploiting evidence to hide the identity of a suspicious person**, etc."
- **Availability** also has to be protected: "Logs have a **fixed size** to store log data. If that
  size reaches its **maximum limit**, then the log will **overwrite the old data with the new data,
  making old log data unavailable**."
- Remedy: "**save copies of log files for a longer period of time than the original log sources can
  support**."

That last line is why storage duration is a *design* decision on p135, not an afterthought.

### 3 — Challenges in log analysis _(Mod 15 p151)_

- "**Generally, system administrators are responsible for performing log analysis** to determine
  events of interest."
- "However, this task is **considered as a low-priority one by most system administrators** as they
  are responsible for **managing operational issues as well as providing solutions to security risks
  and vulnerabilities**."
- "they **may not have received any training** to perform log analysis efficiently or **may not have
  any tools to automate the process**".
- "Some system administrators **may not find the process of log analysis interesting or a
  productive use of their time**."
- Fix: "log analysis needs to be considered as a **proactive process instead of a reactive one**.
  **Suspicious activities or indicators of compromise should be detected before any critical problems
  arise.**"

---

## Module summary _(Mod 15 p152)_

### As printed — slide bullets

1. "**Logs play a pivotal role in incident detection**"
2. "**Almost every device on the network has the capability to produce logs**"
3. "The log file contains **various types of information that help provide valuable and actionable
   information**"
4. "**Monitoring and analyzing log files of different devices locally can be a difficult task.
   Centralized logging helps you to simplify the process**"
5. "In centralized logging, **logs from different devices and applications on the network are
   collected to one central location**"
6. "Centralized logging, monitoring, and analysis are done through a **series of steps, which
   includes log collection, log transmission, log storage, log normalization, log correlation, log
   analysis, alerting, and reporting**"

### As printed — running prose

> "In this module, we discussed **incidents, events, and logs**; **log sources that generate logs**;
> the **role of logging in detecting security threats**; and **local logging and CLM concepts**. In
> local logging, we discussed **monitoring and analysis of different logs of various devices** such
> as **Windows logs, Linux logs, Mac logs, firewall logs, Windows Defender Firewall logs, Mac OS X
> firewall logs, Linux firewall logs, Cisco ASA firewall, Check Point firewall, router logs, web
> server's logs**, etc. This module also discussed **monitoring and analysis of logs through
> centralized logging**."

### What the summary contradicts

**The step count.** Bullet 6 enumerates **eight** steps — "…log analysis, **alerting, and
reporting**". The body numbers **seven**:

| # | Body step, as printed | Page |
|---|---|---|
| 3 | "**Step 3: Log Storage**" | p135 |
| 4 | "**Step 4: Log Normalization**" | p137 |
| 5 | "**Step 5: Log Correlation**" | p140 |
| 6 | "**Step 6: Log Analysis**" | p142 |
| 7 | "**Step 7: Alerting and Reporting**" | p145 |

Step 7 is **one step with a compound heading**, and the module gives it a single section. The summary
**splits it into two items**, so its list is one item longer than the numbered process. Both readings
are recorded; **neither is corrected here**. Full 7-step list, from p121–122, in
[[15-LO08c-Log-Collection-and-Log-Transmission]].

Two smaller drifts, also un-reconciled: bullet 6 says "**Centralized logging, monitoring, and
analysis**" where p121 prints "**logging, monitoring, and analysis**"; and the summary's step 4 reads
"**log normalization**" where the p121–122 figure prints bare "**Normalization**" and the p137
heading prints "**Log Normalization**".

### What the summary omits

Nothing in p152 refers to any of the following, all of which the body prints:

| Omitted from the summary | Printed at |
|---|---|
| **The entire challenges topic** — three challenge classes, log tampering, log overwriting, the clock problem, the admin skills gap | pp150–151 |
| **Storage design** — storage duration, cloud vs distributed storage, scalability, growth over time | pp135–136 |
| **Normalization mechanism** — parsing expression, **Common Event Expression (CEE)**, regular expression, protocol-independence (syslog / SNMP / database) | pp137–138 |
| **The six common normalization fields** — source/destination IP and ports, **taxonomy**, the **two timestamp types**, user information, priority | p139 |
| **The correlation taxonomy** — micro-level ("atomic") vs macro-level ("fusion"), field vs rule correlation, and the macro inputs vulnerability / profile (fingerprint) / anti-port / watch list / geographic location | pp140–141 |
| **Manual vs automated log analysis** — the two approaches and the "only experts can carry it out" vs "time- and cost-efficient" verdict | p143 |
| **Log-analysis best practices** — all twelve, including NTP synchronization and end-to-end logging | p144 |
| **Centralized logging best practices** — all nine | p146 |
| **Every CLM tool name** — Splunk, Logmatic, Logstash, Sumo Logic, Papertrail, LogRhythm, Retrace, Graylog, XpoLog, Loggly | pp147–149 |
| **Alerting's two stated purposes** — **error reporting** and **monitoring** — and the notification channels (email, desk tickets) | p145 |

The sharpest gap: for a module whose argument is that log management is **hard**, the summary states
no difficulty at all. Everything the module says makes the job difficult — variety, clock skew,
tampering, overwriting, untrained admins — is absent from it.







