---
type: note
module: "12"
lo: "05"
tags: [tool, concept, bestpractice, mod/12, flashcard/12]
topic: "Azure monitoring, logging, compliance — Defender for Cloud, Activity Log, Network Watcher"
exam_weight: unknown
status: done
unresolved:
  - "pp239-240 NO retention period, retention tier, archive/routing destination or export destination is printed for the Activity Log. The only export artefact is a 'Download CSV' control visible in the Fig 12.165 screenshot, plus an unreadable 'Diagnostics setings' label — neither is a printed instruction. Nothing is asserted about retention or export."
  - "p235 the slide blurb prints the NSG flow log type as 'JSON format, shows outbound and inbound logs' while the body prints 'JSON format, shows outbound and inbound flows on a per-rule basis'. The body reading is used; the slide wording is garbled."
  - "p242 the Network Watcher feature is printed as 'IP Flow Verifies'. Kept verbatim; the intended product name (IP flow verification / IP flow logs) is not asserted."
  - "pp241-242 NO configuration or enablement walkthrough for Network Watcher is printed — only the feature descriptions. Fig 12.166 dashboard counters ('Out of 36 Active ports', 'Malicious flows 2.87k', 'DCS 1/7', 'Total flows 1015614', 'TotS Active countries') are screenshot-only and garbled; not asserted."
  - "pp236-237 Microsoft Defender for Cloud is described with a 3-function model and 4 feature paragraphs, but no portal walkthrough, no pricing/tier name and no enablement step is printed in this range. Fig 12.162's screenshot source line is 'Source: https://azure.microsoft.com'."
  - "pp235-242 no metric name, alert threshold, sampling rule or diagnostic-setting configuration value is printed anywhere in this range."
---

[[MOC-Module-12]]

# Azure Monitoring, Logging & Compliance (§12.05)

> Covers pp. 235–242: customizable auditing/logging + Table 12.4 (p235) · Microsoft Defender for
> Cloud (pp236–237) · Azure management portal monitoring (p238) · Activity Log (pp239–240) ·
> Network Watcher (pp241–242). Related: `[[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]`,
> `[[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]`.

## Monitoring, logging, compliance — the one-line promise _(Mod 12 p235)_

- "Azure provides **customizable security auditing and logging features** that can help in
  **identifying gaps in the implemented security controls**."

## Table 12.4 — Types of Logs _(Mod 12 p235, eight categories as printed)_

| # | Log category | Log type | Usage |
|---|---|---|---|
| 1 | **Activity logs** | "**Control-plane events** on Azure Resource Manager resources" | "Helps in understanding the **operations that were performed on the resources in the subscription**" |
| 2 | **Azure Resource logs** | "Frequent data about the **operation of Azure Resource Manager resources** in subscription" | "Helps in understanding the **operations performed by a resource**" |
| 3 | **Azure Active Directory reporting** | "**Logs and reports**" | "Reports the **user sign-in activities** and **system activity information regarding the users and group management**" |
| 4 | **Virtual machines and cloud services** | "**Windows Event Log service and Linux Syslog**" | "Takes **system data and logging data on the virtual machines** and transfers them to a **storage account**" |
| 5 | **Azure Storage Analytics** | "**Storage logging**, provides **metrics data for storage accounts**" | "Helps in understanding the **trace requests**, analyzes **usage trends**, and **diagnoses issues** with the storage account |
| 6 | **Network security group (NSG) flow logs** | "**JSON format**, shows **outbound and inbound flows on a per-rule basis**" | "Shows information about **ingress and egress IP traffic through a Network Security Group**" |
| 7 | **Application insight** | "**Logs, exceptions, and custom diagnostics**" | "Allows **application performance monitoring (APM)** services for web developers on multiple platforms" |
| 8 | **Process data / security alerts** | "**Microsoft Defender for Cloud alerts, Azure Monitor logs alerts**" | "Enables **security information and alerts**" |

Mnemonic: control-plane first (Activity), then per-resource, then identity, then host, then storage,
then network flow, then app, then alerts.

## Microsoft Defender for Cloud _(Mod 12 pp236–237)_

- "A solution for **cloud security posture management (CSPM)** and **cloud workload protection
  (CWP)**."
- "It helps in **improving the overall security and finding weak spots across the cloud
  configuration**."
- "It protects workloads across **multi-cloud (AWS and GCP), Azure, and on-premises** environments
  from evolving threats."

**Three main functions** _(p236)_

| Function | Printed text |
|---|---|
| **Continuously Assess** | "**Know security posture.** Identify and track vulnerabilities" |
| **Secure** | "Secure resources and services with **Azure Security Benchmark** and **AWS Security Best Practices** standard" |
| **Defend** | "Identify and resolve **threats to resources and services**" |

**Features offered** _(p237, four paragraphs as printed)_

1. **Assessment of vulnerabilities for SQL resources, container registries, and virtual machines** —
   "Vulnerability assessment solutions can help in **discovering, managing, and resolving
   vulnerabilities**, which can be **viewed, checked, and repaired inside Defender for Cloud**."
2. **Threat protection alerts** — "**Microsoft Intelligent Security Graph** and **advanced
   behavioral analytics** … Attacks and **zero-day exploits can be identified using integrated
   behavioral analytics and machine learning**." Watches incoming assaults and **post-breach
   activities** on networks, devices, data storage (SQL servers hosted within and outside Azure,
   Azure SQL databases, Azure SQL Managed Instance, and Azure Storage) and cloud services.
3. **Monitor adherence to various standards** — "Defender for Cloud **continuously assesses hybrid
   cloud environments to analyze risk factors according to the controls and best practices of the
   Microsoft cloud security benchmark**"; additional industry standards, legal benchmarks and
   industry standards can be added and monitored "from the **regulatory compliance dashboard**".
4. **Application and access controls** — "**Malware and other unwanted applications can be blocked**
   by implementing **machine learning-powered recommendations** adapted to specific workloads to
   create **allowlists and blocklists**."

## Azure Monitoring: management portal _(Mod 12 p238)_

- "The Azure portal can be used to **track the performance and health of the five key statistics
  of a VM**."

| # | Statistic (as printed) |
|---|---|
| 1 | **CPU percentage** |
| 2 | **Disk Read Bytes/s** |
| 3 | **Disk Write Bytes/s** |
| 4 | **Network in** |
| 5 | **Network out** |

**Walkthrough** _(p238)_: "Login to the Azure Management Portal" → "Click on **Virtual machine**" →
"**Select the virtual machine**" → "**Select Monitor** from the top menu".

## Azure Monitoring: Activity Log _(Mod 12 pp239–240)_

- "Azure Activity Log provides **insights regarding the subscription-level events** that occur in
  Microsoft Azure. It is used to **collect, view, and analyze the activity log**."
- Slide _(p239)_: "Use the Activity Log to **collect, view, and analyze activity logs**".

**Filter fields for activity log events — all ten as printed** _(p239)_

| # | Field | # | Field |
|---|---|---|---|
| 1 | **Timespan** | 6 | **Resource type** |
| 2 | **Category** | 7 | **Operation name** |
| 3 | **Subscription** | 8 | **Severity** |
| 4 | **Resource group** | 9 | **Event initiated by** |
| 5 | **Resource (name)** | 10 | **Open search** |

**Walkthrough** _(p240)_

1. "From the Azure homepage, navigate to **Monitor**." _(Fig 12.164)_
2. "Navigate to **Activity Log**, type the name of the field in the search box (**operation
   name**), and enter to view the activity log." _(Fig 12.165)_

Visible in the Fig 12.165 screenshot only (not printed steps): `Add columns`, `Refresh`, `Diagnostics
setings` (label garbled), `Download CSV`, `Pin filters`, and the log-type tabs `Activity log` ·
`Alerts` · `Metrics` · `Logs` · `Workbooks` · `Applications (preview)` · `Services (preview)` ·
`Cosmos DB (preview)`. Example rows read `Update SQL database` with status `Succeeded` / `Started`.
**Retention and export: nothing is printed** — see `unresolved:`.

## Network Watcher _(Mod 12 pp241–242)_

- "Network Watcher is an **Azure regional service** that helps in **monitoring and diagnosing
  problems associated with Azure at a network level**."
- "It contains **network diagnostic and visualization tools** that help to **understand, diagnose,
  and obtain visibility into the Azure network**."
- "This service helps cloud admins to **detect network vulnerabilities** and **secure cloud
  operations**."

**Operational security features — all seven, as printed** _(p242)_

| # | Feature | Printed description |
|---|---|---|
| 1 | **Audit Logs** | "These logs are available for **operations performed on all network resources in Azure**. Audit logs **log operations performed as a part of network configuration**." |
| 2 | **IP Flow Verifies** | "Checks if a packet is **denied or allowed according to flow information 5-tuple packet parameters** (Source IP, Destination IP, Protocol, Source Port, and Destination Port)." |
| 3 | **Next Hop** | "Helps to **diagnose misconfigured user-defined routes** by **determining the next hop** for routed packets in **Azure Network Fabric**." |
| 4 | **Security Group View** | "Provides information regarding **security rules that are effective and applied on a VM**." |
| 5 | **NSG Flow Logging** | "Helps in **capturing traffic logs that are denied or allowed by the security rules** in a group." |
| 6 | **Remote Network Monitoring** | "Enables the **automation of remote network monitoring via packet capture** to **detect networking issues without logging into VMs**." |
| 7 | **VPN Connectivity Issues** | "Helps in **diagnosing common VPN gateway and connectivity issues**. It facilitates the **detection of issues and investigates them via logs**." |

## Exam hooks

- Activity Log = **subscription-level** events → the control-plane audit trail; filterable by
  `Operation name`.
- Network Watcher = **regional**, network-level; `IP Flow Verifies` = the **5-tuple**
  (Src IP · Dst IP · Protocol · Src Port · Dst Port).
- Defender for Cloud = **CSPM + CWP**, **assess → secure → defend**, spanning **multi-cloud
  (AWS/GCP) + Azure + on-premises**.

## Cards

What does the Azure Activity Log give you, and what is it scoped to?
?
Insights into subscription-level events — it is used to collect, view and analyze the activity log

Name the Activity Log filter fields printed on p239
?
Timespan · Category · Subscription · Resource group · Resource (name) · Resource type · Operation name · Severity · Event initiated by · Open search

The five VM statistics the Azure portal is said to track
?
CPU percentage · Disk Read Bytes/s · Disk Write Bytes/s · Network in · Network out

What is Microsoft Defender for Cloud, in the courseware's own framing?
?
A cloud security posture management (CSPM) and cloud workload protection (CWP) solution that continuously assesses, secures and defends workloads across multi-cloud (AWS and GCP), Azure and on-premises

Name the seven Network Watcher operational security features
?
Audit Logs · IP Flow Verifies · Next Hop · Security Group View · NSG Flow Logging · Remote Network Monitoring · VPN Connectivity Issues

What 5-tuple does IP Flow Verifies check, and what is it for?
?
Source IP, Destination IP, Protocol, Source Port and Destination Port — to check if a packet is denied or allowed according to flow information
