---
type: moc
module: "16"
tags: [concept, process, tool, bestpractice, mod/16]
topic: "Module 16 — Incident Response and Forensic Investigation"
exam_weight: unknown
status: done
unresolved:
  - "p16 TRUE NEGATIVE IS PRINTED SELF-CONTRADICTORILY. The table labels it: 'An alarm is raised when no attack is detected. Non-malicious files are rejected successfully'. That is the False Positive definition wearing the True Negative name. Quoted verbatim in [[16-LO03a-Avoid-FUD-Assessment-Severity-and-Types]] and never repaired."
  - "p6 vs p7 NAME TWO DIFFERENT REPS. p6 lists a 'CND Representative' among the IRT-adjacent roles; p7 lists an 'HR Representative' 'involved when an internal employee is in the incident'. Both kept; the page does not say whether these are the same seat."
  - "p12 PRINTS THREE UNGRAMMATICAL PHRASES VERBATIM. The first responder 'ensures reliability and liability of evidence', is responsible for 'protecting, integrating, and preserving' evidence, and the IRT 'works on the pretext of the first responder'. None was normalised to admissibility/protecting-collecting-preserving/premise."
  - "p33 THE OCR INTERLEAVES 'Page 2425' MID-LIST inside the infrastructure bullets, so the item order there is uncertain. Recorded, not reordered."
  - "p35 PRINTS 'preempted questionnaire' for the IT-support triage questionnaire. Quoted verbatim; not corrected to any other word."
  - "p121 TABLE 16.1 PRINTS THE MDR NATURE ROW AS 'packages the assistance of EDR and MDR' — MDR packaging itself. Quoted verbatim, not reconstructed."
  - "p3 THE NUMBERED OBJECTIVE COLUMN IS OCR-DAMAGED (LO#OI, LOi04, LO$07, 'SCR' for SOAR, 'Bidpoint' for Endpoint, 'POR' for XDR) WHILE THE PROSE LIST AT THE FOOT IS CLEAN. The prose list is authoritative; LO numbers were normalised silently."
  - "PROSE 'Source:' LINES ARE KEPT VERBATIM INCLUDING THE TYPOS: 'https://mww.splunk.com/' (p71) · 'https://www.splunk.corn/' (p63) · 'https•.//wuw.manageengine.com/' and 'www.managengine.com' (p82) · 'www.dynatrace.corn' (p56) · 'https://www.solarwinds.corn/' (p97) · 'https://www.matwarebytes.com' and 'https://www.paloanonetworks.com' (p105) · tile-URL OCR on p117 ('trendrricro', 'pabaltonetworks', 'cyberseason', 'Extra Hop'). None corrected; figure-tile URLs were omitted entirely as non-evidence."
  - "p71 THE ALERT-TRIAGE ROW IS TRUNCATED ('prioritize the response a...'). Only the recoverable fragment plus the p72 wording is used."
  - "p58 FIGURES 16.6/16.7 (BigPanda) ARE GARBLED OCR LAYOUT TEXT, not a readable figure. Nothing transcribed from them."
  - "p17–p19 AND p40 PRINT TWO DIFFERENT SEVERITY SCHEMES. LO#03 (pp17–19) categorises incidents as low/medium/high with printed examples and determinants (impact, criticality, confidentiality...). LO#04 (p40) prioritises on two elements, Impact (number of systems) and Urgency (usually defined by the SLA), each high/medium/low. Both kept; the page never relates them."
  - "p128 THE FORENSICS-PROCESS FIGURE IS DIAGRAM-ONLY OCR ('Colkct Evidenc…', 'Forensic Invetwtion Managernmt'). The flow is taken from the running prose only."
  - "p129 THE MODULE SUMMARY LISTS THE ALERT CATEGORIES AS 'false positive, true positive, false negative, true negative' — repeating the p16 True Negative label without its contradictory definition."
  - "SCREENSHOT AND FIGURE PAGES ARE NON-EVIDENCE THROUGHOUT: the IR/recording/triage/notification/containment/eradication/recovery/post-incident flow diagrams (pp29, 32, 34–35, 37–38, 41, 44, 47–48, 51) · Splunk SOAR dashboards and stats (pp64, 67–68, 70, 81) · BigPanda/Dynatrace panels (pp56–58) · the EDR working/workflow diagrams (pp88–90) · Wazuh/Microsoft-learn/Cynet/ECR figures (pp93–100) · every vendor dashboard (Cybereason pp101–102, NetWitness p104, Cynet pp113–114, Log360 pp83/115–116) · the XDR architecture figure (p110) · the forensics strip/process figures (pp126, 128) · the p147-style tool tile grids (pp84–86, 105, 117). No dashboard number, tile label, sidebar entry, graph value or diagram-only label was read out of any of them; only printed prose lists and prose 'Source:' lines were used."
---

[[MOC-Module-15]]

# Module 16 — Incident Response and Forensic Investigation

> [!abstract] Scope
> **9 LOs** · PDF pp. 4–129 (book pp. 2396–2521) · **130 pages** · 19 notes · 91 cards.
> What incident response is and who does it → the **first responder** and the pre-response
> checklist → the **do's and don'ts** (FUD, assessment, severity, communicate, contain, collect,
> record, don't-touch) → the **handling process** (vision → preparation → recording → triage →
> classification → notification → containment → eradication → recovery → post-incident) →
> **AI/ML** enhancement → **SOAR** (components, automation, playbooks, tools) → **EDR**
> (workflow, detection, hunting, tools) → **XDR** (features, tools, EDR-vs-MDR-vs-XDR) → and the
> **forensics investigation process** that closes it.
> **The shape trap:** the module teaches *two* severity schemes that never meet — LO#03's
> low/medium/high incident categories (pp17–19) and LO#04's Impact-vs-Urgency prioritization
> (p40). Anything asking "what severity" is testing *which* table is meant. The second trap is
> the **True Negative row on p16**, which prints the False Positive definition under the True
> Negative name.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 16.1 | Concept of incident response                        | 4–9     | 2396–2401   | 1 |
| LO02 | 16.2 | Role of the first responder in incident response    | 10–13   | 2402–2405   | 1 |
| LO03 | 16.3 | Do's and don'ts in first response                   | 14–27   | 2406–2419   | 2 |
| LO04 | 16.4 | Incident handling and response process              | 28–51   | 2420–2443   | 3 |
| LO05 | 16.5 | Incident response using AI/ML                       | 52–61   | 2444–2453   | 2 |
| LO06 | 16.6 | Incident response using SOAR                        | 62–86   | 2454–2478   | 3 |
| LO07 | 16.7 | Incident response using EDR                         | 87–108  | 2479–2500   | 3 |
| LO08 | 16.8 | Incident response using XDR                         | 109–121 | 2501–2513   | 2 |
| LO09 | 16.9 | Forensics investigation process                     | 122–129 | 2514–2521   | 2 |

p129 is the Module Summary and is carried in `16-LO09b`. p130 is the intentionally-blank
page, p1 the module divider, p2 blank, p3 the objective list — whose numbered column is
OCR-damaged but whose prose list at the foot prints all nine subjects cleanly.

## Technical focus

- **LO01 — the concept.** IR is "**the process of taking organized and careful steps** when
  reacting to a security incident", beginning with first **identifying and reporting**; the
  systematic approach runs on **minimal damage, recovery time, and costs**. Seven goals (p5):
  detect actual-vs-false-positive · maintain/restore **Business Continuity** · reduce impact ·
  analyze cause · prevent future attacks · improve security and IR · **prosecute illegal
  activity**. The **IRT** is the group that collectively **respond, remediate, mitigate,
  recover, and communicate**; because a standing team is costly, orgs use current employees
  expert in their fields plus a few dedicated members. Twelve printed roles (pp6–8), from
  Management ("the **first entity to learn about an incident**") through the IR Assessment
  Team (prioritizes by **amount of loss**) down to IR Custodians. The **IR plan** (p9)
  determines the future course of action; the **IRP** is the guideline set built **before**
  handling incidents. _(Mod 16 pp4–9)_
  → [[16-LO01a-Incident-Response-Concept-IRT-and-IR-Plan]]

- **LO02 — the first responder.** "An individual who **arrives first at the crime scene** and
  brings the incident to the attention of others" — end user, net admin, law enforcement,
  anyone in day-to-day network operations. Value: early **detection, source, impact**,
  evidence **collection and preservation**; the IRT works "**on the pretext** of the first
  responder" (as printed). The exam-shaped core: the **time gap between occurrence and
  transference of evidence**, evidence gathered **without modifying any running services**,
  and the **First Response Rule** (p12) — "**under no circumstances should anyone except
  forensic analysts** collect or recover data" from a system holding electronic information,
  because everything inside is **probable evidence**. Before responding (p13): review the IRP,
  and before escalating document **IP + physical location, data type, activity timeline**. _(Mod 16 pp10–13)_
  → [[16-LO02a-First-Responder-Role-and-Preparation]]

- **LO03 — do's and don'ts.** Open with **FUD** (p15): **Fear, Uncertainty, and Doubt** — do
  not panic, do not damage evidence integrity, **escalate and consult management or the
  in-house computer forensics team**. Assessment (pp16–17): check **actual vs false
  positive**, identify **category and severity**. Four alert types: **False Positive**
  (alarm, no attack) · **True Positive** (alarm, real attack — act immediately) · **False
  Negative** (no alarm, real attack — rules not defined properly) · **True Negative**
  (printed self-contradictorily — see frontmatter). Six CND categories (p16): Unauthorized
  Access · **DOS** · Malicious Code · Improper Usage · Scans/Probes/Attempted Access ·
  Multiple Component. Low/medium/high with printed examples (p17) and determinants — impact,
  **criticality of the service**, confidentiality (p19). Then the action rules (pp20–27):
  **communicate** (identify who inside/outside fast) · **contain** — the disconnect-vs-stay
  dilemma is **decided by the forensic examiner or IR team**, disconnecting may lose
  evidence, staying connected may spread harm · control access (**lock and key**, secure
  nearby mobiles/CDs/flash media) · collect (**who/what/when/how**, IP, system time, running
  services) · **record everything, chronological, facts not speculation** (the Chrome-popup
  weak-vs-ideal example) · **don't investigate yourself** (non-expert collection becomes
  **inadmissible**, worst case **direct legal punishment**) · **ON stays ON, OFF stays OFF**
  · **disable virus protection** (AV changes timestamps, auto-deletes hacking tools). _(Mod 16 pp14–27)_
  → [[16-LO03a-Avoid-FUD-Assessment-Severity-and-Types]]
  [[16-LO03b-Communicate-Contain-Collect-Dos-and-Donts]]

- **LO04 — the handling process.** Ground rules (p29): **restore normal state in the
  shortest possible time**, minimize impact on other systems, avoid further incidents,
  **identify the root cause**, assess damage, update policies, **collect evidence**. Need
  factors (pp29–30): security scenario, risk perception, business advantages, **legal
  compliance**, other policies, previous incidents — and IR **cannot prevent all**
  incidents. Vision (p31): purpose and scope; seven plan-coverage items; five vision
  elements; **publish in an easily accessible repository after appropriate approvals**.
  Preparation (pp32–33): IRT establishment/training, tools/resources **before** the event;
  eight sysadmin duties (password policies, default accounts, logging/auditing, patches,
  backups, filesystem integrity). Recording (pp34–36): tickets, SIEM/IDS/AV alerts, and the
  printed 8-step flow ending in **high-first** classification. Triage (p37) = **analysis and
  validation + classification + prioritization**; accurate indication **does not necessarily
  mean** an incident (web-server crashes can be **human errors**). Classification factors
  (p39): nature, criticality, number of systems, **legal and regulatory requirements**.
  Prioritization (pp39–40): the **most critical decision**, **never first-come,
  first-served** — Impact (systems count) vs **Urgency (usually defined by the SLA)**.
  Notification (pp41–43): internal + external stakeholders, **documented management
  approval** first, **do not hide** info, external parties only **after management
  approval**. Containment (pp44–46): **controlling the effect immediately after
  occurrence**, evidence to forensics at this phase; four techniques in order (disable
  services, remove from network, **change passwords on all interacting systems**, complete
  backups); **low profile** — do not tip off the intruder. Eradication (p47): eliminate
  **root cause** (vulnerabilities, weaknesses, misconfigurations); nine countermeasures in
  order. Recovery (pp48–49): **restore from backup only after verifying it is free of
  malware**; determine course of action → monitor and validate (incl. **penetration
  testing**, watch for **backdoors**). Post-incident (pp50–51): limitations/problems review,
  effectiveness evaluation. _(Mod 16 pp28–51)_
  → [[16-LO04a-IR-Vision-Preparation-and-Recording]]
  [[16-LO04b-Triage-Classification-and-Notification]]
  [[16-LO04c-Containment-Eradication-Recovery-Post-Incident]]

- **LO05 — AI/ML.** Four printed roles (pp53–54): **proactive defense** (historical + TI
  data, upgrades/patching/access steps) · **incident triage** (severity/impact/relevance,
  **prioritize by risk and urgency**) · **automated analysis** (log data, system events,
  network traffic; TI correlation) · **autonomous response** (isolate devices, **block
  malicious IPs**, patch, disable accounts, remediate). Detection (p55): real-time large
  volumes, **patterns and anomalies**, models that **continuously update**. Triage (p57):
  severity/criticality determination, severe-first, fewer false alarms. Analysis (p59):
  TI correlation, **predict potential incidents** from history/trends. Response (p60):
  **millions of events per day**, human delay is what adversaries exploit. Five solutions
  (p61): **SIEM · UEBA · SOAR · EDR · XDR**, each with its printed one-liner. _(Mod 16 pp52–61)_
  → [[16-LO05a-AI-ML-Role-Detection-and-Triage]]
  [[16-LO05b-AI-ML-Analysis-Response-and-Solutions]]

- **LO06 — SOAR.** **Security Orchestration, Automation, and Response**: integrates
  orchestration, automation and response into one framework; combines **people, processes,
  and technology**; cuts **mean time to detect** and **mean time to respond**. Three core
  capabilities (p63): **threat and vulnerability management** (formalized workflow) ·
  **security operations automation** (enrichment, prioritization, AI-recommended measures) ·
  **security incident response** (centralized console, **no tool-switching**). Four
  components (pp65–66): Threat Intelligence (ingest/analyse, feeds **prioritized by impact
  and severity**) · Security Orchestration (**built-in/custom integrations and application
  programming interfaces**) · Security Automation (log analysis, red-flag/anomaly
  detection) · Security Incident Response (single-view dashboard). Integration targets
  (p67): SIEMs, firewalls, IDS, endpoint solutions, TI feeds, ticketing — full prose list
  adds **vulnerability scanners, UEBA, IPS, EDR**. Automation (p69): seven printed items
  from autonomously-strategize to post-incident review. The **playbook** (pp71–72) is a
  "**predefined sequence of automated and manual actions**" with **16 printed fields in
  order** (Title → Description → Triggers → Context/Gathering → Enrichment → Triage →
  Automated Response → Manual Investigation → Resolution → Communication → Documentation →
  Escalation → Metrics → Closure → Author/Reviewer → Version/Date). Six example playbooks
  (pp73–79, prose only): phishing (scan attachments/URLs, **label verified, Slack-message
  the business**) · provisioning (**Okta or Active Directory**) / deprovisioning on exit ·
  malware containment · alert enrichment · threat hunting (standard protocols and standard
  operating procedures) · patching (**automate service-ticket creation**). Tools (pp80–86):
  **Splunk SOAR** (single source for observing/understanding/deciding/acting; manual
  events, playbooks, contextual actions, third-party config, account monitoring) ·
  **ManageEngine Log360** ("unified SIEM with integrated **DLP and CASB**"; MTTD/MTTR) ·
  ServiceNow (MITRE ATT&CK integration) · Heimdal (Visualize/Hunt/Action/Eliminate) ·
  QRadar (chain-graph ATT&CK, privacy-breach playbooks) · Swimlane · Demisto. _(Mod 16 pp62–86)_
  → [[16-LO06a-SOAR-Concept-Components-and-Integration]]
  [[16-LO06b-SOAR-Automation-and-Playbooks]]
  [[16-LO06c-SOAR-Tools-Splunk-Products]]

- **LO07 — EDR.** EDR detects/investigates/responds on **individual endpoints —
  workstations, servers, mobile devices**; isolates endpoints, **blocks malicious network
  traffic**, initiates remediation **before** risks materialize. How it works (p89, five
  printed items): detect (continuous monitoring) · **threat actors** (printed as its own
  list item) · contain at the endpoint · investigate (endpoint **or** network origin) ·
  remediation back to **pre-infestation state**. Workflow (p90): monitoring upon
  installation → behavior-analysis algorithms → real-time awareness → route-tracing to the
  compromise location → analyst/engineer assessment. Eleven features (pp91–92) incl.
  continuous real-time monitoring, **behavioral-analytics baselines**, TI integration
  (IOCs, malicious IPs/domains), **SIEM and CSIR single-interface access**. Six benefits
  (p92) incl. **prevention-first** and false-positive reduction. Detection (pp93–94):
  real-time visibility, **APTs that bypass traditional AV and firewalls**, **Wazuh FIM**
  and log-gathering. Investigation (pp95–96): the printed **8-step process**
  (collection → detection → alert generation → prioritization by **severity and impact** →
  investigation → hunting → containment/eradication → remediation). Hunting (pp97–98):
  **IOCs and behavioral anomalies**, hunter persists **until confirmed harmless**.
  Response (pp99–100): **severity scores by impact and relevance**, isolate/block/remediate.
  Tools (pp101–108, prose only): **Cybereason** (kill-chain-high, all-OS investigator) ·
  **RSA NetWitness** (on- and off-network, **dwell time**, Windows log forwarding) ·
  Sophos Intercept X · **CrowdStrike Falcon Insight** · Malwarebytes (ransomware rollback) ·
  Cortex XDR · **Huntress (24/7 threat hunters)** · Symantec · Coro · Bitdefender
  (GravityZone XDR, event recorder). _(Mod 16 pp87–108)_
  → [[16-LO07a-EDR-Concept-Workflow-and-Features]]
  [[16-LO07b-EDR-Detection-Investigation-Hunting-Response]]
  [[16-LO07c-EDR-Tools]]

- **LO08 — XDR.** XDR detects/investigates/responds **across environments and layers** —
  endpoints, networks, cloud; **holistic view**, data from **EDR + network + cloud + email
  security** unified; **EDR inside XDR uses AI/ML** to automate per severity/impact; NDR
  telemetry correlation; **cross-domain hunting from a single console**. Three stages
  (pp110–111): **Ingest** (normalize: endpoints, cloud, identity, email, traffic,
  containers) → **Detect** (AI/ML correlation of stealthy threats) → **Respond**
  (severity prioritization, automated actions). Seven benefits (p111) and five key
  features (p112): data collection/integration · advanced analytics (**reduce alert
  volumes**) · contextual visibility (**human-machine teaming**, signal-to-noise) ·
  automated response/orchestration · **cross-domain threat hunting**. Tools (pp113–120):
  **Cynet auto XDR** (autonomous, no constant human intervention) · Log360 · Trend Micro
  Vision One · CrowdStrike Falcon/Insight XDR · **SentinelOne Singularity** (endpoint +
  cloud + identity in a **data lake**) · ExtraHop (**no vendor lock-in**) · Cortex XDR ·
  Cybereason (**MalOp** full attack story) · Mandiant (**dark web**, OSINT) · Sophos ·
  **Microsoft XDR** (agentless, self-healing) · Bitdefender. **Table 16.1** (p121) sets
  **EDR vs MDR vs XDR** on scope, nature, data, detection, response: EDR = endpoint
  technology, signature+behavior; XDR = endpoints+cloud+networks technology, **ML/AI over
  multiple sources**; MDR = **managed security service**, analytics + **human
  expertise**, "**usually more automated than EDR/XDR**". _(Mod 16 pp109–121)_
  → [[16-LO08a-XDR-Concept-and-Features]]
  [[16-LO08b-XDR-Tools-and-EDR-vs-MDR-vs-XDR]]

- **LO09 — forensics.** Forensic investigation = "**methodological procedures and
  techniques** to **identify, gather, preserve, extract, interpret, document, and present
  evidence**"; **conducted simultaneously with containment**; IR contains, **forensics
  finds the root cause**; goal: **the incident, the time, the perpetrator, mitigation
  steps**. Five objectives (p123): **track and prosecute** · forensically-sound gathering ·
  **impact estimate + intent assessment** · minimize tangible/intangible losses · protect
  against recurrence. Analysis evaluates **before-and-after** data, builds the **timeline**,
  balances **operations vs security per budget**. Three user groups (p124): Investigators ·
  IT Professionals · Incident handlers. Nine team roles (pp124–125): Attorney ·
  **Photographer (must be certified for evidence photography)** · Incident Responder ·
  Decision Maker · Incident Analyzer · Evidence Examiner/Investigator · Evidence
  Documenter · Evidence Manager (**name, type, time, source** per item) · Expert Witness
  (authenticates facts, **cross-examines**). The nine methodology steps in order
  (pp126–127): **search warrant → evaluate/secure scene → collect → secure evidence →
  acquire data → analyze (the most important phase — log monitoring) → assess → final
  report (investigator's AND suspect's actions) → testify**. Post-analysis (p128):
  perpetrator found → management chooses **prosecution vs disciplinary team**; not found →
  close or pass external; **severe incidents → law enforcement + file a case**. _(Mod 16 pp122–129)_
  → [[16-LO09a-Forensics-Concept-and-People]]
  [[16-LO09b-Forensics-Methodology-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 16 **owns blueprint domain 7 Incident Response = 10%**
  alone — see [[quiz.html]]. The bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield:
  - **The nine forensics methodology steps in order**, especially warrant-first and
    analysis-as-most-important.
  - **The IR goal list** — actual-vs-false-positive, Business Continuity, prosecute.
  - **The First Response Rule** — only forensic analysts collect; everything is probable
    evidence.
  - **The four alert types** — and the p16 True Negative trap.
  - **The six CND incident categories** — Unauthorized Access, DOS, Malicious Code, Improper
    Usage, Scans/Probes/Attempted Access, Multiple Component.
  - **The disconnect-vs-stay dilemma** and who decides it.
  - **ON stays ON, OFF stays OFF** — and disable the antivirus.
  - **Triage = analysis/validation + classification + prioritization**; prioritization is
    **never first-come, first-served**; Impact vs **Urgency (SLA)**.
  - **The containment four, eradication nine, recovery verify-before-restore** sequences.
  - **SOAR expansion, three capabilities, four components, the 16-field playbook**, and the
    six example playbooks.
  - **The EDR 8-step investigation process** and the eleven features.
  - **Table 16.1 EDR vs MDR vs XDR** — technology vs technology vs **managed service**.
  - **The nine forensics team roles** — especially the certified Photographer and the
    name/type/time/source Evidence Manager.
  - **Trivia-looking items that are printed and therefore fair**: FUD, Business Continuity,
    HIPAA/FISMA, Okta/Active Directory, MITRE ATT&CK, MTTD/MTTR, DLP/CASB, MalOp, data
    lake, Wazuh FIM, 24/7 hunters, GravityZone event recorder.
- Deliberate distractors to expect:
  - **"The first responder should start the investigation immediately"** — the page says
    waiting for authorization; non-expert collection becomes **inadmissible**.
  - **"Disconnect the compromised device at once"** — the decision belongs to the forensic
    examiner/IR team; either choice has a printed downside.
  - **"Keep antivirus running on the suspected device"** — the page says disable it.
  - **"Change the device state to preserve evidence"** — ON stays ON, OFF stays OFF.
  - **"A True Negative raises an alarm"** — that is the page's (contradictory) printed
    wording; the *concept* it describes is a False Positive. Read the question stem.
  - **"Prioritize first-come, first-served"** — the page forbids exactly that.
  - **"Restore from backup, then check it"** — verify the backup is clean **before**
    restoring.
  - **"MDR is a technology like EDR/XDR"** — the table says **managed security service**.
  - **"Forensics runs after containment finishes"** — the page says **simultaneously**.
  - **"The methodology starts at the crime scene"** — step 1 is the **search warrant**.
  - **Any dashboard number, tile count, graph value or tool-version string** — all live in
    figures and were deliberately not transcribed.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-16")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/16-incident-response-and-forensic-investigation-map.canvas|Incident Response and Forensic Investigation Map]]
- Flow to visualize: **what IR is** (definition → 7 goals → 12 IRT roles → the plan) →
  **the first responder** (definition → time-gap → the Rule → pre-response checklist) →
  **do's and don'ts** (FUD → assessment → 4 alert types → 6 categories → low/med/high →
  communicate → contain → access control → collect → record → don't-investigate →
  don't-change-state → disable AV) → **the process** (ground rules → need → vision →
  preparation → recording → triage → classification → prioritization → notification →
  containment → eradication → recovery → post-incident) → **AI/ML** (4 roles → detection →
  triage → analysis → response → 5 solutions) → **SOAR** (expansion → 3 capabilities → 4
  components → integration → automation → 16-field playbook → 6 examples → tools) → **EDR**
  (concept → 5 how-it-works → workflow → 11 features → 6 benefits → detection →
  8-step investigation → hunting → response → tools) → **XDR** (concept → 3 stages → 7
  benefits → 5 features → tools → Table 16.1) → **forensics** (definition → 5 objectives →
  3 user groups → 9 roles → 9 methodology steps → post-analysis decisions).

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-15]] (Network Logs Monitoring — the log evidence this
  module's forensics phase consumes) · [[MOC-Module-14]] (Network Traffic Monitoring — the
  traffic evidence of the same phase) · [[MOC-Module-11]] (Auditing — the audit-trail
  framing behind recording and documentation) · [[MOC-Module-02]] (Administrative Network
  Security — the policy layer the IR plan and vision answer to) · [[MOC-Module-17]]
  (Business Continuity and Disaster Recovery — where the Business Continuity goal and the
  recovery phase land) · [[MOC-Module-04]] (Network Perimeter Security — the firewall and
  IDS/IPS alerts that feed recording and triage).

## Unresolved
- **p16 prints True Negative as an alarm-raised definition** — the False Positive wording
  under the wrong name (see frontmatter).
- **p6 vs p7 name two different representatives** (CND vs HR) with no reconciliation.
- **p12's three ungrammatical verbatim phrases** — liability, integrating, pretext.
- **p33's mid-list page-number interleave** leaves the infrastructure-bullet order uncertain.
- **p35's "preempted questionnaire"** and **p121's "packages the assistance of EDR and
  MDR"** are quoted, not repaired.
- **Eight prose `Source:` URLs carry printed typos** (mww, .corn, wuw, managengine,
  matwarebytes, paloanonetworks) and are kept verbatim; figure-tile URLs were omitted.
- **Two severity schemes coexist unreconciled** — LO#03 low/medium/high vs LO#04
  Impact/Urgency.
- **The p128 forensics-process figure is diagram-only OCR**; the flow comes from prose.
- **Screenshot and figure pages are non-evidence throughout** — 20+ flow-diagram and
  dashboard locations listed in the frontmatter.
- **Deliberately not guessed**: the True Negative repair · the CND/HR representative
  identity · the p33 bullet order · the p71 truncated triage row · five Table-19-style
  illegible items (none here — Table 16.1 is complete) · any dashboard value · the
  BigPanda p58 content · cloud-based unified management (figure-only EDR benefit).

## Quick review
How many learning objectives does module 16 have, and what is LO#04's span
?
Nine. LO#01 IR concept · LO#02 first responder · LO#03 do's and don'ts · LO#04 incident handling and response process (pp28–51, book pp2420–2443) · LO#05 AI/ML · LO#06 SOAR · LO#07 EDR · LO#08 XDR · LO#09 forensics investigation process

What is incident response, and what are three of its seven printed goals
?
"The process of taking organized and careful steps when reacting to a security incident", run with minimal damage, recovery time, and costs. Any three of: detect actual-vs-false-positive · maintain or restore Business Continuity · reduce impact · analyze cause · prevent future attacks · improve security and IR · prosecute illegal activity

What is the IRT, and why do organizations usually staff it from current employees
?
A group of specialized people who collectively respond, remediate, mitigate, recover, and communicate the impact of breaches. Maintaining a separate team is costly, so organizations generally use current employees expert in their fields plus a few dedicated members

Who learns about an incident first, and who oversees all IR activities
?
Management is the first entity to learn about an incident and decides the steps once confirmed. The IR Officer oversees all IR activities at executive level, and every IRT action is reported through the IR Officer to management

State the First Response Rule
?
Under no circumstances should anyone except forensic analysts collect or recover data from any computer system or electronic device holding electronic information. Everything inside collected devices is probable evidence, and unqualified retrieval attempts risk compromising file integrity or making files inadmissible

What is FUD and what does the page direct on discovering an incident
?
Fear, Uncertainty, and Doubt. Do not panic, do not perform actions that damage evidence integrity, and escalate and consult management or the in-house computer forensics team. Decisions made in fear or anxiety worsen the situation and can forego important information, mislead investigators, and delay identifying why the incident occurred

The four alert-based incident types as printed
?
False Positive (alarm raised, no attack) · True Positive (alarm raised, actual attack — act immediately) · False Negative (no alarm, actual attack — rules not defined properly) · True Negative, which the page prints as "An alarm is raised when no attack is detected", the False Positive wording under the wrong name

What must the disconnect-vs-stay-connected decision go through, and what is the downside of each side
?
It must be decided by the forensic examiner or IR team. Disconnecting during an attack may lose evidence that would have been found if connected; staying connected may let the attack proceed and cause further harm

What are the ON/OFF and antivirus rules for a suspected device
?
ON stays ON and OFF stays OFF — restart or shutdown forces internal changes that destroy evidence. Disable virus protection as soon as possible, because antivirus can access files, change time/date stamps during automated scanning, and automatically delete suspected files and hacking tools

What is triage in this module, and what rule governs prioritization order
?
Triage is incident analysis and validation plus incident classification plus incident prioritization. Prioritization is the most critical decision and is never first-come, first-served — it runs on Impact (number of systems) against Urgency (usually defined by the SLA), highest business impact first

Name the four containment techniques in printed order
?
Disable specific system services temporarily · remove the computer from the network until an unknown vulnerability is rectified · change passwords and disable the account, on all systems interacting with the affected system · complete backups of the infected system

What must be verified before restoring from backup, and what are the two recovery steps
?
Verify the backup is free of malware and attack vectors before restoring. The two steps are determine the course of action (per resources, criticality, cost-benefit) and monitor and validate (no traces, normal operation, backup-data integrity, vulnerability assessments and penetration testing, watch for backdoors)

What does SOAR stand for, and what are its three core capabilities
?
Security Orchestration, Automation, and Response. Threat and vulnerability management (formalized workflow, collaboration, reporting) · security operations automation (event enrichment, alert prioritization, AI-recommended measures) · security incident response (centralized console, no tool-switching)

What is a SOAR playbook, and which six example playbooks does the module walk through
?
A predefined sequence of automated and manual actions guiding responders through detecting, analyzing, and responding, with 16 printed fields from Title to Version/Date. The six examples are phishing investigations · provisioning/deprovisioning users · malware containment · alert enrichment · threat hunting · patching and remediating

The eight-step EDR incident investigation process in printed order
?
Data collection → threat detection → alert generation → incident prioritization (by severity and impact) → incident investigation → threat hunting → threat containment and eradication → remediation

How do EDR, XDR and MDR differ in Table 16.1
?
EDR is a technology monitoring endpoints with signature and behavior-based analytics. XDR is a technology and extension of EDR monitoring endpoints, cloud services and networks with ML and AI over multiple sources. MDR is a managed security service, usually more automated than EDR/XDR, running on analytics and human expertise

State the nine forensics methodology steps in order
?
Obtain a search warrant → evaluate and secure the scene → collect the evidence → secure the evidence → acquire the data → analyze the data (the most important phase) → assess the evidence and the case → prepare the final report (investigator's and suspect's actions) → testify as an expert witness

Which two forensics roles carry a printed certification or per-item record requirement
?
The Photographer must be certified for evidence photography, and the Evidence Manager holds the name, type, time, and source of each item so the evidence stays admissible in court

When does forensics run relative to containment, and what decides prosecution vs discipline
?
Forensic investigation is conducted simultaneously with the containment process. If the perpetrator is identified, management decides between law-enforcement prosecution and the organizational disciplinary team; severe incidents affecting employees, customers or the public go to external law enforcement with a case filed
