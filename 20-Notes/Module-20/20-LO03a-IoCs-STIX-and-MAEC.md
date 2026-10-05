---
type: note
module: "20"
lo: "03"
tags: [concept, process, mod/20]
topic: "IoCs, STIX and MAEC"
exam_weight: unknown
status: done
unresolved:
  - "p17 'OpenlOC' kept verbatim (lowercase-L rendering throughout); presumed OpenIOC but slice never prints a clean form"
  - "p18 STIX construct list spans the pp17-18 column break; 'TTPs' entry reading order reconstructed, wording verbatim"
  - "p20 figure list vs prose list differ: figure prints 'Geographical anomalies' and omits 'Login irregularities' and 'MD5 hash file in the temporary directory'; prose list followed"
  - "p15 OCR variants 'IoAs' and 'loAs' normalised to IOAs (section title 'IOCs and IOAs')"
---

[[MOC-Module-20]]

# IoCs, STIX and MAEC (§20.03)

> **LO#03: Understand IoCs and IOAs** _(Mod 20 p15)_
> Covers pp15–20. Sibling: [[20-LO03b-IOAs-and-IOC-vs-IOA]].

- Section scope: analysing **IOAs + IOCs** lets defenders understand **past events** and the **"how" and "why" of current events**; the IOC/IOA difference matters for **building a TI program**; section covers IOCs and IOAs, advantages, examples, and differences _(Mod 20 p15)_

## IOC definition and limits

- **IOCs = clues / artifacts / evidence** of potential intrusion or malicious activity; **technical indicators**, **digital footprints** of threats/adversaries _(Mod 20 p16)_
- Found in **system files / log entries**; spotted via real-time tracking, proactive monitoring, severity assessment (printed example: unauthorised database-access breach → preventive measures vs repeats) _(Mod 20 p16)_
- Discovered **after an incident via investigation** or **via alerts during monitoring**; gathered and consumed to improve defence against **similar** threats _(Mod 20 p16)_
- **Anti-malware systems and threat intelligence platforms** use IOCs to spot and stop activity at an initial stage _(Mod 20 p16)_
- Printed IOC examples (prose): specific **registry entries**, **C&C domain names**, **malware file hashes**, **virus signatures**, **IP addresses** _(Mod 20 p16)_
- Limit (also the printed disadvantage): prevent **repeated / unchanged / persistent** threats; **may not detect new or modified** threats _(Mod 20 pp16–17)_
- Documenting IOCs + associated threats enables **sharing** and enhances **IR** → **standardise documentation and reporting** _(Mod 20 p17)_

## IOC advantages (p16)

- Perform **complete forensic analysis**; analyse attempts via critical TI _(Mod 20 p16)_
- Identify incidents **overlooked by other tools**; recurring IOCs feed **policy/tool updates** vs future attacks _(Mod 20 p16)_

## IoC formats: OpenIOC, CybOX, STIX, TAXII, MAEC

- Common formats record/define/share threat info internally + externally in **machine-digestible** form _(Mod 20 p17)_

| Format | Printed role |
|---|---|
| `OpenlOC` [sic] | XML-based framework describing **complex semantics of malware behavior**; **500+ indicator terms**, mostly starting `file / driver / disk / system / process / registry` (e.g. file name, file MD5 hash); stored as **XML schema** _(Mod 20 p17)_ |
| CybOX | Cyber Observable Expression; standard for **observables** (measurable events, stateful properties); **70+ defined objects**; automates sharing; uses: acquire TI, log management, malware characterisation, IR, forensic investigation _(Mod 20 p17)_ |
| STIX | Structured Threat Information Expression; defines **threat details + context** in XML; see constructs + uses below _(Mod 20 pp17–18)_ |
| TAXII | Trusted Automated Exchange of Indicator Information; exchange specs over **HTTPS**; **XML contents + HTTP transport**; built to exchange **STIX** CTI; 3 models below _(Mod 20 p18)_ |
| MAEC | Malware Attribute Enumeration and Characterization; standardised CTI language; 3 output formats + vocabularies below _(Mod 20 pp18–19)_ |

- `OpenlOC` advantages: XML readable by **machine and human** (forensic reports); **reliability + repeatability** via standard syntax; derived indicators feed **security-tool monitoring/detection** and **control/policy configuration** _(Mod 20 p17)_
- STIX data elements (threat-related constructs): **Observables; Cyber-attack campaigns; Exploit targets; Incidents; Indicators; Threat actors; TTPs** = adversary tactics, techniques, procedures (attack patterns, exploits, tools, infrastructure) _(Mod 20 pp17–18)_
- STIX language uses: **identify/analyse threats** (review structured + unstructured info); **specify indicator patterns** (measurable patterns); **manage response** (prevent, detect, investigate, respond); **define + share** threat information _(Mod 20 p18)_
- TAXII sharing models: **Hub and spoke** (one repository); **Source/subscriber** (single source); **Peer to peer** (multiple groups sharing) — Fig 20.1 _(Mod 20 p18)_
- MAEC tiers (Fig 20.2): **Bundle (Tier 1)** = data from analysis of a **single malware instance**; **Package (Tier 2)** = **one or more malware subjects** incl instance detail + analysis-derived data + metadata; **Container (Tier 3)** = collection incl **one or more packages**; **default vocabularies** = default controlled vocabularies _(Mod 20 pp18–19)_

## Printed IOC examples (prose list, p2716)

1. Unusual outbound network traffic
2. Unusual activity through a privileged user account
3. Geographic irregularities
4. Multiple login failures
5. Login irregularities
6. Increase in database read volume
7. Large HTML response size
8. Multiple requests for the same file
9. Mismatched port—application traffic
10. Suspicious registry or system file changes
11. Unusual DNS requests
12. Unexpected patching of systems
13. Signs of DDoS activity
14. Bundles of data at incorrect locations
15. Web traffic with superhuman behavior
16. MD5 hash file in the temporary directory _(Mod 20 p20)_






