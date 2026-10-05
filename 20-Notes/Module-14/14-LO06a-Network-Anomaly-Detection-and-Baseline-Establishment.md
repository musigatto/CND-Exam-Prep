---
type: note
module: "14"
lo: "06"
tags: [concept, process, tool, mod/14]
topic: "Network anomaly detection and baseline establishment"
exam_weight: unknown
status: done
unresolved:
  - "p79 the acronym NBAD is used for two different expansions in the same page: 'Network Behavior Anomaly Detection (NBAD) tools' and 'network anomaly detection and behavior analysis (NBAD) plays a vital role'. Both printed; not reconciled."
  - "p79 the flowmon figure band prints 'Source: https://www.fbwmm.com/' while p80 body prints 'Source: https://www.flowmon.com/' for the same tool. p80 URL used."
  - "p79-p80 the seven-step process diagram (Data Collection -> Response and Mitigation) is inside a screenshot; the step names are reproduced here only because each one is also defined in the surrounding prose."
  - "p80 figure 14.25 (flowmon dashboard) panel text and values are OCR garbage ('C(XJntry reputation', 'DICTATTACK DNS(IERY ANOMALY') — treated as screenshot non-evidence, not transcribed."
---

[[MOC-Module-14]]

# Network Anomaly Detection and Baseline Establishment (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp78–81.

Continuation of [[14-LO03a-Network-Traffic-Signatures-and-Baselining]] — baselining there is a
static signature; here it is **behaviour over time**. Why this exists: [[14-LO01b-Advantages-of-Network-Monitoring]].

## What NADBA is for _(Mod 14 p78)_

- "NADBA plays a crucial role in **identifying abnormal or suspicious activities** within a network."
- "It helps organizations **detect and respond to security incidents by identifying patterns or deviations from normal network behavior**."
- "NADBA aids in maintaining the **integrity, availability, and security** of networks."
- Complementary, not standalone: "often complemented by other security measures, such as **firewalls, intrusion detection systems (IDS), and intrusion prevention systems (IPS)**."

## Network anomaly detection and behavior analysis _(Mod 14 p79)_

Techniques and tools that identify and respond to **unusual or suspicious activities such as intrusion
attempts, malware infections, and data breaches**. Three jobs:

| Job | Detail |
|---|---|
| Unusual activity | identify and respond to **intrusion attempts, malware infections, data breaches** |
| Health/performance | monitor network health and performance — detect **congestion, hardware failures, misconfigurations** |
| Incident response | "helps to **reduce the impact of cyberattacks**" |

> **A network anomaly is "a sudden and brief deviation from the normal operation of a network, often caused by intruders with malicious intent."** _(Mod 14 p79)_

- **Network Anomaly Detection** = "a security technique that **monitors the network for abnormal behavior, relying on network behavior analysis**."
- Position: "used **in addition to** perimeter security systems like firewalls and antivirus software, [it] provide[s] an **extra layer of security**."
- Risk it catches: "**data theft, hidden infections, or system infection**."
- Detected behaviours: "**high traffic flow, intrusion attempts, malware infections, and data breaches**."
- Non-security issues administrators also detect: "**congestion, misconfigurations, and hardware failures**."

### What NBAD tracks _(Mod 14 p79)_

- Scale: "detecting network behavior anomalies **on a large scale** by keeping track of **packets, bandwidth, bytes, traffic volume, and protocol usage**."
- Record: "Every suspicious event is recorded in a report with its **timestamp, relevant ports, protocols, and originating and destination IP addresses**."
- **Three crucial aspects**: 1. **traffic flow patterns** · 2. **passive traffic analysis** · 3. **network performance data**.
- Method: "**machine learning, statistical analysis, and heuristics** to pinpoint abnormal behavior and deviations from established network norms."

## The seven-step process _(Mod 14 pp79–80)_

| # | Step | Definition as printed |
|---|---|---|
| 1 | **Data collection** | "collecting and analyzing data from **multiple sources** to understand and analyze trends" |
| 2 | **Baseline establishment** | "Establishing a baseline **over a longer period** improves accuracy and usefulness of the collected behavior data, aiding in analyzing the current situation" |
| 3 | **Anomaly detection** | "identifying factors such as **data points, events, and observations** that deviate from the **expected dataset behavior**" |
| 4 | **Alert generation** | "When suspicious activities are detected within the environment, **notifications are sent out**" |
| 5 | **Alert correlation** | "collecting multiple **alerts, warnings, and notifications** and correlating them to understand the **larger scope of the situation**" |
| 6 | **Incident investigation** | "identifying the **reasons and root cause** of any detected security breach" |
| 7 | **Response and mitigation** | "The **response strategy** is structured to react to threats, while **mitigation** involves processes to limit the impact of the threat" |

> Step 2 is where baselining earns its keep: **the longer the baseline period, the more accurate the behaviour
> data**. The same "longer period → more accurate" logic as [[14-LO03a-Network-Traffic-Signatures-and-Baselining]].

## Example NBAD tool — flowmon _(Mod 14 p80)_

> Page prints the name lowercase as **"flowmon"**; the body text writes **"Flowmon NBAD"**.

- Detection/response scope: "**targeted attacks, botnets, unknown malware, insider threats, data leakage**, and more."
- Data source: "**network traffic statistics exported by routers, switches, or network probes**."
- Flow standards it consumes: **`NetFlow`, `jFlow`, `IPFIX`, `NetStream`**.
- "By analyzing this data, Flowmon NBAD can effectively **detect malicious behavior within the network**."

## Network Anomaly Detection (recap) _(Mod 14 p81)_

- Monitors "**network traffic and system behavior** to identify **deviations from established normal patterns**."
- Anomalies detected: "**unexpected spikes in network traffic, unusual data access patterns, unauthorized access attempts**, and other irregular activities" → "may indicate **security breaches, operational problems, or unusual user behavior**."
- Techniques: "**statistical analysis, machine learning, or heuristics**."
- Scope: "identifying abnormal or unexpected events in the network, such as **data breaches, intrusions, malware injections**, and other malicious activities, that cause **data to deviate from its conventional pattern**."
- Analysed "based on **trends, historical data, and statistical analysis**."
- Also "maintains a check on the **health of all devices**" and ensures "**no regulations are violated**" → secure and compliant environment.

### Figure 14.26 — Network Anomaly Detection Framework _(Mod 14 p81)_

```
Network Traffic •►
                ►•→ Data Mining •→ Processing of data •→ Detection of anomalies
User Behavior ••••                 (frequent patterns)
```

- **Network traffic** "encompasses all the **requests and responses** occurring within an environment."
- **User behavior** "refers to the **actions frequently performed by users to access information**."
- "This behavior is recorded in an **audit logger**, which is then used for **data mining** to detect anomalies … through a specific model."
- Outcome: if both are normal → **no spikes, no alert**. If they deviate → "considered **abnormal and potentially threatening**", and "**alarms are triggered and sent to the business hierarchy**".

> Figure 14.26 is the pivot of the whole LO: **network traffic + user behaviour** fed together is what later becomes
> [[14-LO06d-Network-Behaviour-Analysis-and-Its-Tools]] (NBA), [[14-LO06e-User-Behaviour-Analytics-UBA-and-Its-Tools]] (UBA) and [[14-LO06f-User-and-Entity-Behaviour-Analytics-UEBA-and-Its-Tools]] (UEBA).






