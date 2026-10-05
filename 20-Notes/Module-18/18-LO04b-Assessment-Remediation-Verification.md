---
type: note
module: "18"
lo: "04"
tags: [process, bestpractice, tool, mod/18]
topic: "vulnerability assessment, mitigation, remediation, verification"
exam_weight: unknown
status: done
unresolved:
  - "p53 spoofing-protection lead-in OCRs as 'Provide spoofing protection: o O' — detail omitted, URPF / IP Source Guard prose kept verbatim."
  - "p54 'Typical Actions: Patc...' truncated in OCR — remainder not reproduced."
---
[[MOC-Module-18]]

# Assessment, Remediation, Verification (§18.04)

> **LO#04: Learn to manage vulnerabilities through a vulnerability management program** _(Mod 18 p3)_
> Covers pp51–57.

## Vulnerability assessment — process _(Mod 18 p51)_

- **Process of identifying vulnerabilities** in network components, **including the OS, web applications, and web servers**.
- Identifies **category and criticality**; organization **rates, prioritizes, designs remedies**, then **measures effectiveness** of those remedies.
- **Goal:** **scanning, examining, evaluating, and reporting** vulnerabilities **to minimize levels of risk**.
- **Key element of a vulnerability management framework**; considered the **first step for enhancing IT security**.

## Reports _(Mod 18 p51)_

- Reported to **security team, auditors, and management**.
- Include **prioritization matrix for all discovered assets and vulnerabilities**.
- Include **risk summary, consolidated vulnerability list, exploit results, and network device details**.

## Benefits + steps _(Mod 18 p51)_

- Benefits: **identifying key information assets** · **deciding vulnerabilities that threaten those assets** · **providing recommendations to strengthen security posture** · **mitigating risks**.
- Steps: **classify network or system resources** → **prioritize importance of each resource** → **identify possible threat to each resource** → **identify possible measures for each threat** → **identify methods required to reduce impact of any attack**.

## Advantages + scheduling _(Mod 18 p52)_

- **Identifies known issues before attackers find and exploit**; chance to **address and avoid serious damage**.
- Assists **updating/creating detailed structure** of network; **identifies rogue machines**; **inventory of network resources** useful for tracking.
- **Blueprint of overall security posture**; **reduces liability and protects assets**.
- Identifies **issues security controls cannot identify**; **alerts security managers when attack occurs**; **additional assurance** on state of security system.
- Use **scheduled assessments** to assess **known vulnerabilities based on defined security configuration policies**.

## Mitigation vs remediation vs verification _(Mod 18 pp53–55)_

| Action | Printed definition |
|---|---|
| Mitigation | **Action taken to prevent vulnerabilities from exploitation**; reduces risk by **other actions instead of correcting** the discovered vulnerability |
| Remediation | **Process of correcting (fixing)** a discovered vulnerability |
| Verification | **Another scan after remediation to ensure the vulnerability is fixed**; assessment **closes upon verification** of successful remediation |

- Canonical mitigation example: **installing a web application firewall is a mitigation action for a discovered web application vulnerability, instead of fixing the vulnerability** _(Mod 18 p53)_.
- Mitigation is improved by **recognizing and categorizing risks in accordance with business operations**; measures **can eliminate or reduce the risk completely** _(Mod 18 p53)_.

## Mitigation types _(Mod 18 p53)_

- **Installing a WAF** to mitigate discovered web application vulnerabilities.
- **Organizing a transit access control list:** allowing **only authorized traffic** through access points / per policies and procedures.
- **Spoofing protection:**
  - `URPF` — **protects packets from spoofing**; **proper URPF mode configured before enabling**.
  - `IP Source Guard` — **prevents IP traffic on non-routed and layer 2 interfaces by classifying packets**.

## Remediation _(Mod 18 p54)_

- Steps: **confirm false positive vs real vulnerability** → **prioritized list / remediation plan to fix (e.g. applying appropriate patches)** → **remediate by executing plan steps**.
- Plan includes: **actions for fixing, mitigating, or accepting** · **mode (automatic or manual)** · **action for mitigating remaining vulnerabilities** · **justification for accepting any vulnerability**.
- **Phased remediation strategy**; ranges **host level to network level**; **deadlines per identified risk level**.
- Guidelines: **proper tools, approved before implementation**; remediation should **improve efficiency** — **automation improves functioning**.
- Action plan covers **budget, resources, priority, timing (immediate, 30 days, 6 months, future)**.

## Verification _(Mod 18 p55)_

- **Scan again after remediation** plus an **unlimited scan for all originally discovered vulnerabilities**.
- Verified fix reports **ensure compliance with security provisions**.
- Verification **must not damage/malfunction any other network device, service, or application**.

## Additional vulnerability management solutions — prose only _(Mod 18 pp56–57)_

| Product | What the prose says | Source as printed |
|---|---|---|
| Qualys Vulnerability Management | **Continuously detect and protect against attacks anytime and anywhere** | Source: www.qualys.com |
| InsightVM | **Find, prioritize, and remediate vulnerabilities**; recognized as a leader in the **Forrester Wave: Vulnerability Risk Management, Q4 2019** | Source: www.rapid7.com |
| ManageEngine Vulnerability Manager Plus | **Comprehensive scanning, assessment, remediation across all endpoints from a centralized console** | Source: www.manageengine.com |
| BeyondTrust Vulnerability Management | **Cross-platform assessment and remediation, including built-in configuration compliance, patch management, and compliance reporting** | Source: www.beyondtrust.com |
| Skybox Vulnerability Control | **Risk-based prioritization and scan-less assessment**; **removes blind spots** and shows how vulnerabilities/threats could impact the system | Source: www.skyboxsecurity.com |






