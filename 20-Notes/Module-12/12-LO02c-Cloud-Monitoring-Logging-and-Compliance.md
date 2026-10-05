---
type: note
module: "12"
lo: "02"
tags: [process, policy, mod/12]
topic: "Cloud monitoring, logging, and compliance"
exam_weight: unknown
status: done
unresolved:
  - "p29: the p29 figure is headed 'Monitoring'/'Cloud Monitoring' with three placeholder images and no text, so the figure contributes nothing beyond the bulleted lists already transcribed from the figure text; the four data-monitoring questions and the six cloud-monitoring-plan items are listed once, not twice."
  - "p29: the p29 prose defines only two of the four data-monitoring activities inline (data replication, data ownership changes); data file name changes and file classification changes are glossed only by the surrounding sentences. No gloss is invented for them."
  - "p31: the p31 figure item 'Controlling log collection and distribution frequency' is glossed by p32 under separate headings ('Keep Applications Safe' / 'System Scalability'); the figure's own one-line glosses and the p32 body agree, so they are merged rather than duplicated."
  - "p31: the two questions 'What assets are they accessing?' and 'From where are they accessing the asset?' are split across the p31/p32 page break in the source; they are listed together here."
  - "p33: the p33 figure lists the three compliance considerations with the same wording as the p33 prose; they are transcribed once."
---

[[MOC-Module-12]]

# Cloud Monitoring, Logging, and Compliance (§12.02)

> **LO#02 — Understanding cloud security insights**
> Section scope: the monitoring, logging, and compliance elements of the cloud security shared
> responsibility model _(Mod 12 p20)_

## Monitoring _(Mod 12 p29–30)_

Cloud monitoring is **required to manage cloud-based services, applications, and infrastructure**.
Effective cloud monitoring helps an organization **protect** the environment from potential
threats, **store and transfer** data easily, and **safeguard** customers' personal data. _(Mod 12 p29)_

### Data monitoring — unauthorized access signals _(Mod 12 p29)_

| Activity to observe | Courseware gloss |
|---|---|
| **Data replication** | Key role in data management — migrating databases online and synchronizing data in real time. **Migration monitoring** should be performed during data replication. |
| **Data file name changes** | Data-handling activity; the **file change attributes** should be used to monitor changes in the file system |
| **File classification changes** | Monitoring through file classification changes helps determine any changes in the cloud data files |
| **Data ownership changes** | Closely monitored to **prevent unauthorized access and security breach** |

_(Mod 12 p29)_

### Data monitoring rules

- **Define thresholds and rules for normal activities** → helps detect **unusual activities**. _(Mod 12 p29)_
- **Alert the data owner** if data activity **exceeds the defined thresholds** (i.e. if any breach
  is observed in the defined threshold). _(Mod 12 p29)_

### Cloud monitoring plan — essential aspects _(Mod 12 p29–30)_

| Aspect | Courseware detail |
|---|---|
| **Identify metrics and events** | Identify key metrics/events that can potentially affect the organization's business and monitor them (p29) |
| **Use one platform to report all data** | Services that report data from **various sources on a single platform** ensure a complete perspective of performance (p30) |
| **Monitor cloud service usage and fees** | Robust monitoring to track organizational activity on the cloud **and the relevant cost** (p30) |
| **Monitor user experience** | Metrics such as **response time and frequency** (p30) |
| **Trigger rules with data** | If cloud-based activity rises/falls past a threshold, **add or remove servers** to maintain efficiency and performance (p30) |
| **Separate and centralize data** | Monitoring of data **centralized and separated** from the monitoring of applications and services (p30) |
| **Try failure** | Evaluate the alert system by **testing the tools** to determine the potential outcome during an **outage or data breach** (p30) |

_(Mod 12 p29–30)_

## Logging _(Mod 12 p31–32)_

Security logs provide a **record of the activities in the IT environment**. They are used for:

- **threat detection**
- **data analysis**
- **compliance audits**

— to enhance cloud security. _(Mod 12 p31)_

> Scale driver: instead of a few servers, companies now maintain **thousands of servers** playing a
> smaller role within the application infrastructure stack — this **complicates the aggregation of
> data silos**. _(Mod 12 p31)_

### Efficient security log management for the cloud

| Practice | Detail |
|---|---|
| **Aggregate all logs** | Capture the **maximum data** and transfer it to **log analytics** or a **SIEM** (security information and event management) system → a database of valuable information to access and analyze **on demand** (p31) |
| **Capture appropriate data** | Key to successful log analytics = a large library of **actionable insights**; ask the five questions below (p31–32) |
| **Control log collection and distribution frequency** | Frequency **impacts server resource utilization** → must be configured/controlled so **application performance is not disturbed** (p31–32) |
| **Ensure system scalability** | Log analytics and management capabilities must **scale according to the log data stored** (p31) |

_(Mod 12 p31–32)_

**Why aggregation matters** — modern log management solutions possess high granularity and
complexity; these features let organizations determine the **root cause of potential anomalies from
logs that were never captured**. _(Mod 12 p31)_

**Keep applications safe** _(Mod 12 p32)_ — log collection and management must not ruin the monitoring
application (legacy-based or virtual); continuous-monitoring needs can bury application
resources, so the frequency parameters must be appropriately configured.

**System scalability** _(Mod 12 p32)_ — a problematic system generates **more data than usual**, producing
**bursts in the log data**; log data volume grows with the organization or with application
demand, so analytics/management must scale accordingly.

### The questions a log must let you ask _(Mod 12 p31–32)_

1. **Who** is accessing the network?
2. **What assets** are they accessing?
3. **From where** are they accessing the asset?
4. **When** are they doing this?
5. Are there **established permissions** to allow their activity?

## Compliance _(Mod 12 p33)_

- A clear understanding of the requirements of an organization and **how compliance is achieved**
  enables **business agility and growth**. _(Mod 12 p33)_
- **Compliance failure can lead to:** regulatory fines · lawsuits · cyber security incidents ·
  reputational damage. _(Mod 12 p33)_

### Compliance considerations when integrating with CSPs

| # | Consideration |
|---|---|
| 1 | **Know the requirements that impact the organization** — based on the **jurisdiction** of the organization, its **industry**, or the **activities** it employs to conduct business |
| 2 | **Conduct regular compliance risk assessments** — establishes the foundation of a strong compliance program and lets the organization **adopt updated and revised risk assessment processes regularly** |
| 3 | **Monitor and audit the compliance program before a crisis hits** — proactively finds **gaps** and improves the compliance position |

_(Mod 12 p33)_

Exam cross-refs: [[Question-Bank]] · [[Exam-Facts]]







