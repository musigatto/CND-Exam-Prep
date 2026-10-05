---
type: moc
module: "18"
tags: [concept, process, tool, policy, bestpractice, mod/18]
topic: "Module 18 — Risk Anticipation with Risk Management"
exam_weight: unknown
status: done
unresolved:
  - "p17 SLIDE VS TABLE 18.1 WORDING DIFFERS. The slide condenses the Extreme/High row to 'immediate measures to combat risk' while the prose prints 'isolate, eliminate, and substitute'. Both reproduced; row-to-action mapping follows prose order."
  - "p18 MATRIX CELL ALIGNMENT IS RECONSTRUCTED FROM LINEAR OCR TILE ORDER. Bands (81–100% down to 1–20%), severity classes (severe, major, moderate, minor, insignificant), the formula Risk rating = Probability x Severity, and the features are verbatim; interior cell mapping carries the record."
  - "p19 VS p21 TREATMENT WORDINGS ARE NEVER MAPPED. p19 lists avoiding / reducing / transferring / accepting; p21 lists Eliminate / Transfer / Mitigate / Accept plus Risk Avoidance / Reduce the Risk. The source never relates the two lists, so they are kept separate and unmerged."
  - "p20 PRINTS TWO BARE PHRASES WITH NO VERB OR OBJECT: 'Uncontrollable risks' and 'Client resistance to risk control'. Quoted verbatim, not completed."
  - "p27 THE KEY-ACTIVITIES LIST IS CUT BY THE PAGE BREAK after 'Selection of appropriate security controls'; the continuation on p28 is carried, but any items between the pages are unrecoverable."
  - "p32 THE COSO FIGURE TILES ARE GARBLED LAYOUT TEXT and the fifth COSO component exists only in that figure. Prose carries four components; the fifth is not asserted."
  - "p30 THE SOURCE LINE PRINTS AS 'http://csrc.nist.gov' IN THE FIGURE and 'https://csrc.nist.gov' in prose. The prose form is carried."
  - "p36 THE 'GOVERNANCE DISTINCT FROM MANAGEMENT' SENTENCE IS TRUNCATED; the full distinction is not captured. p37 focus-area examples likewise truncated."
  - "p35–36 PRINT AN 'EGit SYSTEM' OCR VARIANT; body context indicates a governance system. Recorded, not repaired."
  - "p40 TILE OCR GARBLES VENDOR URLS ('www.sas.can', 'www.inte/ex.com', 'https://www.wofterskluwer.corn/'); prose Source: lines used instead."
  - "p45 THE PHASE-FIGURE READING ORDER IS GARBLED. The phase set comes from prose pp45–47 and p49; only Discovery-first is asserted (p47 states it)."
  - "p45 FINAL SENTENCE TRUNCATED ('Some of the mo...'); omitted. p47–48 discovery prose truncated at the page boundary; the p48 cloud/IP-device fragment is dashboard context, not evidence."
  - "p53 SPOOFING-PROTECTION LEAD-IN OCRS AS 'Provide spoofing protection: o O' — detail omitted; URPF / IP Source Guard prose kept verbatim. p54 'Typical Actions: Patc...' truncated — remainder refused."
  - "p60 'FOUR STAGES OF VULNERABILITY ASSESSMENT' PRINTS ONLY THREE BULLETS (plan/configure, resolve, maintain baseline). The missing stage label is not reconstructed."
  - "p59 THE NMAP SCAN-REPORT BLOCK IS HEAVILY GARBLED (hostnames, port table) — command kept, output values omitted."
  - "p61 TOOL-LIST HEADER OCRS AS 'Not Scans 0' with a stray 'u' lead-in — tool names taken from clean p62 prose."
  - "p63 PRINTS 'Weblnspect' (lowercase L for capital I) AND 'HP Weblnspect' with Source https://www.microfocus.com; rendered as WebInspect. Substitution recorded in the note."
  - "p66 STEP-4 LABEL PRINTS TRUNCATED AS 'Assess necessity and onality'; the 'Consider consultation' and step-4 descriptions are missing in-slice. Nothing reconstructed."
  - "p67 PRINTS 'risks and hams' VERBATIM; left as printed, not corrected to 'harms'."
  - "p68 FIGURE-TILE BULLET OCR IS GARBLED; body prose used instead."
  - "pp72–74 MANDATLY DASHBOARDS AND FIGS 18.4–18.6 PLUS THE SEERS FIGURE ARE NON-EVIDENCE; only prose and Source: lines recorded. p72 'Demonstrate compliance' prose truncated — remainder omitted."
  - "p75–76 URLS QUOTED VERBATIM WITH DAMAGE: 'https://ww.privahai/', 'https://www.smartsheet.corn/', 'https ://www.privacyengine.iO/', 'https ://www.collibra.com/'. None corrected."
  - "p77 PIA PROSE TRUNCATED ('helps identify and reduce possible risks to the...'); remainder omitted."
  - "p9 FUNCTIONAL-MANAGER ROLE SEPARATORS ARE AMBIGUOUS IN OCR; four printed items reproduced without inferring hierarchy."
  - "SCREENSHOT PAGES ARE NON-EVIDENCE THROUGHOUT: OSSIM dashboards (pp48–52), Qualys VMDR (p56), Skybox (p57), Mandatly/Seers captures (pp72–74), the COSO tiles (p32), the nmap block (p59). No dashboard number, tile label, sidebar entry or graph value was read."
---

[[MOC-Module-17]]

# Module 18 — Risk Anticipation with Risk Management

> [!abstract] Scope
> **6 LOs** · PDF pp. 4–78 (book pp. 2562–2636) · **78 pages** · 10 notes · 49 cards.
> What risk management is, who does it, and how KRIs work → the **program** (context →
> identification → assessment → analysis → levels → matrix → treatment → plan → tracking)
> → the **frameworks** (ERM, NIST RMF, COSO, COBIT, policy, vendors) → the
> **vulnerability program** (phases, discovery, prioritization, assessment, remediation,
> verification) → **scanning** (external/internal, stages, tools) → **PIA/DPIA** (process,
> steps, tools) → module summary.
> **The shape trap:** p19 and p21 print **two different treatment lists** (four wordings vs
> six options) that the source never maps to each other — every "which option" item tests
> *which page* is meant. The second trap is **mitigation vs remediation vs verification**:
> mitigation acts without fixing (the WAF example), remediation corrects, verification
> proves solved.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 18.1 | Risk management concepts                            | 4–11    | 2562–2569   | 1 |
| LO02 | 18.2 | Risk management program                             | 12–24   | 2570–2582   | 2 |
| LO03 | 18.3 | Risk management frameworks (RMFs)                   | 25–42   | 2583–2600   | 2 |
| LO04 | 18.4 | Vulnerability management program                    | 43–57   | 2601–2615   | 2 |
| LO05 | 18.5 | Vulnerability assessment and scanning               | 58–64   | 2616–2622   | 2 |
| LO06 | 18.6 | Privacy Impact Assessment (PIA)                     | 65–78   | 2623–2636   | 2 |

p78 is the Module Summary and is carried in `18-LO06b`. p4 is the section-intro epigraph
page ("Risk and vulnerability management is a pro-active approach to manage network
security") carried in `18-LO01a`. p2 blank, p1 divider, p3 objectives — whose prose list
prints all six subjects including PIA.

## Technical focus

- **LO01 — concepts.** Risk management = "**process of reducing and maintaining risk at
  an acceptable level**" via a well-defined, actively employed security program;
  **identify, assess, respond** with controls; prominent through the **system security
  life-cycle**. Six objectives (p6): identify potential risks · impact analysis for
  strategy · **prioritize by impact/severity** · understand/analyse/report events ·
  **control and mitigate impact** · staff awareness and long-term plans. Seven benefits
  in order (pp6–7): potential-impact focus · level-based handling · better handling
  process · effective action in adversity · resource efficiency · **revenue protection**
  · suitable security controls. Roles (pp8–9): Senior Management (supervise, common-risk
  policies) · **CIO** (execute IT plans, train staff) · System/Information Owners
  (monitor, configuration management) · Business/Functional Managers (**trade-off
  decisions**) · ISSOs (security programs) · Practitioners · Awareness Trainers. **KRI**
  (p10) = metric **showing the riskiness of an activity**, early-stage, health
  indicator; slide triad: **define risk for an objective · identify adverse-effect
  possibility · send early warning**. Seven KRI roles (exposure/trends, impact ID,
  **backward-looking learning**, control weaknesses, reporting/escalation,
  appetite/tolerance reached, **real-time actionable intelligence**) and four features:
  **quantifiable · predictable · comparable · informational**. **KPI** (p11) assesses
  progress toward goals with **leading-indicator** info on external-event risks; KRIs
  must reflect negative KPI impact and escalate through **different escalation
  levels**. _(Mod 18 pp4–11)_
  → [[18-LO01a-Risk-Concepts-Benefits-Roles-KRI]]

- **LO02 — the program.** **Establishing context** (p13): current posture, external +
  internal environment. **Identification** (p13) = **foundation and first step**,
  listing risks **before they harm**; sources/causes/consequences of internal + external
  risks; recorded in a **risk register**; **iterative**; threats (prevent objectives)
  and opportunities (enhance them). Role groupings: Environment / Equipment / Client /
  Tasks. Elements (p14): **Description/Event · Causes · Consequences**; techniques
  **checklists, flow charts, systems analysis**; document description, how/why,
  existing controls, methods. **Assessment** (p15): **likelihood — impact** estimate,
  **ongoing iterative**, quantitative + qualitative; severity bands **1–2 eliminate
  within 24 hours**, 3–4 reasonable timeframe, 5–6 as soon as possible. **Analysis**
  (p16): inherent vs **controlled** risks; nature of risk; prioritization of
  same-severity risks by goals/resources. **Table 18.1 levels** (p17): Extreme/High =
  **isolate, eliminate, substitute** immediately · Medium-upper = controls + **strict
  timelines**, system keeps running · Medium-lower = **stop the activity** until
  reduced · Low = quick measures / preventive steps + **periodical review**. **Matrix**
  (p18): **Risk rating = Probability — Severity**; bands 81–100% to 1–20%; classes
  severe/major/moderate/minor/insignificant; quantitative/semi-quantitative, tolerable
  vs non-tolerable lines. **Treatment** (p19): select/implement controls to **modify**
  risks outside tolerance; pre-treatment list (method, owners, costs, benefits,
  success likelihood, measurement). p19 four wordings: **avoiding / reducing /
  transferring / accepting** (transfer = insurance or partnership). p21 six options:
  **Eliminate** (threat-to-zero) · **Transfer** (third party) · **Mitigate** (direct or
  competing controls) · **Accept** (addressing costs exceed impact) · **Avoidance**
  (e.g. no laptops) · **Reduce** (likelihood to acceptable). Residual risks persist.
  **Treatment plan** (p23) = action plan with responses, owners, **target dates**;
  **essential ISO 27001 document**. **Tracking vs review** (p24): tracking finds **new**
  risks and watches probability/impact/status/exposure; review tests **effectiveness**.
  _(Mod 18 pp12–24)_
  → [[18-LO02a-Risk-Context-Identification-Analysis]]
  [[18-LO02b-Risk-Treatment-Plan-and-Tracking]]

- **LO03 — frameworks.** RMFs exist to **understand the overall risk level**; objectives
  + stakeholder needs pick the framework (p25). Enterprise network RM (p26):
  identify/assess/mitigate asset threats in four defender steps. **ERM** (pp27–28):
  **planning, organizing, leading, controlling**; identify events → assess
  likelihood/impact → response strategy → monitor; nine key activities in order
  (classification → control selection → refinement → **system security plan** →
  implementation → assessment → agency-risk decision → **authorization** → continuous
  monitoring). Ten ERM goals (p29). **NIST RMF** (pp30–31): seven tasks with
  assessment sub-steps and authorize/monitor prose; `Source: https://csrc.nist.gov`
  (prose form). **COSO ERM** (pp32–33): origin plus four prose-detailed components;
  the fifth lives only in garbled figure tiles and is not asserted. **COBIT** (pp35–36):
  stakeholder lists, governance principles/objectives/cascade/components. **Policy**
  (p38) objectives and **best practices** incl. KRIs (p39). Vendors with prose
  `Source:` lines only (pp40–42): SAS, LogicManager, Enablon, Acuity (`www.sas.can`
  and `wofterskluwer.corn` tile forms refused). _(Mod 18 pp25–42)_
  → [[18-LO03a-ERM-NIST-COSO-Frameworks]]
  [[18-LO03b-Governance-Policy-Vendors]]

- **LO04 — vulnerability program.** RMFs **require** a vulnerability management program
  (p44; `Source: http://www.tripwire.com`). Phases from prose (pp45–47, 49):
  assessment, reporting (technical + executive), **remediation (treating risks)**,
  with **Discovery first** (p47: identify network assets/components). **Asset
  prioritization** (p49): importance evaluation on a **0–5 scale**. **Assessment**
  (p51): identify vulnerabilities **before attackers do**; report contents, benefits,
  steps; advantages + scheduling (p52). **Mitigation vs remediation vs verification**
  (pp53–55): mitigation acts **without fixing** — the printed example is **installing
  a WAF instead of fixing the web-app vulnerability**; mitigation types; **remediation
  corrects** the discovered vulnerability; **verification proves solved**. Extra
  solutions prose (pp56–57): Qualys, Skybox (risk-based prioritization, **scan-less**
  assessment). OSSIM/Qualys/Skybox dashboards = non-evidence. _(Mod 18 pp43–57)_
  → [[18-LO04a-Vuln-Mgmt-Program-and-Phases]]
  [[18-LO04b-Assessment-Remediation-Verification]]

- **LO05 — scanning.** **External** assessment (p59): internet-facing examination;
  nmap command kept, garbled output refused. **Four Stages** (p60) prints **three**
  bullets (plan/configure, resolve, maintain baseline) — the fourth label is absent.
  **Internal** assessment (p61): password complexity, AV protection; header OCR
  refused, names from p62 prose. Network scanners (pp61–62) and **web assessment**
  (pp63–64): crawl then report toward **vulnerability-free** websites; the printed
  list **OWASP ZAP, WebInspect, IBM Security AppScan, Qualys, Vega** (rendered from
  printed `Weblnspect`); dynamic-testing coverage beyond black-box. _(Mod 18 pp58–64)_
  → [[18-LO05a-Vuln-Assessment-and-Scanning]]

- **LO06 — PIA.** **DPIA** (p66) = **structured, systematic** assessment of privacy
  risks of specific processing; GDPR-relevant; nine steps (identify need → describe
  processing → consultation → necessity/proportionality [label truncated as
  'onality'] → identify/assess risks → mitigation measures → sign-off → integrate →
  **keep under review**). **PIA** (p68) = identify and address data-protection risks
  in new or existing projects; three objectives (legal/regulatory adherence ·
  breach-risk ID · alternative-process assessment); four triggers (new PII tech ·
  risky fresh data · system updates · PII rulemaking). **Twelve PIA steps** (pp69–70);
  PIA inside risk management (p71). Tools, prose only (pp72–76): **Mandatly**
  (case-scenario ID) · **Seers** (risk mapping) · OneTrust · TrustArc · **Privado**
  (real-time flow visualisation) · Smartsheet · PrivacyEngine · Collibra — URLs quoted
  with damage intact. **PIA vs privacy risk assessment** (p77): PIA identifies and
  reduces personal-information risks, mandatory with personal info; the assessment
  framework is the internally managed early-warning system. _(Mod 18 pp65–78)_
  → [[18-LO06a-PIA-DPIA-Process-and-Steps]]
  [[18-LO06b-PIA-Tools-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 18 sits in blueprint domain 8 **Incident Prediction =
  15%** shared with modules 17, 19, 20 — see [[Exam-Facts]]. The bank uses a **flat 5
  per module**.
- Strong question sources, in rough order of yield:
  - **The six treatment options vs the four p19 wordings** — and the fact they are
    never mapped.
  - **Mitigation (WAF) vs remediation (fix) vs verification (prove)**.
  - **Table 18.1 levels** — isolate/eliminate/substitute, strict timelines, stop the
    activity, periodical review.
  - **The matrix**: formula, bands, five classes.
  - **KRI definition, triad, four features** — quantifiable, predictable, comparable,
    informational.
  - **The nine ERM key activities in order**, especially plan → authorize → monitor.
  - **Assessment severity bands 1–2/3–4/5–6** with the 24-hour rule.
  - **The DPIA nine steps and PIA twelve steps**, especially keep-under-review.
  - **The printed scanner list** and the external/internal split.
  - **Trivia-looking items that are printed and therefore fair**: risk register,
    trade-off decisions, system security plan, target dates, ISO 27001 essential
    document, 0–5 prioritization scale, scan-less assessment, MalOp-free zone
    (no such term — it is not in this module).
- Deliberate distractors to expect:
  - **"Risk identification is the last step"** — it is the **foundation and first
    step**, and iterative.
  - **"Transfer eliminates the threat"** — Eliminate zeroes it; Transfer hands it to
    a third party.
  - **"Accept means ignore"** — accept applies at an **acceptable level** when action
    costs exceed impact.
  - **"Mitigation fixes the vulnerability"** — remediation fixes; mitigation works
    around (WAF).
  - **"The Four Stages list four labels"** — only three bullets are printed.
  - **"COSO's fifth component is X"** — it lives only in garbled figure tiles and is
    not asserted anywhere.
  - **"WebInspect is spelled with a capital I in the source"** — the page prints
    `Weblnspect` (lowercase L); the vault renders WebInspect with the substitution
    recorded.
  - **"The matrix interior is exactly X"** — interior alignment is reconstructed
    from linear OCR and recorded as uncertain; bands, classes and formula are exact.
  - **Any dashboard number or tile URL** — refused as non-evidence throughout.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-18")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/18-risk-anticipation-with-risk-management-map.canvas|Risk Anticipation with Risk Management Map]]
- Flow to visualize: **concepts** (definition → objectives → 7 benefits → roles →
  KRI → KPI) → **program** (context → identification → elements → assessment →
  analysis → levels → matrix → treatment → plan → tracking/review) → **frameworks**
  (ERM → NIST → COSO → COBIT → policy → best practices → vendors) → **vuln program**
  (phases → discovery → prioritization → assessment → mitigation vs remediation vs
  verification → tools) → **scanning** (external → stages → internal → scanners →
  web) → **PIA/DPIA** (DPIA 9 steps → PIA objectives → triggers → 12 steps → tools
  → PIA vs assessment).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]] · [[Exam-Facts]]
- Related modules: [[MOC-Module-17]] (BC/DR — the continuity plans risk management
  protects) · [[MOC-Module-16]] (Incident Response — where assessed risks
  materialize) · [[MOC-Module-11]] (Auditing — the control-assessment framing) ·
  [[MOC-Module-19]] (Attack Surface — the threat landscape feeding identification) ·
  [[MOC-Module-02]] (Administrative Network Security — the policy layer).

## Unresolved
- **p19 vs p21 treatment lists are kept separate and unmerged** — the source never
  maps four wordings to six options.
- **Table 18.1 slide-vs-prose wording differs**; mapping follows prose order.
- **Matrix interior alignment is reconstructed**, bands/classes/formula verbatim.
- **The Four Stages print three bullets**; the fourth label is absent.
- **COSO's fifth component is figure-only garble** and unasserted.
- **`Weblnspect` rendered as WebInspect** with substitution recorded.
- **p66 step-4 label truncated** ('onality'); step descriptions missing in-slice.
- **'risks and hams' kept verbatim.**
- **Five damaged URLs quoted verbatim** (privahai, smartsheet.corn, privacyengine.iO,
  collibra spacing).
- **Nine truncated tails omitted** across pp36–37, 45, 47–48, 53–54, 66, 72, 77.
- **Dashboards and figure tiles are non-evidence throughout** (OSSIM, Qualys,
  Skybox, Mandatly, Seers, COSO, nmap block).
- **Deliberately not guessed**: treatment-list mapping · fourth stage label ·
  COSO fifth component · matrix interior · nmap values · step-4 wording · any
  dashboard value · functional-manager hierarchy.

## Quick review
How many learning objectives does module 18 have, and what is LO#06's span
?
Six. LO#01 risk concepts · LO#02 risk program · LO#03 RMFs · LO#04 vulnerability program · LO#05 assessment and scanning · LO#06 PIA (pp65–77, book pp2623–2635)

What is risk management, and what are three of its printed objectives
?
The process of reducing and maintaining risk at an acceptable level through a well-defined, actively employed security program, prominent throughout the system security life-cycle. Any three of six objectives: identify potential risks · identify impact for strategy · prioritize by impact/severity · understand, analyse and report events · control and mitigate impact · staff awareness and long-term plans

What is a KRI, and what are its four printed features
?
A metric showing the riskiness of an activity (and the risk-appetite probability), giving early warning at the early stage. Features: quantifiable (number, count, percentage) · predictable (early warning) · comparable (trackable over time) · informational (risk and control status). The slide triad: define risk for an objective, identify adverse-effect possibility, send early warning

Why is risk identification first, and what does it produce
?
It is the foundation and first step, listing risks and characteristics before they harm, depending on practitioner skill. It identifies sources, causes, and consequences of all internal and external risks, records them in a risk register, and is iterative — generating the threats list (prevent objectives) and opportunities list (enhance them)

State the assessment severity bands and the Table 18.1 Extreme/High action
?
Bands 1–2 eliminate immediately, usually within 24 hours (or reduce with at least one control); 3–4 eliminate or control within a reasonable timeframe; 5–6 eliminate as soon as possible or control when possible. Extreme/High acts immediately: isolate, eliminate, and substitute the risk through effective controls

State the risk matrix formula, bands, and severity classes
?
Risk rating = Probability (Likelihood) x Severity. Probability bands 81–100% down to 1–20%; severity classes severe, major, moderate, minor, insignificant. The matrix is a quantitative/semi-quantitative tool with clearly defined tolerable and non-tolerable lines; interior cell alignment is reconstructed from linear OCR and recorded as uncertain

Which treatment list holds insurance-or-partnership transfer, and which holds threat-to-zero
?
The p19 four wordings hold Transferring the risk as shifting responsibilities to another party through insurance or partnership. The p21 six options hold Eliminate the Risk as applying controls to reduce the threat of exploiting the vulnerability to zero, and Transfer as handing the factor to a managing third party. The two lists are never mapped in the source

What must a treatment plan contain, and which standard makes it essential
?
How to respond to potential risks: summary of identified risks, each designed response, responsible parties, and target dates, with proposed controls, priorities, deadlines, resources, roles, and monitoring. It is an essential document of a certified ISO 27001 information security management system

What are the nine ERM key activities in printed order
?
Classification of the information system → selection of appropriate security controls → refinement from risk assessment → documentation in a system security plan → implementation → security controls assessment → agency-level risk and acceptability decision → authorizing information system operation → continuous monitoring of security controls

How do mitigation, remediation, and verification differ, with the printed example
?
Mitigation acts without fixing — the printed example is installing a web application firewall instead of fixing the web application vulnerability. Remediation corrects the discovered vulnerability. Verification proves the vulnerabilities are solved. Assessment first identifies issues before attackers find them

What scanners does the printed web-assessment list name
?
OWASP ZAP, WebInspect (printed `Weblnspect`), IBM Security AppScan, Qualys, and Vega — run after crawling the website, toward vulnerability-free status. External assessment examines internet-facing assets; internal covers password complexity and AV protection

State the nine DPIA steps and the last one exactly
?
Identify need → describe the processing → consider consultation → assess necessity and proportionality (label truncated as 'onality' in source) → identify and assess risks → identify mitigation measures → sign off and record → integrate outcome into plan → keep under review, repeating the DPIA on substantial changes to nature, scope, context, or purpose

When is a PIA conducted, and how does it differ from a privacy risk assessment
?
On new PII technologies, risky fresh data designs, system updates introducing new risks, and PII rulemaking. PIA identifies and reduces personal-information risks and is mandatory with personal information; the privacy risk assessment is the internally managed early-warning framework that PIA and DPIA sit under

What three vendor-URL corruptions does the vault preserve verbatim
?
https://ww.privahai/ (Privado), https://www.smartsheet.corn/ (Smartsheet), and the spaced-scheme https://www.privacyengine.iO/ and https://www.collibra.com/ forms — all quoted exactly as printed, none corrected
