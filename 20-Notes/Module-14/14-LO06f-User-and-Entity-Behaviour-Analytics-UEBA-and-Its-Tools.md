---
type: note
module: "14"
lo: "06"
tags: [concept, tool, process, mod/14]
topic: "User and entity behaviour analytics (UEBA) and its tools"
exam_weight: unknown
status: done
unresolved:
  - "p111 the ActivTrak URL prints as 'ttps://www.activtrak.com' in the tool list (missing leading 'h'); the p112 body prints 'https://www.activtrak.com/'. Body form used."
  - "p111 the tool heading prints 'IBM Security Qradar SIEM' while the p111 body prints 'QRadar SIEM'. Note that p90 prints a different product, 'IBM QRadar Network Insights'. Kept as printed per page."
  - "p108 is a single screenshot page (figure 14.35, 'Dnif Webpage'); its OCR fragment 'Confidence Level i.e. the certainty of the raised signal' appears to be a UI annotation inside the capture and has been treated as screenshot non-evidence — not transcribed."
  - "p110 is a single screenshot page (figure 14.36, Securonix Dashboard) containing playbooks, ticket numbers and dates — screenshot non-evidence, nothing transcribed."
  - "p105-p112 the OCR renders 'UEBA' as 'I-JEBA'/'IJEBA' in places; rendered as UEBA."
---

[[MOC-Module-14]]

# User and Entity Behaviour Analytics (UEBA) and Its Tools (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp105–112.

The **widest** of the three behaviour families: UBA in [[14-LO06e-User-Behaviour-Analytics-UBA-and-Its-Tools]],
NBA in [[14-LO06d-Network-Behaviour-Analysis-and-Its-Tools]]. The printed comparison is
[[14-LO06g-UBA-vs-UEBA-and-Module-Summary]].

## What UEBA is _(Mod 14 p105)_

> "User and entity behavior analysis (UEBA) is the **security process of detecting unusual anomalies in the
> behavior of users and entities like routers, endpoints, and servers** in a network."

- "Records the **normal conduct** of these entities and detects **anomalous behavior when there is a deviation from the usual pattern**."
- Watched for: "**unusual traffic patterns, malicious activities, unauthorized data access, and movement** on a network or endpoint."
- Techniques: "**machine learning algorithms, statistical analytics, and automation**."

### How UEBA works _(Mod 14 p105)_

1. "Gathers, processes, and analyzes network activity using **machine learning for users and entities** to create a **baseline behavioral reading**."
2. "These readings are collected **for each user or aggregated by department, role, or for the entire organization**."
3. "The algorithm identifies user and entity behaviors that **exceed or fall below the established baseline**."
4. "The system **raises an alert** to inform administrators and security teams that something unusual is occurring on the network."

### Components of UEBA

| Component | Definition |
|---|---|
| **Data analytics** | "Uses information about the **typical behavior** of users and entities to **create profiles of their usual actions**. By applying **statistical models**, the system can detect **deviations from normal behavior** and promptly notify system administrators" _(p105)_ |
| **Data integration** | "**Logs, packet capture data, and other datasets**" — comparing data gathered from various sources "**making the system more robust**" _(p105)_ |
| **Data presentation** | "**Conveying the findings** of the UEBA system and **formulating an appropriate response**, which can vary among organizations" _(p106)_ |

Data presentation, continued _(Mod 14 p106)_: "Some UEBA systems **generate alerts, prompting further
investigation** either by the employee or the IT administrator. In contrast, other UEBA systems are
**configured to take immediate action, like automatically cutting off network connectivity for an employee
if a cyberattack is suspected**."

## Use cases of UEBA _(Mod 14 p106)_

| Use case | What UEBA does |
|---|---|
| **Lateral movement** | "After breaching an endpoint or system, attackers can leverage it as a starting point to **infiltrate other user accounts and systems**. UEBA offers a **holistic view across multiple systems**, enabling the detection of unusual behavior throughout the network" |
| **Stolen credentials** | "While **traditional monitoring tools might not detect malicious activity** carried out using these credentials, UEBA can **recognize unusual behavior within the user's account**" |
| **Data theft** | "Examines data transfers to **differentiate potential exfiltration attacks from legitimate activities**… **evaluates the legitimacy of the destination and the appropriateness of the transmitted data** based on the **user's role and context**" |
| **Targeted devices and accounts** | "Identifies abnormal actions on **high-value assets**, such as **endpoint devices or accounts belonging to key executives like the CEO or CFO**, which advanced attackers may specifically target" |
| **Compromised hosts** | "Attackers can remain undetected for **extended periods, even months or years**… UEBA helps in **spotting changes in system behavior** and facilitates investigations to ascertain the presence of malicious activity" |
| **Insider threats** | "Malicious insiders **might evade detection by conventional security solutions**. UEBA can detect risky or suspicious actions by users, such as **transferring large data volumes, gaining higher privileges, or accessing unexpected applications or systems**" |

## UEBA tools — DNIF and Securonix _(Mod 14 pp107–109)_

| Tool | Source | What the page says |
|---|---|---|
| **DNIF** | `https://www.dnif.it/` | "Leverages **machine learning-based threat detection and user behavior analytics** to protect and enhance your enterprise security posture". "**Identifies users exhibiting risky behavior, such as privileged access and atypical data movement**." "**Analyzes and detects patterns of human behavior in big data to reduce the attack surface**." "**Learns from the anomalies that are most valuable** and then **screens out irrelevant detections**." "**Historical analysis** allows for the quick learning and profiling of **user/entity/parameter behavior**." "**Leverage ML models to detect and make high-level decisions** around the organization's security posture" |
| **Securonix** | `https://www.securonix.com/` | "Helps **uncover complex threats with minimal noise**." "Provides **entity context** needed to **correlate and identify advanced threats that may span across multiple events**." "**Extends security monitoring to cloud environments with built-in APIs for all major cloud infrastructure and application technologies**." "**Mitigates the risk from insiders using UEBA that combines events with user context** to alert the organization of behaviors that **deviate from the established baseline**." "Can be **quickly deployed on top of the existing SIEM without having to replace it**" |

## Additional User and Entity Behavior Analytics Tools _(Mod 14 pp111–112)_

| Tool | Source as printed | What the page says it does |
|---|---|---|
| **IBM Security Qradar SIEM** | `https://www.ibm.com/` | "Applies **machine learning and user behavior analytics to network traffic alongside traditional logs**, providing analysts with **more accurate, contextualized, and prioritized alerts**. Makes threat detection smarter and allows for **faster remediation**"; "run your business in the **cloud and on-premises** with visibility and security analytics built to **rapidly investigate and prioritize critical threats**" |
| **CrowdStrike Falcon Endpoint Protection** | `https://www.crowdstrike.com/` | "Protects systems through a **single lightweight sensor** — "there is **no need for on-premises equipment** to be maintained, managed, or updated, and **no requirement for frequent scans, reboots, or complex integrations**" |
| **cynet 360 AutoXDR** | `https://www.cynet.com` | "Enables any organization to **put its cybersecurity on autopilot**, streamlining and **automating its entire security operations**"; "enhanced levels of visibility and protection, **regardless of the security team's size, skill, or resources**, and **without the need for a multi-product security stack**" |
| **Teramind** | `https://www.teramind.co/` | "Provider of **insider threat management, data loss prevention, and productivity and process optimization** solutions powered by **user behavior analytics**." Serves "**enterprises, governments, and SMBs**". Available "as an **on-prem, cloud, private cloud, or hybrid deployment**"; enables organizations to "**detect, prevent, and mitigate insider threats and data loss with forensic-backed evidence**" while providing "granular behavioral data" |
| **Safetica** | `https://www.safetica.com` / `https://www.safetica.com/us` | "Solutions for **insider threats and data loss**." Two options: **Safetica NXT** (**cloud-native**) and **Safetica ONE** (**on-prem**). "**Safetica ONE** protects data against **human error and malicious attacks**. It is an **all-in-one** solution that integrates seamlessly with your existing security system." "**Safetica NXT**… is a **cloud-based DLP solution designed for companies without in-house infrastructure**, providing **low-maintenance security** through its ease of use and automated features" |
| **Microsoft ATA** | `https://learn.microsoft.com` | "**Advanced Threat Analytics**": "**minimize the risk of damage** and gain a **succinct, real-time view of the attack timeline**"; "utilize **built-in intelligence to learn, analyze, and identify both normal and suspicious user or device behavior**" |
| **ActivTrak** | `https://www.activtrak.com/` | "**Workforce analytics software-as-a-service** platform that **analyzes digital work activity data** to glean insights that improve how people work, **whether in the office or remotely**. The workforce analytics cloud offers **visibility and insights across people, processes, and technology**" |






