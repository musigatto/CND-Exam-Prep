---
type: note
module: "14"
lo: "06"
tags: [concept, tool, process, mod/14]
topic: "User behaviour analytics (UBA) and its tools"
exam_weight: unknown
status: done
unresolved:
  - "p101 figure 14.33's caption prints 'Lifecycle View of User Behavior using ClearTap' while the tool heading and body print 'CleverTap'. Both printed; body spelling used for the tool name, caption quoted as printed."
  - "p103-p104 the tool is listed as 'Crazyegg' in the list heading band and written 'Crazy Egg' in the p104 body. Both printed."
  - "p103-p104 the tool is listed as 'Crea bl' / 'Creabl' in the band; the p103 body prints 'Creabl'. Used as printed."
  - "p101-p102 figures 14.33-14.34 are product dashboards — panel labels/values not transcribed (screenshot non-evidence)."
---

[[MOC-Module-14]]

# User Behaviour Analytics (UBA) and Its Tools (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp99–104.

First of the two behaviour-analytics families. See also [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]]
(where user behaviour first enters the detection framework) and
[[14-LO06g-UBA-vs-UEBA-and-Module-Summary]] for the printed UBA-vs-UEBA table.

## What UBA is _(Mod 14 p99)_

> "User Behavior Analytics (UBA) is a **security process that detects abnormal user activities on the
> network**."

- Goal: "**detect and mitigate insider threats**, as well as to **identify suspicious or malicious activities**."
- Engine: "leverages **machine learning and data science** to develop insights into the **behavioral patterns of users in real time** in each environment."
- Data: "analyzes **data, authentication, and network logs stored in SIEM and log management** to identify traffic patterns caused by user behavior."
- Mechanism: "creates **baselines for user activities and highlights any deviations** from these baselines. These anomalies may serve as **indicators of potential threats or security breaches**."
- Tracked items: "**files accessed, emails sent and read, apps opened, network activity**, etc."
- Detects: "spot[s] irregularities such as **data breaches** and identifies potential security threats and **unauthorized access attempts**."

### How UBA works _(Mod 14 p99)_

1. "Collects diverse data on a user from **multiple sources and locations** within the environment, which may include **log files, network traffic, and application usage**."
2. "Through the process of **behavioral profiling**, UBA creates a **baseline of the user's typical behavior**, encompassing **regular activities, interactions**, and even **passive information like the user's geographic location**."
3. "Utilizes **machine learning, statistical modeling**, and other sophisticated analytics to identify deviations from **either the user's established baseline or the behavior of their peers**."
4. "Assesses their potential risks and **assigns risk scores based on the severity of the detected anomalies**."
5. "**Generates an alert** upon potentially malicious activity."

## Use cases of UBA _(Mod 14 p100)_

| Use case | What UBA does |
|---|---|
| **Insider threats** | "Many employees have access to crucial data. If an employee **goes rogue**, it can be challenging to stop them… UBA helps in **detecting when their behavior deviates from the norm**" |
| **Data theft** | Identifies "instances where a user attempts to **download information beyond their authorized permissions**." The alert "might be triggered **after** unauthorized access and data download have occurred", but "enables administrators to swiftly respond by **promptly disabling the account's access**" |
| **Compromised user accounts** | Detects "abnormal activities, like **unauthorized access to sensitive information that the user typically does not attempt to access**"; alerts a security analyst, "prompting an **immediate investigation**" |
| **Compromised hosts** | Identifies compromised hosts, "**whether they are servers or personal devices**, such as in the case of a **malware infection**"; an abnormal host "triggers an alert, prompting cybersecurity personnel to conduct a **thorough investigation**" |

> Note the asymmetry the page states plainly: for **data theft** the alert can only come **after** the download,
> so UBA's role there is **containment** (disable the account), not prevention.

## UBA tools — CleverTap and FullStory _(Mod 14 pp101–102)_

| Tool | Source | What the page says |
|---|---|---|
| **CleverTap** | `https://clevertap.com/` | "Ingests data from various sources like **CRM, apps, and the web** for deeper insights. Tools like **cohorts, funnels, and pivots** are used to gain insights into user behavior. It creates **micro-segments based on past behavior, real-time actions, and interests**. It identifies **at-risk customers based on recency and frequency**" |
| **FullStory** | `https://www.fullstory.com/` | "**Analytics platform** that helps organizations **track and monitor user activity**. **Session playbacks** provide a **complete view of the user's journey**, with everything **automatically indexed, from clicks to page transitions**. It assists in **tracking and monitoring user activity, inspecting customer activity, and creating funnels**" |

## Additional User Behavior Analytics Tools _(Mod 14 pp103–104)_

| Tool | Source as printed | What the page says it does |
|---|---|---|
| **Mouseflow** | `https://mouseflow.com/` | "Enables **checkout funnel analysis** to identify **path-to-purchase** improvements"; works "regardless of the conversion funnel type — **eCommerce, financial services, SaaS, telehealth**"; its "**website heatmap tool records 100% of your traffic by default, instead of sampling only a fraction of it**" |
| **Creabl** | `https://creabl.com/` | "Records website interactions by **capturing actual mouse movements** as visitors navigate across pages, enabling **user session recording**. You can observe **where visitors click and how frequently they scroll**. Additionally allows for the **automatic sending of emails or the execution of other actions, based on specific events or multiple triggers**, such as clicking a link or completing a form" |
| **Hotjar** | `https://www.hotjar.com/` | "Intuitive, visual way to **discover, consolidate, and communicate user needs**"; "**visualize conversion flows with funnels**"; "understand **where users are getting stuck by zooming into relevant recordings**"; "high-level view of user data, spot issues before they become serious, identify trends" via its dashboard |
| **Userlytics** | `https://www.userlytics.com/` | Dashboards feature "**highlight reels, transcriptions, AI UX Analysis, and Sentiment Analysis**"; "**website usability testing** helps uncover **usability issues and customer pain points**"; "**no-download unmoderated testing**" allows "**shorter study sessions with more participants**" |
| **Crazy Egg** | `https://www.crazyegg.com/` | "Analytics platform that **tracks and optimizes website visitor behavior** to improve user experience, increase conversion rates, and boost the bottom line"; "**compares the performance of referring traffic, campaigns, and landing pages against each other**" |
| **DATADOG** | `https://www.datadoghq.com/` | "**Real User Monitoring (RUM)** offers insights into an application's **frontend performance from the perspective of real users**. It seamlessly **correlates every user journey with synthetic tests, backend metrics, traces, logs, and network performance data**", enabling "**quick detection of poor user experiences**" and issue resolution "with **context from across the stack**" |

> As printed, every tool in this section is a **web/marketing-behaviour analytics platform** (funnels, heatmaps,
> CRM, session replay, workforce UX) rather than a security UBA engine — unlike Log360 UEBA and DNIF elsewhere in
> this LO. Recorded as printed; not reconciled.






