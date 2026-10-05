---
type: note
module: "14"
lo: "06"
tags: [tool, threat, process, mod/14]
topic: "NBAD tools: Awake, Cisco Secure Network Analytics, ransomware and compromised-device detection"
exam_weight: unknown
status: done
unresolved:
  - "p83 the module prints 'advanced persistent threats' in full, twice, and NEVER prints the abbreviation 'APT' or 'APTs' anywhere in the 114 pages. The expansion is therefore not used in this note — search the OCR for 'APT' and you will get zero hits. Do not add it."
  - "p83 the section heading band prints 'Cisco Security Network Analytics' while the body heading and prose print 'Cisco Secure Network Analytics'. Body spelling used; the band variant is recorded here."
  - "p82 the Awake figure band prints 'Source www.arista.com' (no scheme) and the body prints 'Source: https://www.arista.com/'. The body URL used."
  - "p85 is a single screenshot page (figure 14.29, Log360 UEBA ransomware example) with no body prose — no content extracted."
  - "p82, p83, p84, p85 figures 14.27-14.29 are product dashboards; panel labels and values not transcribed (screenshot non-evidence)."
---

[[MOC-Module-14]]

# Behaviour Detection Tools — Awake, Cisco, Ransomware, Compromised Devices (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp82–86.

Named-product continuation of [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]].
The DDoS/NetFlow Analyzer and remaining NBAD tools are in [[14-LO06c-DDoS-Detection-NetFlow-Analyzer-and-Additional-NBA-Tools]].

## Awake Security Platform _(Mod 14 p82)_

- Foundation: "**deep network analysis sensors**."
- Analyses **encrypted traffic** to identify contexts: "the **nature of the traffic**, the **applications communicating**, and the **presence of remote access**" — "thereby **detecting behavioral threats**."
- **Correlates incidents across entities, attack stages, and protocols**, "providing all the **decision-support data** necessary for a rapid response to any threat."
- Tracks entities across IoT environments "whether they are **on-premise, in the cloud, managed, or unmanaged**."

## Cisco Secure Network Analytics _(Mod 14 p83)_

> Heading band prints **"Cisco Security Network Analytics"**; the body prints **"Cisco Secure Network Analytics"** — see `unresolved:`.

- "Informs you **who is on the network and what they are doing** by utilizing **telemetry from your network infrastructure**."
- Detects advanced threats and responds swiftly; **protects critical data through intelligent network segmentation**.
- "Can gather the necessary data using the **existing network infrastructure**" — no new data source.
- Analyses **encrypted traffic** → "**detection of malware without decryption**", plus **managing the quality of network encryption**.

Analytical techniques (printed):

| Technique | Note |
|---|---|
| **Multilayered machine learning** | listed as one of "multiple analytical techniques" |
| **Global threat intelligence** | ditto |
| **Behavioural modelling** | ditto |

Detects: **malware, advanced persistent threats, insider threats, malware propagation**.

## Ransomware detection using NADBA _(Mod 14 p84)_

- Method: "**Monitor network traffic patterns and endpoint behaviors** to identify unusual patterns, such as a **sudden increase in data encryption activity**, **multiple failed login attempts**, or **unusual file access patterns**."
- "Detect ransomware by **analyzing data traffic and identifying network irregularities** … or failed login attempts and **accessing information through abnormal approaches**."
- "**Real-time detection** of these abnormalities enables **rapid countermeasures** to prevent ransomware attacks from compromising critical data."
- Automatic response on a strange pattern: **isolate the impacted endpoints**, **restrict suspect network traffic**, **alert the security team**, **inform the business hierarchy**.

### Example UEBA tool for ransomware — Log360 UEBA (ManageEngine) _(Mod 14 p84)_

- "Powered by **Machine Learning (ML)**, detects anomalies by **recognizing subtle changes in user activity**."
- "Aids in **identifying, qualifying, and investigating threats that might otherwise remain unnoticed**, by **extracting more information from logs to provide better context**."
- "Dashboard offers a **concise overview of anomalous behavior based on users and entities in the network**."
- "As it **consolidates multiple data sources into a single interface**, administrators can swiftly assess the status of their organization's security posture."

> The page introduces a **UEBA** product inside the ransomware example — see [[14-LO06f-User-and-Entity-Behaviour-Analytics-UEBA-and-Its-Tools]].

## Identifying compromised devices using NADBA _(Mod 14 p86)_

Three obligations:

1. "**Create profiles for users, devices, and entities** (e.g., **servers, IoT devices**) based on their **historical behavior**."
2. "Profiles include **normal usage patterns, access privileges, and interactions with other entities**."
3. "**Monitor for anomalies in network traffic, authentication patterns, file access**, and other activities."

Monitor for — five tells of a compromised device:

| # | Tell |
|---|---|
| 1 | **Unusual login activities** — "**logins at odd hours**, from **unusual locations**, or **multiple failed login attempts**" |
| 2 | "Devices accessing **files or resources they don't typically interact** [with]" |
| 3 | "**Unauthorized elevation of user privileges**" — prose: "unauthorized privilege escalation that could potentially lead to **root access**" |
| 4 | "Communication with **known malicious IPs or domains, or unusual data exfiltration**" — prose adds "connections with **unknown IP addresses or unknown servers**, which could be used to **distribute malware**" |
| 5 | "Unusual **file modifications**, especially **encryption or deletion**" — prose adds "**alterations in log files**, encrypting critical resources, and deleting them" |






