---
type: moc
module: "13"
tags: [concept, mod/13]
topic: "Module 13 — Enterprise Wireless Network Security"
exam_weight: unknown
status: done
unresolved:
  - "p37 Table 13.2 WPA3 IV Size cell OCRs as 'Arbitrary length I- 264' / '1- 264' — the exponent base was lost in OCR. The table is printed TWICE on p37 (before and after the explanatory prose) and both passes give exactly four cell values per row label in WEP→WPA→WPA2→WPA3 order, so the row alignment IS recoverable and the note builds the table. The single garbled cell is left verbatim and NOT completed to 2^64."
  - "p77 MODULE SUMMARY CONTRADICTS THE MODULE BODY, three ways. (1) Bullet 1 says 'A wireless network uses the IEEE standard of 802.11', but bullet 2 then places 'wireless standards such as Bluetooth, Wi-Fi' side by side for the AP to connect devices. (2) The summary names only WPA as the encryption method, while p56 ranks WPA3 first and WPA2 second. (3) The summary omits WPA2/WPA3/WEP from its encryption discussion entirely. Reproduced as printed in [[13-LO04l-Additional-Guidelines-and-Module-Summary]]."
  - "p49 vs p50 THE SECURITY-MEASURES LIST HAS TWO DIFFERENT LENGTHS. The p49 slide lists 15 activities; the p50 body lists 13. 'Implement WEP 128 enhanced encryption protocol combination of 104-bit & 24-bit key' and 'Update to the latest available firmware' appear on p49 ONLY and are dropped on p50; p50 also loses p49's ': interference' qualifier on the DoS item. Both lists kept."
  - "p59 SELF-CONTRADICTION ON WPA PASSPHRASE LENGTH, both printed on the same page: the body rule list says 'at least 12 characters', the Passphrase Complexity callout says 'a minimum of 20 characters'. High exam value; neither is treated as authoritative."
  - "p33 WPA2-PERSONAL KEY SIZE: the callout says a 128-bit key derived from an 8-63 ASCII-character passphrase; the body on the SAME page says 'the same 256-bit key generated from a password'. Direct contradiction, unreconciled."
  - "p37 vs p35 WPA3: Table 13.2 gives WPA3 a 192-bit key length, while p35 describes 256-bit GCMP-256. Separately p35 names TKIP among WPA3's algorithms although p31 defines TKIP as the WPA cipher and Table 13.2 lists no TKIP under WPA3."
  - "p56 THE TWO ORDER-OF-PREFERENCE LISTS DISAGREE WITH EACH OTHER. WEP ranks 7th of 7 in the 'encryption mode' list but 6th of 7 in the 'Wi-Fi security method' list, and 'Open Network (no security at all)' exists only in the second."
  - "p49 vs p56 WEP AS A HARDENING MEASURE: p49 lists 'Implement WEP 128 enhanced encryption protocol' as an activity that defends wireless security, while p56 ranks WEP last of seven modes. Both printed."
  - "p73 vs p74 ROUTER HARDENING LISTS DIFFER: the p73 slide has 5 settings, the p74 body has 11, and 'Enable logging' appears on p73 but is ABSENT from the eleven."
  - "p57 THE CLOSED/OPEN MAC-FILTER DEFINITIONS ARE INVERTED relative to everyday usage: 'In a closed MAC filter, only the listed addresses are permitted' and 'In an open MAC filter, the addresses listed are prevented'. Reproduced verbatim as printed."
  - "p63 vs p60 WHAT A WIDS IS: p60 says 'dedicated systems or software that continuously monitor wireless network traffic'; p63 says 'WIDS are wireless access points that detect and alert... it scans for rouge devices every few milliseconds'. Both printed."
  - "WIDS/WIPS NAMING HAS FOUR FORMS across the module: 'prevention system' (p72 heading), 'protection systems' (p72 body), 'WIDS = wireless access points' (pp60/63), and 'wireless INTRUDER detection-prevention system (WIDPS)' (p75)."
  - "p25 says 'There are FIVE types of wireless antennas' but eight are then described across pp25-27. p25 also defines gain as 'the ratio of the power INPUT to the antenna to the power OUTPUT from the antenna' — the reverse of the usual ratio; kept verbatim because the wording is exam-relevant. p24 places antennas at '960 MHz to 1215 MHz' with '1200 W peak and 140 W on an average', incompatible with the 2.4/5 GHz Wi-Fi bands given on pp7-8. All three quoted, none corrected."
  - "pp10-11 THE THREE STANDARDS TABLES ARE UNRECONSTRUCTABLE: the OCR reads them column-by-column and row alignment is lost (p10 t1 has 4 frequency values for 3 row labels; p10 t2 has 10 bandwidth values for 5 rows; p11 has 7 row labels but only 4 description cells). They are NOT rebuilt as a table. The exam-answerable content is the clean pp11-13 prose, which carries the note's tables."
  - "p15 the block headed 'key characteristics of an AD-HOC wireless network' lists three items that all describe an ACCESS POINT, contradicting p14's definition of ad-hoc mode as having no AP. Reproduced verbatim under an explicit caveat."
  - "p39 'A busy AP can use all 224 available IV values within hours' — printed as 224, left as printed and NOT corrected to 2^24. p40's 'Hole 96 vulnerability in WPA2' is a garbled vendor identifier with no expansion, CVE or year anywhere in the module; quoted, not mapped to any real CVE."
  - "p46 gives the shared-key challenge-text key size as '64-bit or 128-bit' — a THIRD distinct key-size set in the module, alongside WEP's 40/104/128/232-bit (p29) and the '140-bit WEP key' on p31. Never reconciled by the courseware."
  - "Per-module exam blueprint weights are not stated in the courseware. Module 13 sits in domain 5 'Enterprise Virtual, Cloud, and Wireless Network Protection' (15%, 15 of 100) shared with modules 11 and 12 — see [[quiz.html]]. The bank uses a flat 5 items per module."
  - "OCR/screenshot gaps: pp55, 56, 57, 59, 73-74 are walkthrough screenshots treated as NON-EVIDENCE — no UI text was read from any of them. p20's component figure has 9 labels but only 5 description cells with no binding, so labels were NOT paired. p16's figure caption OCRs as 'use 46 Hot»ot G Connection Cen 4G Hotspot' and was not used."
---

[[MOC-Module-12]]

# Module 13 — Enterprise Wireless Network Security

> [!abstract] Scope
> **4 LOs** — this module has four, not nine · PDF pp. 4–77 (book pp. 2052–2125) · **78 pages,
> the smallest of the three domain-5 modules** · 28 notes · 157 cards.
> Wireless fundamentals (terminologies, 802.11 standards, topologies, components, antennas) →
> encryption (WEP → WPA → WPA2 → WPA3, and why each earlier one fails) → authentication (open
> system, shared key, centralized server) → the security measures themselves, which is the bulk of
> the module and the most exam-dense part.
> **The shape trap:** this module is built as a *retirement narrative*. Every encryption note exists
> to be superseded by the next one, and the `Issues in` note is where the exam value concentrates.
> Learn WEP not as a working protocol but as the answer to "why is it broken."

## Sections
| LO   | §    | Section                                          | PDF pp. | Book pp.    | Notes |
| ---- | ---- | ------------------------------------------------ | ------- | ----------- | ----- |
| LO01 | 13.1 | Fundamentals of Wireless Networks                | 4–27    | 2052–2075   | 6 |
| LO02 | 13.2 | Encryption Mechanisms Used in Wireless Networks   | 28–43   | 2076–2091   | 7 |
| LO03 | 13.3 | Authentication Methods Used in Wireless Networks  | 44–47   | 2092–2095   | 3 |
| LO04 | 13.4 | Security Measures for Wireless Networks           | 48–76   | 2096–2124   | 12 |

p77 is the Module Summary and is carried in `13-LO04l`. pp. 2 and 78 are the intentionally-blank
pages, p1 the module divider, p3 the objective list.

## Technical focus

- **LO01 fundamentals.** Terminologies: **OFDM** (orthogonal frequency-division multiplexing),
  **SSID** (32 alphanumeric characters), WLAN, RF. Technology types: **Wi-Fi** vs wired. Standards
  across pp. 10–13: the **802.11 family** (a, b, g, n, ac, ad) plus **802.12**, **802.15** (1 and 4)
  and **802.16** (WiMax). Topologies: **ad-hoc** vs **standalone/infrastructure**, typical uses
  (extension to a wired LAN, etc.), and **WMAN**. Components: **AP**, **wireless NIC cards**
  (PC card / PCI / mini-PCI), **wireless router**, **antenna**, **wireless controller**.
  Antennas: gain, the types described across pp. 25–27, and their characteristics.
  → [[13-LO01a-Wireless-Fundamentals-and-Terminologies]] [[13-LO01b-Types-of-Wireless-Technologies]]
  [[13-LO01c-Wireless-Network-Standards]] [[13-LO01d-Wireless-Network-Topologies]]
  [[13-LO01e-Components-of-a-Wireless-Network]] [[13-LO01f-Wireless-Antennas]]

- **LO02 encryption — the core.** **WEP**: defined by the **802.11b** standard; a **24-bit IV** added
  to the key, and key + IV = the **WEP seed**; the seed is the input to **RC4**, whose keystream is
  **XOR**ed with data + **ICV**; **CRC-32** produces the ICV. The **64/1280/256-bit WEP versions use
  40/104/232-bit keys** (p29). **WPA**: introduces **TKIP**; the four-way handshake. **WPA2**:
  mandatory **CCMP** (counter-mode CBC-MAC) with **AES**, replacing WPA in **2006**; two modes —
  **WPA2-Personal** (PSK, home networks) and **WPA2-Enterprise** (EAP/RADIUS, centralized
  authentication using token cards, Kerberos, certificates). **WPA3**: **AES-GCMP-256**, natural
  password choice, secured IoT connections. Table 13.2 comparison — encryption algorithm
  **RC4 · RC4+TKIP · AES-CCMP · AES-GCMP**; IV size **24 / 48 / 48 / arbitrary**; key length
  **40-104 / 128 / 128 / 192 bits**; key management **none · 4-way handshake · 4-way handshake ·
  ECDH and ECDSA**; integrity **CRC-32 · Michael + CRC-32 · CBC-MAC · BIP-GMAC-256**.
  **Wi-Fi Easy Connect / DPP** closes the section. → [[13-LO02a-WEP-Encryption]]
  [[13-LO02b-WPA-Encryption]] [[13-LO02c-WPA2-Encryption]] [[13-LO02d-WPA3-Encryption]]
  [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]]
  [[13-LO02g-Wi-Fi-Easy-Connect-DPP]]

- **LO02 weaknesses — highest exam density in the module.** **WEP's problems** (pp. 30, 38–39):
  **CRC-32 insufficient** for cryptographic integrity — an attacker flipping a bit can modify the
  checksum so the packet is accepted; **24-bit IVs are too small and sent in cleartext** — an AP
  broadcasting 1500-byte packets at 11 Mb/s exhausts the IV space in **five hours**; **known-plaintext
  attacks** on IV collision; **dictionary attacks**; **DoS** — associate/disassociate messages are
  unauthenticated; about **24 GB** of reconstructed key stream allows **real-time** decryption; no
  **centralized key management**. **WPA's issues** (p40): weak password; **lack of forward
  secrecy**; vulnerable to **packet injection and decryption**, allowing TCP hijacking; **predictable
  group temporal key (GTK)** via an insecure RNG; **IP-address guessing** via TKIP vulnerabilities.
  **WPA2's issues** (pp. 40–41): weak password (eavesdropping, dictionary, cracking); lack of forward
  secrecy; **man-in-the-middle**; **wireless DoS** by exploiting replay-attack detection with forged
  group-addressed frames carrying a large **PN**; **WPS PIN recovery** exposes the WPA2 key.
  → [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]]

- **LO03 authentication.** **Open System**: any wireless device can be authenticated with the AP —
  "anyone who knows the SSID can easily access"; transmits in **cleartext**. **Shared Key**: the
  station and AP hold a shared key; only a **Disadvantage** is printed. **Centralized
  authentication** (802.1x/EAP/RADIUS): users are assigned login credentials by a centralized
  server which they must present when connecting. Note the courseware **never defines EAP** and
  prints **no port number** for the uncontrolled port. → [[13-LO03a-Open-System-Authentication]]
  [[13-LO03b-Shared-Key-Authentication]] [[13-LO03c-Centralized-Authentication-Server]]

- **LO04 security measures.** The canonical list: **create an inventory of wireless devices · place
  the AP and antenna · disable SSID broadcasting · select a strong encryption mode · enable MAC
  filtering · monitor wireless traffic · defend against WPA cracking · detect rogue APs · locate
  rogue APs · protect from DoS/interference · assess wireless security · deploy WIDS/WIPS ·
  configure router security** (plus p49's two extra items). A **wireless security policy** must
  state identity of users, who may install APs, what may be transmitted, AP limitations (location,
  cell size, frequency), standard security settings, and when devices may use the network.
  **Order of preference** (p56): **WPA3 → WPA2 Enterprise with RADIUS → WPA2 Enterprise → WPA2 PSK →
  WPA Enterprise → WPA → WEP**. **Rogue AP** techniques: **WIDS · wireless site surveys · signal
  strength analysis · MAC address monitoring**, with tools **inSSIDer, NetSurveyor, NetStumbler,
  Vistumbler, Kismet**, plus **Nmap** for wired scanning and **SNMP polling** (SolarWinds SNMP
  Scanner, Lansweeper SNMP Scanner) — SNMP must be enabled on IP devices. Assessment tools:
  **NetSpot, Ekahau, AirMagnet, CommView for WiFi, Wi-Fish, Aircrack-ng, WEPCrack**. WIDS/WIPS
  products: **Cisco Adaptive WIPS**, **Extreme AirDefense**. → [[13-LO04a-Security-Measures-and-Wireless-Inventory]]
  [[13-LO04b-AP-and-Antenna-Placement]] [[13-LO04c-Disable-SSID-Broadcasting]]
  [[13-LO04d-Strong-Wireless-Encryption-Mode]] [[13-LO04e-MAC-Address-Filtering]]
  [[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]] [[13-LO04g-Rogue-Access-Point-Detection]]
  [[13-LO04h-RF-Interference-Protection]] [[13-LO04i-Wireless-Security-Assessment-Tools]]
  [[13-LO04j-WIDS-WIPS]] [[13-LO04k-Router-Administrative-Security]]
  [[13-LO04l-Additional-Guidelines-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 13 sits in blueprint domain 5 **Enterprise Virtual, Cloud, and
  Wireless Network Protection = 15%** (15 of 100) shared with modules 11 and 12 — see [[quiz.html]].
  The bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield:
  - **Table 13.2**, row by row. The four algorithms, the four IV sizes, the four key lengths, the
    four key-management schemes, and the four integrity mechanisms are all directly examinable.
  - **The p56 order of preference** — WPA3 first, WEP last — and the seven-mode list.
  - **WEP's failure modes**, each with its printed quantity: **five hours** to exhaust the IV
    space, **24 GB** for a real-time decryption table, **CRC-32**, **24-bit IV in cleartext**.
  - **WPA2's two distinctive attacks**: the **wireless DoS** via forged group-addressed frames with
    a large **PN**, and **WPS PIN recovery** disclosing the WPA2 key.
  - **WPA's GTK predictability** and **TKIP IP-address guessing** — the two issues unique to WPA.
  - **WEP mechanics**: seed = key + IV, input to **RC4**, keystream XORed with data + ICV,
    **CRC-32** ICV, versions **40/104/232-bit** keys.
  - **WPA2-Personal vs WPA2-Enterprise** — PSK for home networks, EAP/RADIUS with token cards,
    Kerberos and certificates for centralized authentication.
  - **The rogue-AP technique set** — WIDS, site surveys, signal strength analysis, MAC monitoring —
    and the tool names attached to each.
  - **Named tools the exam may probe**: NetStumbler, Nmap (`-A` option), AirCheck G2 Wi-Fi Tester,
    Ekahau Spectrum Analyzer, AirMagnet, CommView for WiFi, Wi-Fish, Cisco Adaptive WIPS,
    Extreme AirDefense, SolarWinds SNMP Scanner, Lansweeper SNMP Scanner.
  - **Trivia-looking items that are printed and therefore fair**: the **passphrase** rules, **SSID =
    32 characters**, the **960 MHz–1215 MHz** antenna band, the **48-bit** WPA/WPA2 IV size, and
    the **UK Data Protection Act** analogue from the checklist-style guidelines.
- Deliberate distractors to expect:
  - **"WPA3 uses a 192-bit key"** — true of Table 13.2, but p35 describes **256-bit GCMP-256**. Both
    printed; the module never reconciles them.
  - **"WEP is a recommended hardening measure"** — p49 lists it; p56 ranks it **last of seven**.
  - **"WEP's IV space allows 2^24 values, so exhaustion takes long"** — the module says an AP
    exhausts it in **five hours**, and separately prints **224** on p39. Use the five-hours figure.
  - **"Open System Authentication provides security because it checks the WEP key"** — any device
    can authenticate; the SSID alone grants access.
  - **"EAP is Extensible Authentication Protocol, defined in this module"** — LO03 never expands it.
  - **Confusing WIDS and WIPS** — the courseware never states what separates them.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-13")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/13-enterprise-wireless-network-security-map.canvas|Enterprise Wireless Network Security Map]]
- Flow to visualize: RF/WLAN/SSID basics → 802.11 standards and topologies → AP, NIC, router, antenna, controller → **encryption ladder**, each rung superseding the last (`WEP (RC4 + CRC-32, 24-bit IV) → WPA (TKIP + 4-way handshake) → WPA2 (AES + CCMP, PSK | Enterprise/EAP-RADIUS) → WPA3 (AES-GCMP-256)`), with **Table 13.2** as the convergence point → **why the earlier rungs fail** (IV exhaustion, CRC-32, dictionary/known-plaintext, no forward secrecy, GTK predictability, WPS PIN recovery) → **authentication** (open system · shared key · centralized server) → the **security-measures ladder**: inventory → placement → hide the SSID → choose the strongest mode → MAC filter → monitor → defend against cracking → detect and locate rogue APs → RF interference → assess → WIDS/WIPS → harden the router → guidelines.

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-11]] and [[MOC-Module-12]] (same blueprint domain 5 — enterprise
  virtual, then enterprise cloud) · [[MOC-Module-03]] (technical network security — the encryption,
  tunneling and monitoring fundamentals wireless inherits) · [[MOC-Module-04]] (network perimeter
  security — the firewall/WAF placement questions in the guidelines) · [[MOC-Module-07]] (endpoint
  security — mobile devices join the same wireless networks) · [[MOC-Module-10]] (data security —
  encryption and key management, the thread running through LO02).

## Unresolved
- **The p77 Module Summary contradicts the module body three ways** — Bluetooth placed alongside
  Wi-Fi as a WLAN standard, WPA named as *the* encryption method, WPA2/WPA3 omitted (see frontmatter).
- **The p49 vs p50 security-measures list differs in length** — 15 items vs 13 (see frontmatter).
- **p59 contradicts itself on passphrase length** — 12 characters vs 20, on one page (see frontmatter).
- **p33 contradicts itself on the WPA2-Personal key size** — 128-bit vs 256-bit (see frontmatter).
- **p37 vs p35 disagree on the WPA3 key length** — 192-bit vs 256-bit GCMP-256 (see frontmatter).
- **p56's two order-of-preference lists disagree** — WEP 7th vs 6th (see frontmatter).
- **p73 vs p74 router-hardening lists differ** — 5 settings vs 11, and `Enable logging` is dropped (see frontmatter).
- **p57's closed/open MAC-filter definitions are inverted** vs everyday usage (see frontmatter).
- **p60 vs p63 disagree on what a WIDS is** (see frontmatter).
- **WIDS/WIPS is spelled four different ways** across the module (see frontmatter).
- **p25 says five antenna types then describes eight**, reverses the gain ratio, and p24 gives an
  antenna band and power figures incompatible with the Wi-Fi bands (see frontmatter).
- **The pp. 10–11 standards tables are unreconstructable** and were not rebuilt (see frontmatter).
- **p15 mislabels AP characteristics as ad-hoc** (see frontmatter).
- **p39 prints `224` IV values** and p40 prints an unexpandable `Hole 96 vulnerability`; both left as
  printed (see frontmatter).
- **p46's `64-bit or 128-bit` challenge key is a third distinct key-size set** in the module (see frontmatter).
- **Three key facts could NOT be recovered and are absent from every note**: the port number of the
  802.1X uncontrolled port; any expansion or definition of **EAP**; and the real identity behind
  `Hole 96`.
- **Screenshot walkthroughs on pp. 55, 56, 57, 59, 73–74 are non-evidence** — no UI text was read from
  them, and the p20 component figure's labels were not paired to descriptions.

## Quick review

How many learning objectives does module 13 have, and which four?
?
Four — fundamentals of wireless networks (pp. 4–27) · encryption mechanisms (pp. 28–43) · authentication methods (pp. 44–47) · security measures (pp. 48–76). The p77 Module Summary is carried in 13-LO04l

WEP's core mechanism, in order
?
A 24-bit IV is added to the WEP key; key + IV = the WEP seed; the seed is the input to RC4, which generates a keystream; the keystream is XORed with data + the ICV; CRC-32 computes the 32-bit ICV

The three WEP versions and the key length each uses
?
64-bit WEP uses a 40-bit key · 128-bit uses 104-bit · 256-bit uses 232-bit (p29)

Two printed quantities that quantify how badly WEP fails
?
An AP broadcasting 1500-byte packets at 11 Mb/s exhausts the entire IV space in five hours · about 24 GB of reconstructed key stream lets an attacker decrypt WEP packets in real time

The order of preference for choosing an encryption mode
?
WPA3 → WPA2 Enterprise with RADIUS → WPA2 Enterprise → WPA2 PSK → WPA Enterprise → WPA → WEP

The two WPA2 authentication modes and what each is for
?
WPA2-Personal (PSK) — home networks, no authentication server · WPA2-Enterprise — EAP or RADIUS for centralized client authentication using token cards, Kerberos, certificates

The four key-management values in Table 13.2
?
WEP None · WPA 4-way handshake · WPA2 4-way handshake · WPA3 ECDH and ECDSA

The three WPA-specific issues that WPA2 fixes
?
Predictable group temporal key via an insecure RNG · TKIP vulnerabilities allow IP-address guessing and packet injection · lack of forward secrecy

The two issues printed only under WPA2
?
Wireless DoS — attackers exploit WPA2 replay-attack detection to send forged group-addressed data frames with a large PN · Wi-Fi protected setup PIN recovery — with WPA2 and WPS enabled the attacker can disclose the WPA2 key from the WPS PIN

The four techniques for detecting rogue access points
?
Wireless intrusion detection systems (WIDS) · wireless site surveys · signal strength analysis · MAC address monitoring

Which tool finds rogue APs on the wired network, and which SNMP prerequisite does it need
?
Nmap (the -A option scans the entire address space) · SNMP polling requires the SNMP service enabled on all IP devices in the network; SolarWinds SNMP Scanner and Lansweeper SNMP Scanner are the named utilities

Two facts the module names about open system authentication
?
Any wireless device can be authenticated with the AP, and transmission is permitted only when its WEP key matches the AP's — but it transmits in cleartext, so anyone who knows the SSID can easily access the network