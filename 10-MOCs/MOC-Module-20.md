---
type: moc
module: "20"
tags: [concept, process, tool, bestpractice, mod/20]
topic: "Module 20 — Threat Prediction with Cyber Threat Intelligence"
exam_weight: unknown
status: done
unresolved:
  - "pp9–10 SAY THREE TI TYPES WHILE p14 PRINTS A FOURTH (Technical). Intro and body frame strategic/tactical/operational; p14 adds Technical with full prose. Source contradicts itself; all four recorded."
  - "p25 SAYS FOUR TI LAYERS WHILE FIGURE 20.3 TILES FIVE (Providers / Sources / Feeds / Platforms / Professional Services). Prose defines four; the fifth tile is unasserted."
  - "p24 TABLE 20.1 IOA CELLS GARBLED, QUOTED VERBATIM: 'Monitoring what (whom) recognize yet' and 'Used in real time we do not'. Not reconstructed."
  - "p23 'ADVANCE PERSISTENCE THREATS' KEPT VERBATIM (printed identically in figure and prose). p23 singular 'Connection using uncommon ports' vs figure plural — prose followed."
  - "p17 'OpenlOC' KEPT VERBATIM (lowercase-L throughout); slice never prints a clean form, so OpenIOC is presumed but not asserted."
  - "p18 STIX LIST SPANS THE COLUMN BREAK; TTPs reading order reconstructed, wording verbatim."
  - "p20 FIGURE VS PROSE LISTS DIFFER: figure prints 'Geographical anomalies', omits 'Login irregularities' and 'MD5 hash file in the temporary directory'. Prose list followed."
  - "p14 'single loc' VS CAPTION 'single IoC' — IoC used. p11 'lnformation' read as Information. p10 'ISAO/lSAC's' expanded per p11 prose."
  - "TRUNCATED TAILS OMITTED THROUGHOUT: p27 Internal Intel, p28 counterintel, p30 Finance factor, p35 US-CERT, p40 collection bullet, p45 USM sentence, p46–47 DeepSight block + unattributed monitor bullets, p47 darkweb + p49 Frontline fragments, p51 TI classification, p53 STIX benefits, p54 SIEM benefits, p72 compliance tail, p77 PIA tail."
  - "p29 'https://www.exp/oit-db.com' AND 'OxOOsec vs 0x00sec' WITH https://OxOOsec.org/ QUOTED VERBATIM. p35 AIS 'Source: www.dhs.gov' kept without reconciliation."
  - "pp37–39 NO PROSE SOURCE LINES for Recorded Future, Broadcom, Team Cymru, Trellix, Anomali — URLs omitted. AlienVault, CrowdStrike, Infragard, ISC, Proofpoint, ThreatStop, Talos prose deliberately omitted per assignment scope."
  - "p44 'suddenly stop threats' KEPT VERBATIM. p46 LookingGlass 'www.zerofox.com' KEPT VERBATIM, not corrected."
  - "p60 'SHAI AND MD5' REFUSED NORMALISATION (likely SHA1). Fig 20.7 difficulty pairing read from label order + p60 ascending prose; TTPs apex not captured as OCR text."
  - "p69 'out of data' QUOTED (likely out of date). p70 'Security QRadar SIEM, Splunk, IBM QRadar SIEM' quoted with apparent duplication. p66 maturity-diagram adjacency ambiguous — traits follow p67–68 prose."
  - "p71 'CrowdStrike Falcono', 'Managed )(DR', 'Mantix4'; p72 'Cynet 369' AND 'Cynet 360'; 'www.www.ka/i.org'; 'www.managengine.com'/'MangeEngine' — ALL KEPT AS PRINTED."
  - "p75 'LO#OZ', 'A/ ML'; p76 'police enforcement', 'adaption', 'Al'-for-AI; p79 'https://www.ropid7.com'; p81 'tremx.com' vs 'trellix.com', truncated 'https://www.ibm.', 'WILF-IRE' vs 'WILFIRE', 'recieve' — ALL KEPT VERBATIM."
  - "p81 TOOL ENTRIES CARRIED IN SIBLING (LO07a pp75–80, LO07b pp81–85) AGAINST THE MANIFEST SPLIT; citations match actual pages."
  - "p85 SUMMARY OCR ENDS AT 'before consuming threat intelligence'; later bullets if any are omitted."
  - "SCREENSHOT AND FIGURE PAGES ARE NON-EVIDENCE THROUGHOUT: threatfeeds.io/CISA-AIS captures (pp34–35), tile grids (p37), TC Complete dashboards (pp42–43), OSSIM screenshot (pp56–57), hunting-tool dashboards (pp71–73), Log360 capture (Fig 20.12), Rapid7 IntSights (Fig 20.13). No dashboard number, tile label, sidebar entry or graph value was read."
---

[[MOC-Module-19]]

# Module 20 — Threat Prediction with Cyber Threat Intelligence

> [!abstract] Scope
> **7 LOs** · PDF pp. 4–85 (book pp. 2700–2781) · **86 pages** · 13 notes · 67 cards.
> The largest module in the second half of the vault. What CTI is and why orgs consume
> it → the **four TI types** (strategic/tactical/operational + the unannounced
> Technical) → **IoCs vs IOAs** (what vs why, Table 20.1) → the **layers** (providers,
> sources, feeds, platforms) → **consuming** TI (goals, Cisco, SIEM, manual review,
> Pyramid) → **threat hunting** (blocks, maturity, practices, tools) → **AI/ML for TI**
> (uses, tools, guidelines) → summary.
> **The shape trap:** the module announces **three** TI types twice, then prints a
> **fourth** (Technical) with full prose — every "how many types" item tests whether
> you count the unannounced one. The second trap is **IoC-vs-IOA**: reactive/known/
> post-point-in-time/malware vs proactive/unknown/real-time/behavior, with two
> Table 20.1 cells too garbled to quote for meaning.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 20.1 | CTI role in network defense                         | 4–8     | 2700–2704   | 1 |
| LO02 | 20.2 | Types of threat intelligence                        | 9–14    | 2705–2710   | 1 |
| LO03 | 20.3 | IoCs and IOAs                                       | 15–24   | 2711–2720   | 2 |
| LO04 | 20.4 | Layers of threat intelligence                       | 25–49   | 2721–2745   | 3 |
| LO05 | 20.5 | Consume TI for proactive defense                    | 50–60   | 2746–2756   | 2 |
| LO06 | 20.6 | Threat hunting                                      | 61–74   | 2757–2770   | 2 |
| LO07 | 20.7 | AI/ML for threat intelligence                       | 75–85   | 2771–2781   | 2 |

p85 is the Module Summary and is carried in `20-LO07b`. p86 is the intentionally-blank
page, p2 blank, p1 divider, p3 objectives — whose numbered column is badly damaged
against a clean seven-subject prose list.

## Technical focus

- **LO01 — CTI role.** CTI = **collection and analysis of information about threats
  and adversaries** for informed preparedness/prevention/response decisions; lets
  defenders grasp **what the attacker is doing and how to stop or prevent it**.
  Consumption reasons (pp6–8): risk-management efficiency, persistent-mechanism
  removal (malicious files/systems), Identify/Detect/Respond/Recover objectives.
  `these indictors` [sic] kept verbatim. _(Mod 20 pp4–8)_
  → [[20-LO01a-CTI-Role-in-Network-Defense]]

- **LO02 — four types.** Basis (p9): initial requirements, sources, audience; by
  consumption **strategic, tactical, operational** — then p14 prints **Technical**.
  **Strategic** (pp10–11): high-level posture/financial-impact/trends for execs and
  CISO; **report** form, pre-emptive; OSINT/vendors/**ISAOs/ISACs**; budgets, staffing,
  attribution, sector landscapes. **Tactical** (p12): attacker **TTPs** as forensic
  reports (malware, campaigns, tools); campaign/malware/incident/group reports + HUMINT;
  feeds product updates and patching. **Operational** (p13): **specific threats** with
  **intention, capability, opportunity**; IR heads/defenders/forensics/fraud teams;
  often **government-only** collection; human/social/chat sources; report form with
  **courses of action**. **Technical** (p14): tools/channels/resources for security
  teams; **stealer logs, IOC feeds, CVE data**; quick, transient, **single-IoC**
  scope. _(Mod 20 pp9–14)_
  → [[20-LO02a-Types-of-Threat-Intelligence]]

- **LO03 — IoCs vs IOAs.** **IoCs** (p16) = **clues/artifacts/evidences** of intrusion;
  stop **repeated, unchanged** threats but **not new or modified** ones. Formats:
  OpenIOC (printed `OpenlOC`), CybOX, **STIX** (construct list across the break),
  TAXII (models figure), **MAEC** (container + vocabulary). Prose examples (p20):
  unusual outbound traffic, C&C domain names, hashes, login irregularities, temp-dir
  MD5. **IOAs** (p21) = **strategic indicators** from **intent + end goal + pre-attack
  action series**; the **'why'** to IoC's 'what'; visible **before IOCs**; needs **no
  malware knowledge**; data types incl. **EBA**, DLLS [sic], code-execution metadata.
  Advantages (p22): strategic TTP view, **pre-entry prevention** (attacker needs no
  malware, system needs no tools). Examples (p23): advance persistence [sic],
  RCE, DNS tunneling, fast-flux, beaconing, honeytoken bursts, port scans, C&C
  heartbeat, exfiltration, high SMTP, uncommon ports. **Table 20.1** (p24): reactive
  vs proactive · post-point-in-time vs real-time [truncated] · malware/signatures/
  exploits/vulns/IPs vs code-execution/persistence/stealth/C2/lateral · known
  universal bad news vs situational bad news · tool examples vs behavior examples —
  with two garbled cells quoted, not read for meaning. _(Mod 20 pp15–24)_
  → [[20-LO03a-IoCs-STIX-and-MAEC]]
  [[20-LO03b-IOAs-and-IOC-vs-IOA]]

- **LO04 — layers.** Prose defines **four** (providers, sources, feeds, platforms);
  Fig 20.3 tiles a fifth (Professional Services), unasserted. **Providers**:
  open-source communities/movements or private/commercial bodies. **Sources**:
  open/internal/commercial raw data; **employees** as internal-threat source;
  hacking-forum OSINT example. **Feeds**: continuous packaged-data streams; free
  lists; focus areas botnets/C&C/IPs/phishing/mobile. Providers, prose only: free
  + open-source sets · government (incl. **ENISA**, US-CERT/AIS with verbatim
  quirks) · commercial five (**Recorded Future, Broadcom, Team Cymru, Trellix,
  Anomali** — no prose URLs, omitted; seven more tile-only names deliberately
  excluded per scope). **TIPs**: definition (aggregate/normalize/enrich/automate),
  processing necessity, **TC Complete** (ratings, votes, false-positive counts),
  **IBM X-Force** (`suddenly stop threats` [sic]), **IntelMQ** (message-queue CERT
  tool), **USM Anywhere** (AlienVault Labs stream), plus Pulsedive/LookingGlass/
  iSIGHT/DeepSight/threatnote/AbuseHelper/NetWitness/IntSights/Recorded Future/
  Webroot prose fragments. Dashboards on pp42–43 non-evidence. _(Mod 20 pp25–49)_
  → [[20-LO04a-TI-Layers-Providers-Sources]]
  [[20-LO04b-TI-Feed-Providers]]
  [[20-LO04c-Threat-Intel-Platforms]]

- **LO05 — consumption.** Goals first: define **goals, need, purpose**; proactive
  defense as ultimate goal. Feed evaluation (pp51–52): landscape coverage, **data
  age**, and truncated criteria. **Cisco** (p53): Firepower + **Threat Intelligence
  Director** on Firepower Management Center, STIX/TAXII single integration point.
  **SIEM** (pp54–55): scope-finding via local-to-feed correlation; **OSSIM** rule
  list (p56 prose; Fig 20.6 screenshot refused). **Manual review** (p58) = obtain
  feeds, review by hand for posture-relevant threats. **Pyramid of Pain** (pp59–60):
  higher = costlier for attackers = more resilience; TTP-focus beats tool-focus.
  Six levels bottom→top: **Trivial Hash Values** (`SHAI`/MD5, metamorphic,
  least significant) · **Easy IP Addresses** (VPN/proxy rotation) · **Simple
  Domain Names** (dynamic DNS services + domain-generated algorithms) ·
  **Annoying Network/Host Artifacts** (rejection causes pain) · **Challenging
  Tools** (rebuild research) · **Tough! TTPs** (counter behaviors, apex).
  _(Mod 20 pp50–60)_
  → [[20-LO05a-Consume-TI-and-SIEM-Integration]]
  [[20-LO05b-Manual-Review-and-Pyramid-of-Pain]]

- **LO06 — hunting.** Definition (p62): **proactive search** for signs missed by
  regular measures; actors dwell **months**; non-signature; findings feed **IR**
  (→ [[MOC-Module-16]]). Four steps (Fig 20.8): **Hypothesize → Investigate (raw +
  linked + ML merge) → Uncover patterns/TTPs (the success criterion) → Enrich
  analytics (automate outward)**. Hunter duties (p63): insider/outsider/known/hidden
  threats, IR-plan execution. Blocks (p64): **Automation** (never start over) ·
  **Enrichment** (context) · **Visualization** (dataset links) · **Hunters**
  (curiosity, tooling). Maturity (pp66–68): **0 Initial/HMMO** (no collection, OSINT
  + lower-Pyramid data) · **1 Minimal** (alert-driven IR, TIP-enriched IOCs) ·
  **2 Procedural** (others' processes — **most orgs**) · **3 Innovative** (own
  procedures, stats-to-ML fluency) · **4 Leading** (automated successes, continuous
  refinement). Best practices (pp68–69): know the environment · full visibility ·
  track techniques · existing tools + **ML speed** · **UEBA** · internal/external
  scans (`out of data` [sic]) · external hunters · dark web · **OODA (Observe,
  Orient, Detect, Act)**. Tool types (p70): monitoring (SolarWinds/Nagios/
  Wireshark) · SIEM (`Security QRadar SIEM`, Splunk, IBM QRadar SIEM [sic]) ·
  analytics (**YARA**). Platforms (pp71–73, prose): Carbon Black, Exabeam, **Cynet
  369/360** (both kept), Maltego, **Log360**. AI/ML hunting (p74): three-item list
  + persistent proactivity. _(Mod 20 pp61–74)_
  → [[20-LO06a-Threat-Hunting-Concept-and-Maturity]]
  [[20-LO06b-Hunting-Tools-and-AI-ML]]

- **LO07 — AI/ML for TI.** Capabilities (p76): **automated collection/analysis**
  (logs, alerts, OSINT → IOCs) · **ML/deep-learning adaptation** · **sharing**
  (peers, `police enforcement` [sic], agencies; cross-validation) · **skills**
  (courses → podcasts). Use cases (pp77–78): **summarization (LLMs condense)** ·
  **IOC extraction** (social/dark-web unstructured) · **TTP extraction** (long
  research docs) · **predictive** (past → future posture) · **alert generation** ·
  **LLM exchange** (auto warnings/reports) · decision support · real-time TI.
  **IoC enrichment** (p79): feeds add context to IPs/domains/hashes; impact-based
  prioritization; hunting correlation; `ropid7` garble + dashboard refused.
  **Phishing** (p80): known malicious domains/addresses/techniques + compromised
  accounts; automated, preventive-tool, AI-analysis approaches. Solutions (pp81–82):
  **Trellix GTI** (cloud reputation, `tremx` tile) · **IBM Watson** (self-
  strengthening ML) · **TCPWave** (benign-vs-malicious deep learning) ·
  **WILDFIRE/WILF-IRE** (`recieve` [sic]) · **ThreatConnect TIP** (normalize/enrich/
  automate). Guidelines (pp83–84): proactive AI · embed in tooling (TI-alone is
  weak) · **alert quality** (false-positive rejection) · transparency/accountability
  (AI-vs-human provenance) · CIA-prioritized resilience · bias supervision
  (diversity). _(Mod 20 pp75–85)_
  → [[20-LO07a-AI-ML-for-Threat-Intel]]
  [[20-LO07b-TI-Tools-Guidelines-and-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 20 sits in blueprint domain 8 **Incident Prediction =
  15%** shared with modules 17, 18, 19 — see [[quiz.html]]. The bank uses a **flat 5
  per module**.
- Strong question sources, in rough order of yield:
  - **Three-vs-four TI types** — Technical is printed but unannounced.
  - **IoC-vs-IOA**: what/known/reactive/malware vs why/situational/proactive/behavior.
  - **The Pyramid bottom→top with pain labels** — Trivial Hashes to Tough! TTPs.
  - **The four hunting steps** with Uncover-patterns as success criterion.
  - **Maturity levels 0–4**, especially HMMO-empty and Procedural-most-orgs.
  - **The nine DPIA-style lists**: nine AI-use cases, six guidelines, five solutions.
  - **Layers/providers/sources/feeds/platforms** and the ENISA/government set.
  - **OODA**, EBA/DLLS data types, pre-entry prevention's no-malware/no-tools pair.
  - **Trivia-looking items that are printed and therefore fair**: ISAOs/ISACs,
    stealer logs, single-IoC scope, C2 heartbeat, honeytoken bursts, HMMO, YARA,
    ropid7/tremx/WILF-IRE garbles (as "which is printed" items).
- Deliberate distractors to expect:
  - **"There are three TI types"** — the page prints a fourth on p14.
  - **"IOCs catch new threats"** — they miss new/modified; IOAs catch them.
  - **"IOAs need malware samples"** — pre-entry needs **no malware**, system needs
    **no tools**.
  - **"Move down the Pyramid for resilience"** — move **up**.
  - **"Level 0 collects everything"** — Level 0 collects **nothing**, lives on OSINT.
  - **"Most orgs are Leading"** — most are **Procedural**.
  - **"TI works best alone"** — less effective alone; embed it.
  - **"OpenIOC is spelled with capital I in source"** — printed `OpenlOC`.
  - **"Table 20.1's garbled cells read X"** — quoted, never reconstructed.
  - **Any dashboard number, tile count, or figure-only label** — non-evidence.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-20")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/20-threat-prediction-with-cyber-threat-intelligence-map.canvas|Threat Prediction with Cyber Threat Intelligence Map]]
- Flow to visualize: **CTI role** (definition → reasons → objectives) → **types**
  (strategic → tactical → operational → Technical) → **IoCs** (definition → limits →
  formats → examples) → **IOAs** (why → data types → advantages → examples → Table
  20.1) → **layers** (providers → sources → feeds → platforms) → **consume**
  (goals → Cisco → SIEM → manual → Pyramid) → **hunt** (steps → blocks → maturity
  → practices → tools → AI/ML) → **AI/ML for TI** (capabilities → use cases →
  enrichment → phishing → solutions → guidelines).

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-19]] (Attack Surface — the exposures TI watches) ·
  [[MOC-Module-16]] (Incident Response — where TI lands and hunting runs) ·
  [[MOC-Module-18]] (Risk Management — the framework TI feeds) · [[MOC-Module-11]]
  (Auditing — the log evidence hunting correlates).

## Unresolved
- **Three-vs-four TI types** — Technical unannounced on p14, all four recorded.
- **Four layers vs five figure tiles** — fifth unasserted.
- **Table 20.1 garbled cells quoted, never reconstructed.**
- **Advance persistence / uncommon-ports singular / OpenlOC / STIX break /
  figure-vs-prose p20 list** — all kept as printed.
- **loc/IoC/lnformation/ISAO normalisations** logged in notes.
- **Nine truncated tails omitted** across pp27–72.
- **verbally-damaged URLs and names** (exp/oit-db, OxOOsec, zerofox, ropid7,
  tremx, ibm-dot, WILF-IRE, recieve, Falcono, Cynet 369, ka/i.org,
  managengine, Mantix4) — all verbatim.
- **Commercial URLs absent in prose (pp37–39); seven providers out of scope.**
- **Fig 20.7 pairing read from labels + ascending prose; apex uncaptured.**
- **Maturity traits follow p67–68 prose over jumbled p66 diagram.**
- **LO07a/07b split at pp80/81 against the manifest** — citations match actuals.
- **p85 summary cut at 'before consuming threat intelligence'.**
- **All dashboard/figure captures non-evidence** — 12+ locations in frontmatter.
- **Deliberately not guessed**: the three-vs-four count · garbled cells ·
  OpenIOC spelling · p20 figure-only item · missing tails · dashboard values ·
  out-of-scope providers · post-cutoff summary bullets.

## Quick review
How many learning objectives does module 20 have, and what is LO#04's span
?
Seven. LO#01 CTI role · LO#02 TI types · LO#03 IoCs/IOAs · LO#04 layers (pp25–49, book pp2721–2745) · LO#05 consume · LO#06 hunting · LO#07 AI/ML for TI

What is CTI, and what does it let defenders grasp
?
The collection and analysis of information about threats and adversaries for informed preparedness, prevention, and response decisions. It lets defenders understand what an attacker is doing and how to stop or prevent an attack — consumed for risk efficiency, persistent-mechanism removal, and Identify/Detect/Respond/Recover

How many TI types does the module print, and what is the catch
?
Four with prose each — Strategic, Tactical, Operational, and Technical — but the p9/p10 framing announces only three. Technical (tools/channels/resources, stealer logs, IOC feeds, CVE data, single-IoC scope) is printed in full on p14 and counts

Who consumes Tactical vs Operational, per the page
?
Tactical: IT service managers, security operations managers, NOC staff, administrators, architects — attacker TTPs, capabilities, goals, vectors. Operational: security managers/IR heads, network defenders, forensics, fraud teams — specific threats with intention, capability, opportunity, and courses of action; often government-only collection

State the IoC-vs-IOA contrast as Table 20.1 prints it
?
IOCs: monitoring what (who) we know · reactive · post-point-in-time only · malware/signatures/exploits/vulns/IPs · miss new threats · known universal bad news. IOAs: strategic intent/goal/action indicators · proactive · real-time · code-execution/persistence/stealth/C2/lateral · catch new unknown threats · situational bad news. Two IOA cells are garbled in source and quoted, never reconstructed

What do STIX, TAXII, and MAEC each do in the module
?
STIX is the language for sharing (construct list spans the pp17–18 break). TAXII has exchange models (Fig 20.1). MAEC characterizes malware data via container + vocabulary. IoCs travel in OpenIOC (printed OpenlOC), CybOX, STIX, TAXII, MAEC

Name the four prose layers and the figure-only fifth
?
Providers (open-source communities or commercial bodies) · Sources (open/internal/commercial raw data, employees included) · Feeds (continuous packaged streams) · Platforms (aggregate/normalize/enrich/automate). Figure 20.3 tiles a fifth, Professional Services, which the prose never defines — unasserted

Which providers does the prose name, and what is deliberately absent
?
Free/open-source sets, government (ENISA, US-CERT/AIS with verbatim quirks), and five commercial: Recorded Future, Broadcom, Team Cymru, Trellix, Anomali — with no prose Source URLs, so none asserted. AlienVault, CrowdStrike, Infragard, ISC, Proofpoint, ThreatStop, Talos are tile-only and out of scope

What does TC Complete do, and which TIP detail is verbatim garble
?
Ratings, team votes, and false-positive counts per indicator/incident; analyst efficiency. IBM X-Force's printed feature 'Integrated solution to help suddenly stop threats' is kept verbatim as likely OCR garble

State the Pyramid of Pain bottom→top with pain labels
?
Trivial Hash Values (SHAI/MD5 as printed, metamorphic, least significant) → Easy IP Addresses (VPN/proxy rotation) → Simple Domain Names (dynamic DNS services + domain-generated algorithms) → Annoying Network/Host Artifacts (rejection causes pain) → Challenging Tools (rebuild research) → Tough! TTPs (countering behaviors not tools, apex). Move up for resilience

What are the four hunting steps, and which is the success criterion
?
Create Hypothesis (models + existing-alerting note) → Investigate Via Tools and Techniques (raw + linked + ML merge) → Uncover New Patterns and TTPs (the definitive success criterion) → Inform and Enrich Analytics (automate outward). Hunter duties span insider/outsider/known/hidden threats plus IR-plan execution

State maturity levels 0–4 with their printed traits
?
0 Initial/HMMO: no collection, OSINT + lower-Pyramid data. 1 Minimal: alert-driven IR, TIP-enriched IOCs. 2 Procedural: others' processes — most organizations. 3 Innovative: own procedures, stats-to-ML fluency. 4 Leading: automated successes, continuous refinement. Criteria: collection, hypotheses, tools/techniques

What is OODA in this module, and which practice hosts it
?
Observe, Orient, Detect, Act — printed inside the threat-hunting best practices (know the environment, full visibility, track techniques, existing tools + ML speed, UEBA, internal/external scans, external hunters, dark web). Note the module's Detect-for-D: as printed, not the standard third term

Name four AI-in-TI use cases and the LLM exchange point
?
Summarization (LLMs condense volumes) · IOC extraction (unstructured social/dark-web) · TTP extraction (long research docs) · predictive intelligence (past → future posture) — plus alert generation, LLM-streamlined exchange (auto warnings/reports), decision support, real-time TI. Enrichment adds context to IPs/domains/hashes for impact-based prioritization

Which solution-name garbles does the vault preserve, and what are the six guidelines
?
Trellix tile tremx.com vs prose trellix.com · truncated https://www.ibm. vs https://www.ibm.com · WILF-IRE tile vs WILFIRE prose · recieve. Guidelines: proactive AI · embed in tooling · alert quality (false-positive rejection) · transparency/accountability (provenance) · CIA-prioritized resilience · bias supervision (diversity)

What does the module summary lock in
?
CTI as collection + analysis for preparedness/prevention/response · IOCs stop repeated-unchanged threats while IOAs catch new-modified ones · providers as communities or commercial bodies · goals-need-purpose before consuming TI
