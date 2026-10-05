---
type: note
module: "14"
lo: "05"
tags: [concept, tool, process, bestpractice, mod/14]
topic: "Bandwidth monitoring and best practices"
exam_weight: unknown
status: done
unresolved:
  - "p74 The two printed definitions of bandwidth differ. Side bar: 'the amount of information that can be transmitted over a network in a given amount of time'. Body prose: 'the amount data that can be transferred from one point to another' — printed without a word between 'amount' and 'data'. Both quoted verbatim; neither corrected."
  - "p74 vs p75 The p74 side bar names the tool 'SolarWinds Bandwidth Monitor'; the product heading on p75 is 'SolarWinds Real-Time Bandwidth Monitor'. Both names printed as-is."
  - "p77 The heading of the three-item list reads 'rules to increase bandwidth usage in their environment', although the items listed (limiting media sites, proxy cache, QoS) act on consumption/reservation rather than raising raw usage. Printed wording kept."
  - "p77 The last best practice reads 'these backups act as a good configuration and keep the bandwidth stable' — printed as-is."
---

[[MOC-Module-14]]

# Bandwidth Monitoring and Best Practices (§14.05)

> **LO#05: Discuss network performance and bandwidth monitoring concepts** _(Mod 14 p71)_
> Covers pp74–77. Performance side of the same LO: [[14-LO05a-Network-Performance-Monitoring]].

## Bandwidth — the two definitions the pages print

| Where | Verbatim |
|---|---|
| p74 side-bar bullet | "Bandwidth is **the amount of information that can be transmitted over a network in a given amount of time**" |
| p74 body prose | "The bandwidth is **the amount data that can be transferred from one point to another**. It is **one of the criteria defining network performance**." |

Both from _(Mod 14 p74)_; the two do not match word-for-word — see `unresolved:`.

## Bandwidth terms as printed

| Term | Courseware wording |
|---|---|
| **Effective bandwidth** | "one that provides the **highest transmission rate**" _(Mod 14 p74)_ |
| **Bandwidth monitoring test** | "identifies the **maximum throughput of a system**" _(Mod 14 p74)_ |
| **Bandwidth monitoring** | "**measuring and controlling** the traffic on a network link to **avoid the overfilling of the link**" _(Mod 14 p74)_ |
| **Bandwidth capacity** | "the **maximum data transfer rate of a link**" _(Mod 14 p75)_ |

- "Network bandwidth selection plays a vital role in the **design, maintenance, and performance** of
  an organization's network." _(Mod 14 p74)_
- "**Poor bandwidth management** leads to **network congestion** and poor performance of the
  network." _(Mod 14 p74)_
- "**A low detected bandwidth indicates poor network functioning.**" _(Mod 14 p75)_
- "Bandwidth monitoring includes the monitoring of **various bandwidth utilizations** that are
  implemented in the organization." _(Mod 14 p75)_

### Two bandwidth speed types

"An organization works on **two types of bandwidth speed: upload and download**." _(Mod 14 p75)_

| Term | Exact wording |
|---|---|
| **Upload speed** | "the speed at which data are **sent to a destination**" _(Mod 14 p75)_ |
| **Download speed** | "the speed at which data are **received**" _(Mod 14 p75)_ |

"With growing networks and huge volumes of data, organizations have started to **maximize their
upload and download speeds**." _(Mod 14 p75)_

### The two levels bandwidth tools report on

> "The tools provide bandwidth information at the **interface and device levels**." _(Mod 14 p75)_

Both levels are spelled out for ManageEngine Bandwidth Monitor _(Mod 14 pp75–76)_:

| Level | What is reported at that level |
|---|---|
| **Interface level** | "the bandwidth utilization details of a **network interface**" — "It uses SNMP to fetch the bandwidth utilization details of a network interface." _(Mod 14 p76)_ |
| **Device level** | "a comparison of the **individual traffic and its interfaces**" _(Mod 14 p76)_ |

## Factors for measuring bandwidth

_(Mod 14 p74)_
- Determine the amount of **available** network bandwidth.
- Determine the **average utilization required by a specific application**.

### CND callout — considerations to **decrease** the bandwidth requirements

_(Mod 14 p74)_
Server-side computing · **Data caching** · **Data compression** · **Latency mitigation** ·
**Loss mitigation**

## Planning the figure

- "With hundreds of users in a network, it is important to know the **bandwidth required per
  day**." _(Mod 14 p75)_
- "Although it can be a tedious job for administrators to determine the bandwidth usage per day, a
  **blueprint of the usage** can help draft a proper bandwidth monitoring plan." _(Mod 14 p75)_
  → compare [[14-LO03a-Network-Traffic-Signatures-and-Baselining]]

## Benefits of bandwidth monitoring

_(Mod 14 p75)_

1. "Bandwidth monitoring helps **determine the network utilization** of the system."
2. "Systems using high bandwidth amounts should be **monitored closely** as they **may be
   performing suspicious activities** or **may have become a victim of suspicious activity**."
   → [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]]
3. "**High amounts of network traffic** lead to **network congestion** and affect the functioning of
   the organization."
4. "Deploying a **network limit** will raise an **alarm** when the network is about to **reach the
   maximum bandwidth**."
5. "If the network congestion is high, depending on the size of the organization, **additional links
   can be added** to the network."
6. "An **additional link** in the network will **boost the network performance**, reducing the
   network congestion."

## Bandwidth-monitoring tools named

| Tool | What the courseware says it does |
|---|---|
| **PRTG Bandwidth Monitor** | "analyzes the traffic in a network and provides **detailed results including tables and graphs**. It monitors network devices, bandwidth, servers, applications, virtual environments, remote systems, IoT, and many more." _(Mod 14 p75)_ |
| **SolarWinds Real-Time Bandwidth Monitor** | "**critical and warning thresholds** can be set so that the administrator is **instantly notified when usage is out of bounds**." _(Mod 14 p75)_ |
| **ManageEngine Bandwidth Monitor** | "shows the **real-time network traffic of any SNMP device**. It provides bandwidth usage details on **both interface and device levels**. It uses SNMP to fetch the bandwidth utilization details of a network interface. The details on the bandwidth utilization of a device includes a **comparison of the individual traffic and its interfaces**." _(Mod 14 pp75–76)_ |
| **tbbMeter** | "a **bandwidth meter that monitors Internet usage**. It shows **how much data a computer sends to and receives from the Internet in real time**. It also shows **how the Internet usage varies at different times of the day**." _(Mod 14 p76)_ |
| **BandwidthD** | "monitors the amount of data being **received/transmitted by specific machines and/or subnets**. It **tracks the usage of TCP/IP network subnets** and **builds HTML files with graphs** to display utilization." _(Mod 14 p76)_ |
| **NetWorx** | "monitors **all the network connections or a specific network connection** such as **wireless or mobile broadband**. The incoming and outgoing traffic is represented on a **line chart** and **logged into a file** such that the statistics about the **daily, weekly, and monthly bandwidth usage and dial-up duration** can always be viewed. The reports can be exported to a variety of formats such as **HTML, Microsoft Word, and Microsoft Excel**." _(Mod 14 p76)_ |

> **Non-evidence:** pp.75–76 are product screenshots captioned "Source: https://…" / "Source: http://…".
> No dashboard, graph, interface list, threshold value or window content was read from them — only the
> readable running body prose under each heading.

## Bandwidth Monitoring: Best Practices (p77)

### A. Best practices for current and future bandwidth needs

_(Mod 14 p77)_

| # | Practice, verbatim |
|---|---|
| 1 | "It is recommended to use **only a single bandwidth monitoring tool** to assess the current utilization of bandwidth for the organization" |
| 2 | "**Define and categorize** the bandwidth need based on the **application, user, user groups, time period**, etc." |
| 3 | "Calculate the **total number of nodes** that contribute to the overall bandwidth requirement including **workstations, shared printers, and servers**" |
| 4 | "Calculate the **average bandwidth required per node**" |
| 5 | "Always consider **peak bandwidth requirements** for the organization" |
| 6 | "**Determine, assess, and list the type of application** that should be used within a specific time period and **how much bandwidth it will consume**" |
| 7 | "**Check with the Internet service provider (ISP)** as to whether they allow **provisions for growth** in bandwidth requirements" |

### B. Rules "to increase bandwidth usage in their environment"

"The rules below **depend on the size and requirement of the organization**." _(Mod 14 p77)_

| Rule | Courseware explanation |
|---|---|
| **Limited use of media sites** | "limit their employees' access to media services such as **online gaming, movies, and music**. This will **enhance the upload as well as download speed** of the overall network." _(Mod 14 p77)_ |
| **Proxy cache** | "When a user visits a website for the first time, the content of the site is **saved (cached) on the proxy server**. If the user visits the same website again, the content **does not have to be downloaded again**." _(Mod 14 p77)_ |
| **QoS** | "**Quality of service (QoS) is a bandwidth reservation mechanism.** Since certain applications require additional bandwidth, administrators can **configure the QoS for these applications**. Consequently, if a user accesses these applications in the future, the QoS bandwidth will be utilized. **Utilizing the QoS bandwidth will not affect the bandwidth usage for other users in the network.**" _(Mod 14 p77)_ |

### C. Additional best practices for **effective bandwidth monitoring**

"In addition to above bandwidth usage recommendations, the following best practices can also be
helpful in effective bandwidth monitoring:" _(Mod 14 p77)_

1. "Provide **timely education or training** to employees on excessive bandwidth consumption to
   **create awareness** among them concerning bandwidth usage."
2. "**Monitor the traffic** consumed by the **network components** in the organization."
3. "**Implement a QoS policy** to **prioritize bandwidth usage** as per application requirements."
4. "**Optimize the WAN capacity** to increase the network bandwidth."
5. "**Backup the devices** configured on the network. During a power failure or network failure,
   these backups act as a good configuration and **keep the bandwidth stable**."







