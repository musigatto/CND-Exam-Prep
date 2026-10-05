---
type: note
module: "17"
lo: "04"
tags: [process, tool, mod/17]
topic: "BC/DR standards and module summary"
exam_weight: unknown
status: done
unresolved:
  - "p29 tile prints Source as https with a garbled separator; used the clean p29 prose form https://www.iso.org"
  - "p31 tile prints a garbled source line reading Snurcp wwwq nra.or; no clean prose Source line visible in slice so no FINRA URL recorded"
  - "p33 heading OCRs the ASIS identifier as ORM. 1.201 with odd spacing; quoted as printed"
  - "p34 figure tiles show bare layout numbers 2 3 4 7 next to standard names; treated as non-evidence, titles taken from prose list"
  - "p34-35 prose lines truncated at 2000 chars: ISO Guide 73 description and contingency-planning guidance cut off; kept to printed titles only there"
  - "p36 tile vs prose wording differs (tile: DR is data-centric; prose: recovery is data-centric; tile: BR and DC; prose: DR and BC); quoted the prose form"
---
[[MOC-Module-17]]

# BC/DR Standards and Module Summary (§17.04)

> **LO#04: Discuss BC/DR Standards** _(Mod 17 pp27–36)_
> Objective as printed: to discuss the various standards related to BC/DR including the **ISO 22301:2019**, the **ISO 22313:2012**, and the **ISO/IEC 27031:2011**. _(Mod 17 p27)_

## ISO 22301:2019 — Security and Resilience — Business Continuity Management Systems (BCMS) — Requirements

- Specifies requirements to **implement, maintain, and improve a management system** to **protect against, reduce likelihood of, prepare for, respond to and recover from disruptions**. Applies **regardless of size, industry, or nature**. _(Mod 17 p28)_
- Requirements are **generic**, applicable to **all organizations or parts thereof**; extent depends on **operating environment and complexity**. _(Mod 17 p28)_
- Applies to organizations that: implement/maintain/improve a BCMS; seek conformity with stated BC policy; aim to **deliver products and services continually at acceptable predefined capacity** during disruption; seek to **enhance resilience** through effective BCMS application. Can assess ability to meet own BC needs and obligations. _(Mod 17 p28)_
- Source: `https://www.iso.org` _(Mod 17 p28)_

## ISO 22313:2012 — Societal Security — BCMS — Guidance

- **Guides ISO 22301** for setting up and managing an effective BCMS; guidance based on **good international practices** for **planning, establishing, implementing, operating, monitoring, reviewing, maintaining, and continually improving** a documented management system to **prepare for, respond to and recover from disruptive incidents**. _(Mod 17 p29)_
- **Not intended to imply uniformity** in BCMS structure; design a BCMS **appropriate to needs**, shaped by legal, regulatory, organizational, industry, product/service, process, environment, size, structure, and interested-party requirements. _(Mod 17 p29)_
- Source: `https://www.iso.org` _(Mod 17 p29)_

## ISO/IEC 27031:2011 — Information Technology — Security Techniques — Guidelines for Information and Communication Technology Readiness for Business Continuity

- Describes **concepts and principles of ICT readiness for business continuity**; framework of methods and processes to identify and specify all aspects (performance criteria, design, implementation) for improving ICT readiness. _(Mod 17 p30)_
- Applies to **any organization** (private, governmental, non-governmental, irrespective of size) developing its **ICT readiness for business continuity (IRBC)** program, requiring ICT services/infrastructures ready to support business operations amid emerging events, incidents, and disruptions affecting continuity (including security) of critical business functions. _(Mod 17 p30)_
- Source: `https://www.iso.org` _(Mod 17 p30)_

## FINRA Rule 4370 — Business Continuity Plans and Emergency Contact Information

- **FINRA = government-authorized, not-for-profit** organization establishing rules to ensure integrity. _(Mod 17 p31)_
- Each member must **create and maintain a written BCP** with procedures for **emergency or significant business disruption**, reasonably designed so the firm continues business operations; firm answerable for letting clients know how it continues. _(Mod 17 pp31–32)_
- Plan **customized per organization** but must contain topics such as **data backup and recovery, alternate communications**; also covers **alternate physical location of employees; critical business constituent, bank, counter-party impact; regulatory reporting; communications with regulators**; how member assures **customers prompt access to funds and securities** if it cannot continue business. _(Mod 17 pp31–32)_
- **Senior management member (registered principal)** approves plan, responsible for **annual review**; update on change of location, structure, or operations; meet to discuss changes. _(Mod 17 pp31–32)_
- **Disclosure in writing**: to customers at account opening, posted on website if maintained, mailed on request — how the plan addresses future significant disruption and varying scopes. _(Mod 17 p32)_
- **Emergency contact info reported to FINRA**: **two associated persons**, at least one a senior-management registered principal; second either registered or senior management with business-operations knowledge; single-person member designates knowledgeable outsider (e.g. attorney, accountant, clearing contact); update promptly. _(Mod 17 p32)_
- **Mission-critical system** necessary for accurate processing of business transactions, including all logs of securities transactions. _(Mod 17 p31)_

## ASIS ORM.1 (as printed ORM. 1.201) — Security and Resilience in Organizations and Their Supply Chains

- Standard: **integrated, comprehensive, systematic risk-based approach** to manage risks; enhance **sustainability, survivability, resilience** of organization and supply chain; pursue improvement opportunities. _(Mod 17 p33)_
- Emphasizes **proactive risk and business management**: prevention, protection, preparedness, readiness, mitigation, response, continuity, recovery. _(Mod 17 p33)_
- **ASIS = volunteer, nonprofit professional society** with **no regulatory, licensing, or enforcement power**; does not enforce compliance, does not list/certify/test/inspect/approve practices or products; undertakes no duty to third parties. _(Mod 17 p33)_
- Source: `www.asisonline.org` _(Mod 17 p33)_

## Further BCDR standards listed (prose titles, pp34–35)

- **ISO 22320:2018 — Security and resilience — Emergency management — Guidelines for incident management**: incident response requirements with emphasis on **command and control, operational data, communication** with incident response organizations. _(Mod 17 p34)_
- **ISO 31000:2018 — Risk Management — Guidelines**: generic risk management approach regardless of nature/kind/complexity of activities; key areas risk management and effective resource allocation. _(Mod 17 p34)_
- **ISO Guide 73:2009 — Risk Management — Vocabulary**: mutual consistent understanding and coherent approach to describing risk-management activities. _(Mod 17 p34)_
- **IEC 31010:2019 — Risk management — Risk assessment techniques**: guidance on selection and application of risk-assessment techniques under uncertainty, informing decisions as part of managing risk. _(Mod 17 p35)_
- Also listed with printed titles: **ISO/TS 22317:2021** (BCMS — Guidelines for business impact analysis; formal documented BIA process, no uniform process prescribed); **NFPA 1600** (Standard on Continuity, Emergency, and Crisis Management, new consolidated draft pending); **NIST SP 800-34 Rev. 1** (Contingency Planning Guide for Federal Information Systems). _(Mod 17 p35)_

## Module Summary (p36)

- **DR = ability to restore data and applications** critical to operations; employed to restore **data center, servers, or other infrastructure**. _(Mod 17 p36)_
- **Organization BCP specifies processes and procedures** to ensure BC. _(Mod 17 p36)_
- **BC is business-centric, while recovery is data-centric** (prose form). _(Mod 17 p36)_
- **Main activities of DR and BC: prevention, response, resumption, recovery, restoration**. _(Mod 17 p36)_
- **BIA = systematic process** determining and evaluating potential effects of interruption to critical operations from disaster, accident, or emergency. _(Mod 17 p36)_

See also: [[17-LO03a-BCP-DRP-and-Elements]] (BCP/DRP goals and elements these standards govern); [[MOC-Module-18]] (risk management the BIA rests on).






