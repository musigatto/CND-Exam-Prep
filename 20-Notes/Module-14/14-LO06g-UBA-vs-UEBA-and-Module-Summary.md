---
type: note
module: "14"
lo: "06"
tags: [concept, exam, mod/14]
topic: "UBA vs UEBA differences and the Module 14 summary"
exam_weight: unknown
status: done
unresolved:
  - "p114 the Module Summary does not mention LO#06 at all. Its coverage sentence lists 'manual network traffic monitoring, types of network signatures, network traffic baselining, network monitoring tools, and detection techniques for various types of attacks' — network anomaly detection, NBA, UBA and UEBA (pp78-113) are absent. Not reconciled."
  - "p113 vs p99 CONTRADICTION, not reconciled: p113 says UBA 'relies on event logs', but p99 says UBA 'collects diverse data on a user from multiple sources and locations within the environment, which may include log files, network traffic, and application usage' and analyses 'network logs stored in SIEM and log management'."
  - "p113 vs p99 CONTRADICTION, not reconciled: p113 says UBA 'is a stand-alone and cannot integrate with existing security systems', but p99 says UBA analyses data held in SIEM and log management."
  - "p113 vs p109/p111 TENSION, not reconciled: p113 says UBA cannot integrate with existing security systems, while p109 states Securonix's UEBA 'can be quickly deployed on top of the existing SIEM without having to replace it' and p111 describes IBM Qradar SIEM applying UBA 'alongside traditional logs'."
  - "p114 the summary lists 'Wireshark is a widely used network packet analyzer for network analysis' and 'A network baseline is a description of accepted behavior for network traffic' — both consistent with the module body, but the page states them as definitions whereas the body develops them; no contradiction found."
  - "p113 the table body prints 'I-JEBA'/'IJEBA' and 'existing security systems' repeated as a stray fragment ('cannot integrate with I-JEBA … existing security systems'); rendered as UEBA in the table row 'It is a stand-alone and cannot integrate with existing security systems' per the duplicated sidebar text on the same page."
---

[[MOC-Module-14]]

# UBA vs UEBA and the Module Summary (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp113–114.

Closes the LO with the printed comparison table, then the Module 14 summary.

## Differences between UBA and UEBA _(Mod 14 p113 — Table 14.2)_

| # | **UBA** | **UEBA** |
|---|---|---|
| 1 | "It **focuses on user behavior**" | "It **focuses on user and entity behavior**" |
| 2 | "It **relies on event logs**" | "It **integrates data from multiple sources**" |
| 3 | "It can detect threats that involve **human actors or malware**" | "It can detect threats that involve **malware, human actors, or machine actors**" |
| 4 | "It provides **limited visibility into network activity**" | "It provides **more visibility into network activity and context for threat investigation and response**" |
| 5 | "It **is a stand-alone** and **cannot integrate with existing security systems**" | "It **integrates with existing security products and systems**" |

### The three-way progression of the LO

| Layer | Scope | Entry point |
|---|---|---|
| **NBA / NBAD** | network traffic | [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]] · [[14-LO06d-Network-Behaviour-Analysis-and-Its-Tools]] |
| **UBA** | users only | [[14-LO06e-User-Behaviour-Analytics-UBA-and-Its-Tools]] |
| **UEBA** | users **and entities** (routers, endpoints, servers) | [[14-LO06f-User-and-Entity-Behaviour-Analytics-UEBA-and-Its-Tools]] |

> "UBA vs UEBA" — the only point on which UEBA adds a *class of threat* UBA does not is
> **machine actors**.

### Unreconciled internal tension (p99 vs p113) — recorded, not resolved

- p113 states UBA "**relies on event logs**" and "**is a stand-alone and cannot integrate with existing
  security systems**".
- p99 states UBA "**collects diverse data on a user from multiple sources and locations** within the
  environment, which may include **log files, network traffic, and application usage**", analyses
  "**network logs stored in SIEM and log management**", and compares "the **behavior of their peers**".

Both passages are printed in the same LO. **Not reconciled here** — see `unresolved:`. Answer to the
question as the table presents it (limited data sources, no SIEM integration) is what p113 states.

## Module summary _(Mod 14 p114)_

Reproduced as printed.

"This module covered the importance of **manual network traffic monitoring**, **types of network
signatures**, **network traffic baselining**, **network monitoring tools**, and **detection techniques for
various types of attacks**. The key points discussed in this module are summarized as follows:"

- "Network traffic monitoring and signature analysis involve **capturing network packets and analyzing them to identify signs of malicious activity**."
- "Signatures are **patterns created using a set of rules that identify typical intrusive activity on a network**."
- "Signature analysis helps **differentiate legitimate traffic from suspicious traffic**."
- "**Wireshark is a widely used network packet analyzer** for network analysis."
- "**A network baseline is a description of accepted behavior for network traffic**."
- "**Network defenders should monitor the network traffic for different types of attack attempts**."

### Summary vs module body — comparison

| Summary claim | Consistent with |
|---|---|
| Capturing packets and analysing them identifies malicious activity | the whole manual-monitoring half of the module |
| Signatures = patterns from a **set of rules** identifying typical intrusive activity | signature material ([[14-LO03a-Network-Traffic-Signatures-and-Baselining]]) |
| Signature analysis **differentiates legitimate from suspicious traffic** | ditto |
| Wireshark as the widely used packet analyzer | [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]] |
| A baseline = "**description of accepted behavior**" for network traffic | [[14-LO03a-Network-Traffic-Signatures-and-Baselining]] and the baseline step in [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]] |

**Not in the summary at all:** network anomaly detection, NBAD, NBA, UBA, UEBA — i.e. **all of LO#06
(pp78–113, a third of the module)** — and the LO#05 performance/bandwidth monitoring material. The
summary's coverage sentence enumerates five topics and none of them is behaviour analytics. Recorded in
`unresolved:`; not reconciled.






