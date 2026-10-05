---
type: moc
module: "19"
tags: [concept, process, tool, bestpractice, mod/19]
topic: "Module 19 — Threat Assessment with Attack Surface Analysis"
exam_weight: unknown
status: done
unresolved:
  - "p6 VS p7 ON WHO THE SURFACE IS OPEN TO. p6: interfaces 'accessible to an unauthenticated user'. p7 software surface: 'accessible to an authorized user'. Both wordings kept as printed."
  - "p7 PHYSICAL SECOND THREAT TYPE TRUNCATED after Insider threats; not stated in slice, omitted."
  - "p14 TWO SOURCE LINES PRINTED. Body gives https://attivonetworks.com/ while a garbled tile line prints a https://www.sentinelone.corn variant. Body form kept."
  - "p19 'IOE' VS 'IoE' CASING VARIES on the same page; the body uses both."
  - "p21 SOURCE PRINTS AS www.microsoft.com IN BODY vs https://www.microsoft.com in the figure caption; body form used."
  - "p25 THREE OWASP SOURCE VARIANTS: https://mwv.owasp.org vs https://www.owasp.org vs https://owasp.org. Body form https://owasp.org used."
  - "p25→26 THE ASD CAPABILITY SENTENCE IS CUT MID-LIST and continues on p26, which lives in the sibling note. Each note records its own half with a cross-link."
  - "pp26–27 ARE APPLICATION TAIL INSIDE THE NETWORK/HUMAN SLICE (ASD static-route parsing on p26, ThreatModeler on p27). Covered as-sourced with placement noted, not dropped."
  - "p28 THE ATTACKSURFACEMAPPER SOURCE LINE IS SPACED AS 'A ttackSurfoceMapper' so no URL is asserted. p29 Table 19.1 column mapping flattened by OCR — lists reproduced without column claims; 'IPv41nfo', 'Sublist3rAPl', 'Archivelt' kept as printed."
  - "p31 OHPHISH DASHBOARD NUMBERS ARE NON-EVIDENCE; figure URL garbled, body form www.shieldalliance.com used. p32 SPF Source is bare https://github.com with no repo path; p33 Phishing Frenzy is bare www.github.com. Both kept as printed. p33 prints 'hosing websites', likely hosting, kept verbatim."
  - "p36 FIGURE CAPTION PRINTS Source: https://www.akamai.com WHILE BODY PROSE PRINTS Source: www.guardicore.com. Prose form recorded with the discrepancy logged."
  - "p38 BAS TILE LISTS AttackIQ, CyCognito AND XM CYBER WITH PROSE; omitted per assignment scope (note covers Infection Monkey, Cymulate, Picus, SafeBreach, FireMon, WhiteHaX, PhishThreat). Recorded, not reconstructed."
  - "p43 OCR PRINTS 'SurfaceBrowserto' WITHOUT SPACE; rendered as SurfaceBrowser per the p47 clean form. p44 prints 'severs' for servers; quoted scope kept without the garbled token."
  - "pp46–47 ATTACK-METHODOLOGY AND ATTACK-CATEGORY TABLES HEAVILY GARBLED AND TRUNCATED; omitted per assignment scope."
  - "p50 TABLE/GRID OCR JUMBLED; row-to-example mapping taken from pp51–52 prose, not grid order. Participant-classes sentence truncated mid-phrase. p53 IoT table-start covered in full only in the sibling note."
  - "p54 IOT FOUR-COMPONENT MODEL TRUNCATED (Devices + Communication Channels printed; remaining two cut off). p55 Device Web Interface vector list truncated at 'SQL...' — scope only, no enumeration."
  - "SCREENSHOT AND FIGURE PAGES ARE NON-EVIDENCE THROUGHOUT: ThreatPath/Skybox captures (pp13–16), ASA captures and CLI transcript (pp21–22), Sandbox tiles (p23), Burp/ZAP screenshots (p25), ASD/ThreatModeler/ASM/amass figures (pp26–30), OhPhish dashboard (pp31–32). No dashboard number, tile label, CLI value or diagram label was read out of any of them."
---

[[MOC-Module-18]]

# Module 19 — Threat Assessment with Attack Surface Analysis

> [!abstract] Scope
> **6 LOs** · PDF pp. 4–59 (book pp. 2640–2695) · **60 pages** · 8 notes · 42 cards.
> What the attack surface is and its five categories → **visualizing** it (topologies,
> ThreatPath, Skybox) → **IoEs** per surface (system, application, network, human) →
> **attack simulation** (purpose, run, BAS tools) → **reducing** the surface (app, human,
> code, browser, ports) → **cloud** (six surfaces) and **IoT** (OWASP areas) → summary.
> **The shape trap:** analysis runs a fixed four-step pipeline — **Visualize → IoEs →
> Simulate → Reduce** — and every LO after LO#01 is one pipeline stage. Items asking
> "what comes next" test pipeline order, not tool trivia. The second trap is the
> surface taxonomy: **five** categories (network, software, physical, human, system),
> each with its own IoE toolset.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 19.1 | Attack surface analysis concept                     | 4–9     | 2640–2645   | 1 |
| LO02 | 19.2 | Understand and visualize the attack surface         | 10–17   | 2646–2653   | 1 |
| LO03 | 19.3 | Indicators of Exposure (IoEs)                       | 18–33   | 2654–2669   | 2 |
| LO04 | 19.4 | Attack simulation                                   | 34–41   | 2670–2677   | 1 |
| LO05 | 19.5 | Reduce the attack surface                           | 42–48   | 2678–2684   | 1 |
| LO06 | 19.6 | Cloud and IoT attack surface                        | 49–59   | 2685–2695   | 2 |

p59 is the Module Summary and is carried in `19-LO06b`. p60 is the intentionally-blank
page, p2 blank, p1 divider, p3 objectives — whose prose list prints all six subjects
cleanly against a damaged numbered column.

## Technical focus

- **LO01 — concept.** Attack surface = **sum of all possible exposures (known, unknown,
  potential)** through which an unauthorized user reaches assets; exposures span
  **protocols, interfaces, user input fields, services**, plus unpatched vulns, open
  ports, misconfiguration, excess privilege, bad segmentation, unaware employees.
  Smaller surface = less exploitable = less risk; standard practice keeps it **minimum**.
  Five categories (pp6–8): **Network** (HW/SW/firmware interfaces, unauthenticated;
  e.g. open ports on public IP) · **Software** (code/config/function profile; e.g.
  unvalidated inputs) · **Physical** (direct hardware; USB-enabled laptops, discarded
  drives) · **Human** (the **weakest point**; free-seekers, goodwill helpers, the
  manipulable; fake calls, lost media, trojaned legit sites) · **System** (OS entry
  points; more services = greater surface; unused Windows roles). Network detail (p7):
  **unencrypted Telnet, FTP, HTTP, SMTP** · **NFS, SMB** · **`netdump`** · printers.
  Software detail: Java/Adobe Reader/Flash unpatched. Analysis (p9) = **assessment of
  all exploitable vulnerabilities** in the target; finds review/test targets,
  defense-in-depth code, and change moments. Four steps in order: **Understand and
  Visualize → Identify IoEs → Simulate the Attack → Reduce the Surface**.
  _(Mod 19 pp4–9)_
  → [[19-LO01a-Attack-Surface-Analysis-Concept]]

- **LO02 — visualization.** Visualization = monitoring the surface; identify assets,
  **topologies, policies** (p59 triad). Mapped topology elements (p12): servers,
  data flows, vulnerable-asset access paths. Challenges (pp12–13): no correlation
  tooling, policy opacity, **security silos**. **ThreatPath** (pp14–15): lateral-movement
  topographical map, four defender actions, Fig 19.1 benefits incl. **early exposure
  detection**; `Source: https://attivonetworks.com/` (prose form). **Skybox** (pp16–17):
  true visibility statement, three key features; prose Source kept. Captures on
  pp13–16 = non-evidence. _(Mod 19 pp10–17)_
  → [[19-LO02a-Visualize-Attack-Surface-and-Tools]]

- **LO03 — IoEs.** **IoEs = potential risk exposures** attackers use to breach (p59).
  Identification (p20) incl. firewall-rule event example. **System** (pp21–24):
  **Attack Surface Analyzer** (9-component list, GUI/CLI/SQLite) · **Windows Sandbox
  Attack Surface Analysis Tool** (14-tool table verbatim: DumpProcessMitigations,
  NewProcessFromToken on Windows 8+). **Application** (pp25–27): **OWASP Attack
  Surface Detector** — endpoints, static route parsing (p26 lives in sibling),
  version diffs, ZAP/Burp/CLI, BApp Store (`Source: https://owasp.org`) ·
  **ThreatModeler** (channels, widgets, engine). **Network** (pp28–30):
  **AttackSurfaceMapper** (OSINT + active; enumeration triple; URL omitted as
  unprintable) · **amass** (definition, technique/source lists; Table 19.1 without
  column claims). **Human** (pp31–33): phishing-framework table — OhPhish, **SPF**,
  SoSafe, **SET**, PhishGrid, Frenzy, GoPhish — with bare-but-printed Sources.
  _(Mod 19 pp18–33)_
  → [[19-LO03a-IoE-System-and-Application-Surfaces]]
  [[19-LO03b-IoE-Network-and-Human-Surfaces]]

- **LO04 — simulation.** Purpose (p34): **validate and manage security controls**,
  **assess flaws before any attack**, recognize **how IoEs become exploits** and how
  the org looks to the attacker. Run (p35): org as **single unit**, one target
  (Network/Software/Application/Human); goal setting → recon → server/service
  attacks; social engineering, phishing simulation, exfiltration testing; **small
  input or change** answers five questions (exploit paths, asset moves, topology
  changes, policy add/remove, directional attacks). **BAS tools** run the virtual
  pentest. Tools, prose only: **Infection Monkey** (open-source; random-server
  infection, propagation paths) · **Cymulate** (one-click gap ID + fix guidance,
  **APT simulation**) · **PhishThreat** (train + test, 9 languages) · **Picus**
  (detection-tool testing, Mitigation Library, SIEM optimization) · **SafeBreach**
  (continuous real-world validation) · **FireMon** (change/compliance/behavior;
  Security Manager + Cloud Defense) · **WhiteHaX** (cloud-hosted readiness
  verification, cyber-insurance framing). _(Mod 19 pp34–41)_
  → [[19-LO04a-Attack-Simulation-and-Tools]]

- **LO05 — reduction.** ASR = **close all but needed doors**, restrict the rest;
  lowering vuln count lowers compromise likelihood. Scope: system, application,
  network, human, physical. **Application**: kill redundant functions, entry
  points, **APIs**, code, complexity — **simplest code, least assumptions**.
  **Browser list** (p45, as printed): disable firewall traversal, network
  prediction, cloud-peripheral sharing, data sync, pop-ups, 3D APIs, JS
  everywhere, autocomplete, session-only cookies, background processing, search
  suggestions, metrics, incognito, cleartext passwords, password manager,
  saved-password import, outdated plugins, auto plugin install/execution,
  third-party cookies, desktop notifications — enable revocation checks, safe
  browsing; set provider/homepage/auth scheme, plugin whitelists, encryption.
  **Ports**: open-everything widens the surface; **audit before the attacker**
  with **Nmap**, plus Unicornscan, Angry IP Scanner, Netcat. **Human**: periodic
  policy/social-engineering/physical-security training → CIA preservation;
  six-question program (what/why/where-policies/how-protect/regulations/
  incident-effects). _(Mod 19 pp42–48)_
  → [[19-LO05a-Reduce-the-Attack-Surface]]

- **LO06 — cloud and IoT.** Cloud/IoT growth = more endpoints to protect. Three
  participant classes (p50): **service users, service instances/services, cloud
  provider**; interactions involve ≥2. Six cloud surfaces (pp51–52): **Service to
  User** (client-server attacks: buffer overflow, SQLi) · **User to Service**
  (browser/cache/phishing) · **Cloud to Service** (instance-vs-host: resource
  exhaustion) · **Service to Cloud** (provider-vs-instance — **most critical**)
  · **Cloud to User** (control-plane view) · **User to Cloud** (fake usage bills).
  Seven reduction recommendations (p52): map **all** assets · single-view
  infra mapping · vuln/misconfig/threat ID · local + cloud controls · **every**
  endpoint · **all** data repositories · provider contract **before the SLA**.
  IoT surface = vulnerabilities/threats of IoT + apps + devices (p53); OWASP
  areas (`Source: https://www.owasp.org`): **Ecosystem Access Control**
  (enrollment, implicit trust) · **Device Memory** (clear-text credentials,
  cipher keys) · **Physical Interfaces** (firmware extraction, console CLI) ·
  **Web Interface** (scope only — vector list truncated) · **Firmware**
  (hardcoded/default credentials, botnets) · **Network Services** (injection,
  DoS, MitM, overflow) · **Administrative Interface** (SQLi, XSS, enumeration,
  weak passwords, lockout) · **Local Storage** (unencrypted, found keys, no
  integrity) · **Cloud Web Interface** (no 2FA) · **Third-Party Backend APIs**
  (PII/location leaks) · **Update Mechanism** (unsigned/unencrypted/writable)
  · **Mobile App** (implicit trust) · **Vendor Backend APIs** (weak auth) ·
  **Ecosystem Communication** (one failure cascades) · **Network Traffic**
  (LAN/short-range/non-standard). IoT recommendations (p58): Secure-by-Design
  purchase · pre-connect risk review · secure configuration · feature
  minimization · segmentation + IAM + remote access · physical protection ·
  continuous monitoring. _(Mod 19 pp49–59)_
  → [[19-LO06a-Cloud-Attack-Surface]]
  [[19-LO06b-IoT-Attack-Surface-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 19 sits in blueprint domain 8 **Incident Prediction =
  15%** shared with modules 17, 18, 20 — see [[quiz.html]]. The bank uses a **flat 5
  per module**.
- Strong question sources, in rough order of yield:
  - **The four-step pipeline in order** — Visualize → IoEs → Simulate → Reduce.
  - **The surface definition** — sum of known/unknown/potential exposures.
  - **The five categories with examples** — especially Human as weakest and the
    unauthenticated-network vs authorized-software wording.
  - **The unencrypted-protocol list** — Telnet, FTP, HTTP, SMTP (+ NFS/SMB/netdump).
  - **Per-surface IoE tools** — Analyzer/Sandbox, OWASP ASD, AttackSurfaceMapper,
    amass, SPF/SoSafe/SET.
  - **Simulation purpose + the five small-change questions** and the BAS tool set
    (Infection Monkey random-server, Cymulate one-click + APT, PhishThreat 9
    languages).
  - **The browser-hardening disable list** and the port-audit trio (Nmap first).
  - **The six cloud surfaces**, especially Service-to-Cloud as most critical and
    the fake-bill User-to-Cloud example.
  - **The IoT area table** — default credentials (firmware), no-2FA cloud
    interface, unsigned updates, implicit-trust mobile app.
  - **The seven cloud + seven IoT recommendations**, especially contract-before-SLA
    and Secure-by-Design purchase.
- Deliberate distractors to expect:
  - **"The surface counts only known vulnerabilities"** — known, unknown,
    **and potential**.
  - **"Analysis implements the fixes"** — assessment only; reduction implements.
  - **"Simulation targets the whole org at once"** — single unit viewed, one
    target attacked.
  - **"ASD capabilities live entirely on p25"** — the sentence continues on p26.
  - **"AttackIQ/CyCognito/XM Cyber are detailed in the notes"** — tile-only,
    deliberately omitted per scope.
  - **"pp46–47 tables give clean attack rows"** — garbled and omitted.
  - **"The AttackSurfaceMapper URL is X"** — unprintable in source; omitted.
  - **Any dashboard number, CLI transcript value, or tile label** — non-evidence
    throughout.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-19")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/19-threat-assessment-with-attack-surface-analysis-map.canvas|Threat Assessment with Attack Surface Analysis Map]]
- Flow to visualize: **definition** (sum of exposures → five categories → protocol
  and software detail) → **visualize** (assets/topologies/policies → ThreatPath →
  Skybox) → **IoEs** (system → application → network → human, one toolset each) →
  **simulate** (purpose → run → five questions → BAS tools) → **reduce** (app →
  browser → ports → human) → **cloud** (participants → six surfaces → seven
  recommendations) → **IoT** (OWASP areas → seven recommendations).

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-18]] (Risk Management — the vulnerabilities this
  module exposes) · [[MOC-Module-20]] (Threat Intel — the IoCs/IOAs behind the
  exposures) · [[MOC-Module-16]] (Incident Response — where exposures materialize)
  · [[MOC-Module-04]] (Network Perimeter Security — the ports and segmentation this
  module audits).

## Unresolved
- **p6 vs p7 disagree on who the surface is open to** (unauthenticated vs authorized).
- **p7 second physical threat type truncated.**
- **p14 dual Source lines** — body form kept, tile garble logged.
- **p19 IOE/IoE casing varies** on one page.
- **p21/p25/p27 Source-variant trios** — body forms used throughout.
- **p25→26 ASD sentence split across notes**, each half cross-linked.
- **pp26–27 application tail inside the network/human slice**, placement noted.
- **AttackSurfaceMapper URL unprintable; Table 19.1 flattened; Fig 19.7 prose-free.**
- **Bare github.com Sources and 'hosing' kept verbatim.**
- **akamai-vs-guardicore Source conflict logged; BAS tile trio omitted per scope.**
- **SurfaceBrowserto/severs rendered from clean forms; pp46–47 tables omitted.**
- **p50 grid jumbled (prose mapping used); IoT model and Web-Interface list truncated.**
- **All figure/dashboard/CLI captures non-evidence** — 15+ locations listed in
  frontmatter.
- **Deliberately not guessed**: the p7 second threat · ASD column claims · any CLI
  or dashboard value · tile-only BAS vendors · garbled-table rows · truncated
  vector/component lists.

## Quick review
How many learning objectives does module 19 have, and what is LO#03's span
?
Six. LO#01 analysis concept · LO#02 visualize · LO#03 IoEs (pp18–33, book pp2654–2669) · LO#04 simulation · LO#05 reduce · LO#06 cloud and IoT

What is the attack surface, and what are its five categories
?
The sum of all possible exposures — known, unknown, and potential — through which an unauthorized user reaches assets, spanning protocols, interfaces, input fields, services, unpatched vulns, open ports, misconfiguration, excess privilege, bad segmentation, and unaware employees. Network (unauthenticated interfaces) · Software (code/config) · Physical (direct hardware) · Human (the weakest point) · System (OS entry points, more services = greater surface)

Which four protocols does the page name as passing unencrypted data
?
Telnet, FTP, HTTP, and SMTP — plus NFS and SMB file systems and the netdump remote memory dump service. Network printers are listed alongside

State the four-step analysis pipeline in order
?
Understand and Visualize the attack surface → Identify the Indicators of Exposures (IoEs) → Simulate the Attack → Reduce the Attack Surface. Analysis itself only assesses; reduction implements

Which IoE tool belongs to each surface
?
System: Attack Surface Analyzer and the Windows Sandbox Attack Surface Analysis Tool. Application: OWASP Attack Surface Detector (plus ThreatModeler). Network: AttackSurfaceMapper and amass. Human: phishing frameworks SPF, SoSafe, SET (plus OhPhish, PhishGrid, Frenzy, GoPhish in the table)

What is the point of attack simulation, and what five questions does a small change answer
?
Validate and manage security controls, assess flaws before any attack, and recognize how IoEs become exploits / how the org looks to the attacker — via virtual pentesting of one target (Network/Software/Application/Human). A small input or change answers: how exposures become exploits · asset-move effects · topology/routing-change effects · policy add/remove effects · directional-attack results

Name three BAS tools and what the page says each does
?
Infection Monkey (open-source, infects a random Cloud/on-prem server, walks propagation paths) · Cymulate (one-click gap ID with fix guidance, APT simulation) · Picus (detection-tool effectiveness testing, Mitigation Library, SIEM optimization). Also: SafeBreach (continuous real-world validation), FireMon (change/compliance/behavior), WhiteHaX (cloud-hosted readiness verification), PhishThreat (train + test, 9 languages)

What does application ASR remove, and what is the code-simplicity rule
?
Redundant and unnecessary functionalities, entry points, APIs, code, and complexity. The simplest code with the least assumptions avoids bigger attack surfaces — audit and eliminate redundancies

What are the port-audit and human-ASR directives
?
Audit network ports with Nmap before the attacker scans them; Unicornscan, Angry IP Scanner, and Netcat are the other named scanners; close all unnecessary ports on public IPs. Human: periodic policy/social-engineering/physical-security training preserving CIA against phishing — the program answers what/why/where-policies/how-protect/regulations/incident-effects

Which cloud surface is most critical, and what are the other five
?
Service to Cloud — all provider-on-instance attack types, easy to exploit with high impact. The rest: Service to User (client-server attacks) · User to Service (browser/cache/phishing) · Cloud to Service (instance-on-host exhaustion) · Cloud to User (control-plane view) · User to Cloud (fake usage bills)

Name four IoT areas and their printed example vulnerabilities
?
Ecosystem Access Control (implicit component trust, enrolment flaws) · Device Memory (clear-text credentials, cipher-key monitoring) · Firmware (hardcoded/default credentials, credential botnets) · Administrative Interface (SQLi, XSS, enumeration, weak passwords, lockout). Also: physical extraction/console CLI · network-service injection/DoS/MitM · unsigned updates · implicit-trust mobile app · PII-leaking backend APIs · no-2FA cloud web interface

What do the cloud and IoT recommendation lists most stress
?
Cloud: map all assets and both infrastructures, know every vuln/misconfig/threat, control local + cloud, protect every endpoint and repository — and read the provider contract before the SLA. IoT: Secure-by-Design purchase, pre-connect risk review, secure configuration, feature minimization, segmentation/IAM/remote-access, physical protection, continuous monitoring
