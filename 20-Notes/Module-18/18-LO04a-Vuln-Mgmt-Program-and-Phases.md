---
type: note
module: "18"
lo: "04"
tags: [process, tool, mod/18]
topic: "vulnerability management program, phases, discovery, prioritization"
exam_weight: unknown
status: done
unresolved:
  - "p45 phase-figure reading order garbled in OCR; phase set taken from prose pp45-47 and p49, Discovery stated first on p47."
  - "p45 final sentence truncated (Some of the mo...); omitted."
  - "p47-48 discovery prose truncated at Page 2605 boundary; cloud/IP-device fragment on p48 treated as non-evidence dashboard context."
---
[[MOC-Module-18]]

# Vulnerability Management Program and Phases (§18.04a)

> **LO#04: Learn to manage vulnerabilities through vulnerability management program** _(Mod 18 p43)_
> Covers pp43–50. Dashboard captures on pp48–50 are non-evidence; only prose is recorded.

## Program requirement

- Risk management frameworks require organizations to **maintain a vulnerability management program**. _(Mod 18 p44)_
- Source: `http://www.tripwire.com` _(Mod 18 p44)_
- Vulnerability management is a **continuous information security risk process** including **identifying, assessing, classifying, remediating, and mitigating vulnerabilities**. _(Mod 18 p45)_
- Well-planned and implemented process plays a vital role in organizational risk management; provides a **comprehensive approach toward mitigating risks** on system and network. _(Mod 18 p45)_
- It is a **superset of the vulnerability assessment process**; vulnerability assessment is a part of vulnerability management. _(Mod 18 p45)_
- Scanning (e.g. scanning networks, systems, applications with a scanner) is only identification; management adds **risk acceptance and remediation**, among others. _(Mod 18 p45)_
- Organization maintains the program with solutions such as **AlienVault OSSIM, Qualys VM**. _(Mod 18 p45)_

## Program phases

- Phase set named in prose/figure: **Discovery, Asset Prioritization, Assessment, Reporting, Remediation, Verification**. _(Mod 18 pp45–46)_
- Discovery is stated as the **first phase**. _(Mod 18 p47)_
- Assessment (Scanning): **scan and evaluate a system for vulnerabilities**. _(Mod 18 p46)_
- Reporting (Technical and Executive): **report results** for the different vulnerability management processes. _(Mod 18 p46)_
- Remediation (Treating Risks): **reduce the risks and remove the root cause**. _(Mod 18 p46)_
- Verification (Rescanning): **monitor network continuously** to check for new vulnerabilities. _(Mod 18 p46)_

## Discovery: identify assets and components

- Identifying assets and components is the first phase; inventory detailing **inactive and active assets** and network components should include **physical and logical elements** of the information infrastructure. _(Mod 18 p47)_
- Assets include hardware devices such as **servers, internal applications, software licenses**. _(Mod 18 p47)_
- Discovery record per element: **location, business processes, data classification, identified threats, risks**. _(Mod 18 p47)_
- Better asset knowledge gives a clear picture of **relationship between assets and network components**. _(Mod 18 p47)_
- Functions: **identifies all hosts including rogue devices** and assigns host per business needs; **graphical representation** of hosts; **risk-based ranking** of remedial efforts; **identifies services and ports** on each device; **selects preferred hosts** for scanning or reporting; provides a **hacker's view** of the network. _(Mod 18 p47)_
- Use **automated network discovery tools**; automated scheduled vulnerability checks; SIEM can automatically discover all attached assets; example **AlienVault OSSIM Asset Discovery**. _(Mod 18 p47)_

## Asset prioritization: evaluate importance

- All assets do not have the same significance; classify per business needs to identify **high business risks**. _(Mod 18 p49)_
- Prioritize based on **impact of failure** and **reliability in the business**. _(Mod 18 p49)_
- Prioritization helps: **customized first/second/third list**; identify most critical assets; identify value per asset; evaluate and decide a solution for the consequence of assets failing; examine risk tolerance level; organize prioritization methods. _(Mod 18 p49)_
- Correlate **asset value + accessible information** with possible vulnerabilities; club each **asset–vulnerability pair with a known threat**; the three values show which assets and risks to prioritize. _(Mod 18 p49)_
- Example: AlienVault USM Appliance asset value **0 to 5**, where **0 least importance, 5 most important**. _(Mod 18 p49)_

Non-evidence treated as layout only: Figure 18.1 OSSIM Asset Discovery (p48) and Figure 18.2 OSSIM Asset Prioritization (p50) dashboard captures; no tile labels, numbers, or sidebar entries read. _(Mod 18 pp48–50)_

See also [[MOC-Module-16]] for incident response where unmanaged vulnerabilities materialize.





