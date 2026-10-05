---
type: moc
module: "14"
tags: [tool, process, mod/14]
topic: "Module 14 — Network Traffic Monitoring and Analysis"
exam_weight: unknown
status: done
unresolved:
  - "p114 THE MODULE SUMMARY OMITS LO#06 ENTIRELY. Six bullets cover the baseline, signature analysis, Wireshark, packet loss, bandwidth and traffic monitoring — but anomaly detection, NBAD, NBA, UBA and UEBA (pp. 78–113, a third of the module) appear nowhere in either the coverage sentence or any bullet. This is the largest structural defect in the module and it makes the summary useless for LO#06 revision. Reproduced as printed in [[14-LO06g-UBA-vs-UEBA-and-Module-Summary]]."
  - "p113 CONTRADICTS p99 ON UBA TWICE. p113 says UBA 'relies on event logs' and 'is a stand-alone' that 'cannot integrate with existing security systems'; p99 says UBA collects data from multiple sources and analyses network logs in SIEM/log-management systems. The UBA-vs-UEBA table is the exam-likely form of the p113 text; neither version is treated as authoritative."
  - "p79 NBAD is expanded two different ways on one page: 'Network Behavior Anomaly Detection' and 'network anomaly detection and behavior analysis'. The module title band uses a third form, 'network anomaly detection with behavior analysis'."
  - "p79 vs p80 flowmon URL conflict: the band prints https://www.fbwmm.com/, the body prints https://www.flowmon.com/. Body used; band variant recorded."
  - "p83 Cisco product name conflict: band prints 'Cisco SECURITY Network Analytics', body prints 'Cisco SECURE Network Analytics'. Body used."
  - "p74 vs p75 SolarWinds product name conflict: p74 side bar says 'SolarWinds Bandwidth Monitor', the p75 heading says 'SolarWinds Real-Time Bandwidth Monitor'. Both printed."
  - "p74 TWO DIFFERENT DEFINITIONS OF BANDWIDTH on one page: side bar 'the amount of information that can be transmitted over a network in a given amount of time' vs body 'The bandwidth is the amount data that can be transferred from one point to another' — the body is printed with no word between 'amount' and 'data'. Both shown, neither merged."
  - "p31 vs p52 FTP AUTHENTICATION CONTRADICTION: p31 says FTP 'does not need authentication', p52 says FTP 'requires the user to login'. Both printed."
  - "p33 UFTP contradiction: the heading expands it as 'Unicast Fast Transfer Protocol', the body describes it as a 'multicast file transfer program'. Both printed."
  - "p36 vs p37 TABLE 14.1 IS PRINTED DIFFERENTLY ON THE TWO PAGES: p36's copy lists TTL as three values and SACK OK as 'Variable'; p37's copy differs. p36's prose also calls window size and SACK OK IP-header fields while the table groups them under TCP. Table reproduced from p37 (the fuller page); p36's variant recorded."
  - "p55 SELF-CONTRADICTION ON SAME-SOURCE TRAFFIC: the source calls same-source traffic a 'legitimate source', then two sentences later says same-source plus same TTL means 'there may be a MAC flooding attempt'. Both reproduced unreconciled."
  - "p69 CONTRADICTS ITSELF: the fake-AP-beacon section instructs the reader to use the printed filter to 'analyze client DISASSOCIATION traffic' — beacons are not disassociation. Quoted as printed, not corrected."
  - "p61 vs p63 the Interfaces count is 'the number of LOST packets' in one place and 'how many packets were NOT captured' in the other. Both quoted."
  - "p57 THE PRINTED SQL-INJECTION INDICATOR LIST HAS ITS TOKENS MISSING: 'characters specific to SQL injection such as OR, , , and z.' The characters between the commas are absent from the source. Quoted verbatim; no characters supplied."
  - "p69 THE p70 FILTER-BAR EXPRESSION WAS SEEN IN A SCREENSHOT AND DELIBERATELY NOT REPRODUCED: a compound filter combining an HTTP-request/TLS-handshake test with SSDP is legible in the p70 image. Per the screenshot non-evidence rule it is excluded from [[14-LO04j-Name-Service-Encrypted-and-Handshake-Traffic]] and recorded here so a later editor knows it was rejected, not missed."
  - "Vendor-name OCR conflicts preserved verbatim, not normalised: p101 'ClearTap' vs 'CleverTap'; p103 'Crazyegg' vs 'Crazy Egg' and 'Crea bl'/'Creabl'; p111 'ttps://www.activtrak.com' (missing h) and 'IBM Security Qradar SIEM' in the band vs 'QRadar SIEM' in the body, which is also a different product from p90's 'IBM QRadar Network Insights'; p96 Splunk source printed both 'www.splunk.com' and 'splunkbase.splunk.com'; p98 prints an unidentified 'CIS 20'."
  - "p18 prints 'SIN FIN' (not 'SYN FIN') twice, e.g. 'SIN FIN PSH RST' and 'variants of SIN FIN'. Kept as printed, not corrected."
  - "p19 the Reconnaissance definition is ungrammatical as printed: 'an unauthorized discovery of vulnerabilities, which maps of systems and services'. Quoted, not completed. p18 and p19 also print 9 and 4 bullet markers against 8 and 3 readable items; the readable items were recorded and no extra item was invented."
  - "p14 'Roving Analysis Port (RAP)-3Com' is a technical name with no expansion anywhere; reproduced verbatim and not mapped to any other name."
  - "p25 the printed command is '$ wireshark -i eth0 —k' with an EM DASH before -k. Kept as printed rather than silently normalised to '-k'."
  - "p10 vs p11 vendor URLs: the p10 figure list OCRs to 'https://www.\"npcap.org', 'https://www.sohrwinds.com', 'https://www.netresec.com'; the p11 captions print the same three hosts cleanly. Clean p11 forms used, p10 garbles recorded."
  - "p14 the figure labels 'Ingress Traffic' and 'Egress Traffic source' do not establish a replication scope in the text layer, and the callout's 'all the packets passing through the switch are replicated' is ambiguous. No scope rule asserted."
  - "Per-module exam blueprint weights are not stated in the courseware. Module 14 sits in domain 6 'Incident Detection' (10%, 10 of 100) shared with module 15 — see [[quiz.html]]. The bank uses a flat 5 items per module."
  - "SCREENSHOT NON-EVIDENCE, deliberately excluded. Wireshark GUI captures and packet dumps: pp. 26–35, 43–50, 52–60, 62–66, 68–70. Product dashboards with 'Source: https://...' captions: pp. 72, 73, 75, 76, 82–85, 87, 88, 90, 92, 93, 95–98, 101, 102, 108, 110. p26 was excluded INCLUDING the 'Wireshark 2.6.6 ... ubuntu16.04' version string, because it lives inside the image. p85, p88, p108 and p110 are whole-page figures with no usable body text; p88's OCR is console garbage ('WTC NCM rcp IOS TCPRst inva4d'). No dashboard value, panel label, confidence score or console string was transcribed from any of them."
---

[[MOC-Module-13]]

# Module 14 — Network Traffic Monitoring and Analysis

> [!abstract] Scope
> **6 LOs** · PDF pp. 4–114 (book pp. 2130–2240) · **114 pages** · 27 notes · 159 cards.
> Why you monitor → where you put the capture rig → what "normal" is → **Wireshark and 20-odd
> attack tells** → performance/bandwidth → and then the three flavours of behaviour analytics
> (network · user · user-and-entity) that close the module.
> **The shape trap:** the module teaches *two* different detection philosophies and never
> reconciles them. LO01–LO05 are **signature-based** ("match a known pattern"); LO06 is
> **behaviour/anomaly-based** ("deviate from a learned norm"). Each carries its own baseline
> vocabulary, and several exam items turn on which one is meant.

## Sections
| LO   | §    | Section                                                              | PDF pp. | Book pp.    | Notes |
| ---- | ---- | -------------------------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 14.1 | The Need for and Advantages of Network Traffic Monitoring            | 4–8     | 2130–2134   | 2 |
| LO02 | 14.2 | Setting Up the Environment for Network Monitoring                    | 9–14    | 2135–2140   | 3 |
| LO03 | 14.3 | Baseline Traffic Signatures for Normal and Suspicious Traffic        | 15–22   | 2141–2148   | 3 |
| LO04 | 14.4 | Network Monitoring and Analysis for Suspicious Traffic Using Wireshark | 23–70 | 2149–2196   | 10 |
| LO05 | 14.5 | Network Performance and Bandwidth Monitoring Concepts               | 71–77   | 2197–2203   | 2 |
| LO06 | 14.6 | Network Anomaly Detection with Behavior Analysis                     | 78–113  | 2204–2239   | 7 |

p114 is the Module Summary and is carried in `14-LO06g`. p2 is the intentionally-blank page, p1 the
module divider, p3 the objective list — whose **numbered** column prints subjects for LO#01 and
LO#02 only (`LO#03 / LO#04 / LO#05 / LO#06` appear with no text) while the **prose** list at the
foot of the same page gives all six verbatim. The prose list is authoritative; not a contradiction.

## Technical focus

- **LO01 — the case for monitoring.** Network monitoring is a **retrospective** security approach
  watching for abnormal activity, performance issues and bandwidth issues. It is defined as "the
  process of capturing network traffic and inspecting it closely to determine what is happening on
  the network", and the printed process is **sniff → capture packets → signature analysis**. Three
  reasons security tools alone are not enough: attackers bypass mechanisms, signature-based tools
  cannot track continuously changing signatures, and security tools are not designed to spot
  behavioural anomalies or activity that began *before* the attack. Four advantages: **Proactive ·
  Utilization · Optimization · Minimizing risk** (the last is the SLAs-and-compliance one).
  Operators watch four attributes: **download and upload speeds, throughput, content, and traffic
  behaviours**. → [[14-LO01a-Network-Traffic-Monitoring-and-Its-Need]]
  [[14-LO01b-Advantages-of-Network-Monitoring]]

- **LO02 — the capture environment.** A sniffer requires the **NIC in promiscuous mode** to "listen
  to all the data transmitted in the network"; copying intercepted packets to a file is **packet
  capture**. Placement: connect to "a switch in front of a firewall" so all inbound and outbound
  traffic is visible. The switch feature that replicates traffic to a monitor port is **port
  monitoring / port mirroring** — **Cisco: SPAN (Switched Port Analyzer)** · **3Com: RAP (Roving
  Analysis Port)** — selected through the **switch management interface**, which is what makes the
  switch "managed". Named sniffers: **tcpdump, WinDump, ManageEngine NetFlow Analyzer, SolarWinds
  Deep Packet Inspection and Analysis Tool, NetworkMiner**.
  → [[14-LO02a-Network-Sniffers-for-Network-Monitoring]]
  [[14-LO02b-How-Network-Sniffers-Work-and-Placement]]
  [[14-LO02c-Connecting-the-Capture-Device-to-a-Managed-Switch]]

- **LO03 — signatures and baseline.** A **signature** is "a set of traffic characteristics such as a
  source/destination IP address, ports, TCP flags, packet length, TTL, and protocols". A **network
  baseline** is the accepted behaviour for normal traffic. Normal TCP: the **ACK bit should be set
  in every packet except the initial packet, in which the SYN bit is set**; during a conversation
  packets carry only ACK by default, occasionally with PSH or URG. The **illegal-packet tests** are
  the exam gold: SYN+FIN both set, only FIN, all six flags unset, source or destination port zero,
  ACK with a zero acknowledgement number, only SYN with data present, a broadcast destination
  address, or either reserved-for-future-use bit set. Four categories of suspicious signature:
  **Informational · Reconnaissance · Unauthorized access · Denial of service**.
  Four analysis techniques: **Content-based · Context-based · Atomic · Composite** (composite = a
  series of packets over a long period; the printed example is ICMP flooding).
  → [[14-LO03a-Network-Traffic-Signatures-and-Baselining]]
  [[14-LO03b-Suspicious-Traffic-Signature-Categories]]
  [[14-LO03c-Attack-Signature-Analysis-Techniques]]

- **LO04 — Wireshark and the attack tells.** The largest section, 48 pages. Wireshark is "a widely
  used network sniffer"; the note needs the **correct network interface** to capture, and the page
  prints the command `wireshark -i eth0 -k`. Wireshark "uses the **libpcap** filter language for
  capture filters", and **Statistics → Conversations → TCP** is the printed route for viewing
  multiple TCP sessions. Then one page per attack class, each giving the mechanism and the tell:
  plaintext protocols (**FTP, TFTP, UFTP, Telnet, HTTP** — readable in the clear, hence `port`
  tagging); **OS fingerprinting** (passive = TTL, do-not-fragment, maximum segment size, window
  size, SACK OK, detected only manually because the attacker sends nothing; active = ICMP or TCP
  probes, e.g. a **FIN probe** with neither ACK nor SYN, answered with RESET by Windows, BSDI,
  Cisco, HP/UX, MVS and IRIX); **Nmap** scans (ping sweep, **ARP sweep** to see past a firewall,
  **TCP half-open/stealth**, **full connect**, **TCP null** with `tcp.flags==0x000` and no Windows
  support, `nmap-os-db` / `nmap-os-fingerprints`); **SYN/FIN DDoS** (`tcp.flags==0x003`);
  **UDP scan** (open = silence, closed = ICMP Type-3 Code-3); **password cracking** (brute force vs
  dictionary, spotted by login attempts from one IP); **MiTM sniffing**; **malformed packets** in
  the **Expert Information** panel; **ARP poisoning**; **SQL injection**; **DHCP spoofing**;
  **VLAN hopping**; **unexplained packet loss**; **NBNS** host information (port 137, `nbns`);
  **SSL/TLS**, **Kerberos** (port 88), **client deauthentication**, **fake AP beacon flood** and
  **HTTPS**. → [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]
  [[14-LO04b-Plaintext-Protocol-Traffic-FTP-TFTP-UFTP-Telnet-HTTP]]
  [[14-LO04c-OS-Fingerprinting-Passive-ICMP-and-TCP-Based]]
  [[14-LO04d-Nmap-Scan-Traffic-Ping-Sweep-ARP-Sweep-and-TCP-Scans]]
  [[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]]
  [[14-LO04f-MiTM-Sniffing-and-Malformed-Packets]]
  [[14-LO04g-ARP-Poisoning-and-SQL-Injection-Traffic]]
  [[14-LO04h-DHCP-Spoofing-and-VLAN-Hopping]]
  [[14-LO04i-Unexplained-Packet-Loss]]
  [[14-LO04j-Name-Service-Encrypted-and-Handshake-Traffic]]

- **LO05 — performance and bandwidth.** NPM "helps measure, maintain, and optimize network health";
  PRTG is the named product and "can collect data for almost anything of interest". Bandwidth is
  reported at **two levels — the interface level and the device level**. A monitoring test
  "identifies the maximum throughput of a system". **QoS is a bandwidth reservation mechanism**, and
  using the reserved bandwidth does not affect other users. → [[14-LO05a-Network-Performance-Monitoring]]
  [[14-LO05b-Bandwidth-Monitoring-and-Best-Practices]]

- **LO06 — behaviour analytics, the three flavours.** A network anomaly is "a sudden and brief
  deviation from the normal operation of a network, often caused by intruders with malicious
  intent". **NBAD** tracks five metrics to work at scale — **packets, bandwidth, bytes, traffic
  volume, protocol usage** — over three aspects (**traffic flow patterns, passive traffic analysis,
  network performance data**) using three techniques (**machine learning, statistical analysis,
  heuristics**), and consumes **NetFlow, jFlow, IPFIX, NetStream** exported by routers, switches or
  probes. The seven steps: **data collection → baseline establishment → anomaly detection → alert
  generation → alert correlation → incident investigation → response and mitigation**. Then
  **NBA** (Awake Security Platform, Cisco, ransomware, compromised devices, DDoS, NetFlow Analyzer,
  InsightIQ, NETWITNESS, McAfee NTSA, Flowmon ADS, AppNeta, Splunk), **UBA** (CleverTap, FullStory,
  Mouseflow, Userlytics) and **UEBA** (DNIF, Securonix, IBM QRadar). Table 14.2 sets UBA against
  UEBA on focus, data sources, actor coverage, network visibility and integration.
  → [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]]
  [[14-LO06b-Behaviour-Detection-Tools-Awake-Cisco-Ransomware-Compromised]]
  [[14-LO06c-DDoS-Detection-NetFlow-Analyzer-and-Additional-NBA-Tools]]
  [[14-LO06d-Network-Behaviour-Analysis-and-Its-Tools]]
  [[14-LO06e-User-Behaviour-Analytics-UBA-and-Its-Tools]]
  [[14-LO06f-User-and-Entity-Behaviour-Analytics-UEBA-and-Its-Tools]]
  [[14-LO06g-UBA-vs-UEBA-and-Module-Summary]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 14 sits in blueprint domain 6 **Incident Detection = 10%** (10 of
  100) shared with module 15 — see [[quiz.html]]. The bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield:
  - **The illegal-packet / flag tests on p18** — SYN+FIN, only FIN, NULL flags, port zero, ACK with
    a zero acknowledgement number, only SYN with data, broadcast destination, reserved bits. Eight
    discrete, checkable conditions.
  - **The four categories of suspicious signature** with their printed examples (ping sweep / port
    scan / DNS query under Reconnaissance; password cracking / sniffing / brute force under
    Unauthorized access; ping of death / SYN flood under DoS).
  - **The four advantages of monitoring** — Proactive, Utilization, Optimization, Minimizing risk —
    and which one owns SLAs and compliance.
  - **The four signature-analysis techniques**, especially Atomic vs Composite.
  - **Scan tells**: `tcp.flags==0x000` for a TCP null scan on Unix with **no Windows support**;
    `tcp.flags==0x003` for SYN/FIN DDoS; **open UDP = silence, closed UDP = ICMP Type-3 Code-3**;
    **open port = SYN+ACK, closed = RST/RST+ACK, firewalled = ICMP type-3 codes 1, 2, 3, 9, 10, 13**.
  - **Why ARP sweep beats ping sweep** — a firewall blocks ICMP, ARP reaches hidden hosts; the tell
    is an unexpected burst of broadcast ARP requests.
  - **Why passive OS fingerprinting evades firewalls** — the attacker sends nothing.
  - **The FIN probe OS list** — Windows, BSDI, Cisco, HP/UX, MVS, IRIX.
  - **LO06's five NBAD metrics, three aspects, three techniques, seven steps, four flow standards.**
  - **Table 14.2 UBA vs UEBA** — the cleanest five-row comparison in the module.
  - **Trivia-looking items that are printed and therefore fair**: SPAN vs RAP as the vendor names,
    **port 137** for NBNS, **port 88** for Kerberos, **TCP/UDP port 7** for ping sweeps, the
    `libpcap` filter language, and promiscuous mode.
- Deliberate distractors to expect:
  - **"Network monitoring is proactive"** — the page says **retrospective**; "proactive" is the name
    of one of the four *advantages*.
  - **"Passive OS fingerprinting can be blocked by a firewall"** — the module says firewalls
    **cannot** detect it and the defender must find it manually with packet sniffing tools.
  - **"A UDP scan shows an open port by a response"** — open means **no response at all**.
  - **"A TCP null scan works against Windows"** — the page says the opposite.
  - **"UEBA is a stand-alone product that cannot integrate with existing systems"** — that is
    Table 14.2's description of **UBA**, and it also contradicts p99 (see frontmatter).
  - **"The module abbreviation APT appears"** — it does not. p83 prints "advanced persistent
    threats" in full and the string `APT` occurs **zero** times in the 114 pages.
  - **Any Wireshark version number** — the only one in the PDF (`Wireshark 2.6.6 ... ubuntu16.04`)
    lives inside a screenshot on p26 and was deliberately not transcribed.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-14")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/14-network-traffic-monitoring-and-analysis-map.canvas|Network Traffic Monitoring and Analysis Map]]
- Flow to visualize: **why** (retrospective, and the three gaps security tools leave) → **where** the
  capture rig goes (promiscuous NIC, placement, **port mirroring/SPAN/RAP** on a managed switch) →
  **baseline** (what normal looks like; the flag tests; the four categories; the four analysis
  techniques) → **Wireshark** as the instrument → **the tell for each attack class** (plaintext
  protocols · OS fingerprinting · Nmap scans · SYN/FIN DDoS · UDP scan · password cracking · MiTM ·
  malformed · ARP poisoning · SQL injection · DHCP spoofing · VLAN hopping · packet loss · NBNS ·
  TLS · Kerberos · wireless deauth/beacon flood · HTTPS) → **performance & bandwidth** (NPM, the
  interface/device levels, QoS) → then **the pivot to behaviour analytics**: anomaly definition →
  **NBAD** (5 metrics / 3 aspects / 3 techniques / 7 steps / 4 flow standards) → **NBA tools** →
  **UBA** → **UEBA** → **UBA vs UEBA**.

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-15]] (Network Logs Monitoring — the other half of blueprint domain
  6) · [[MOC-Module-03]] (Technical Network Security — the protocol fundamentals every tell rests
  on) · [[MOC-Module-04]] (Network Perimeter Security — the firewall and IDS/IPS placement this
  module positions the sniffer against) · [[MOC-Module-13]] (Enterprise Wireless — this module
  analyses the wireless captures of pp. 68–69, client deauthentication and fake AP beacon flood) ·
  [[MOC-Module-01]] (Attack and Defense Strategies) · [[MOC-Module-16]] (Incident Response — where
  the "incident investigation" and "response and mitigation" steps of NBAD actually land).

## Unresolved
- **The p114 Module Summary omits LO#06 entirely** — a third of the module is missing from it (see frontmatter).
- **p113 contradicts p99 on UBA twice** — data sources and integration (see frontmatter).
- **p31 and p52 contradict each other on whether FTP needs authentication** (see frontmatter).
- **p33 contradicts itself on UFTP** — "Unicast" heading vs "multicast" body (see frontmatter).
- **Table 14.1 is printed differently on p36 and p37** (see frontmatter).
- **p55 contradicts itself** — "legitimate source" then same-source + same TTL as possible MAC flooding.
- **p69 contradicts itself** — tells you to read beacon traffic as *disassociation*.
- **p61 vs p63** disagree on what the Interfaces count means.
- **Vendor and acronym drift preserved verbatim**: `SIN FIN` (p18) · `RAP`/`Roving Analysis Port`
  with no expansion (p14) · `ClearTap`/`CleverTap` (p101) · `Crazyegg`/`Crazy Egg`, `Crea bl`/`Creabl`
  (p103) · `ttps://www.activtrak.com`, `Qradar`/`QRadar` (p111) · Splunk printed two ways (p96) ·
  an unidentified `CIS 20` (p98) · `CIS 20`-style vendor noise on p83.
- **Three items could NOT be recovered and are absent from every note**: the Wireshark version (it
  is inside a p26 screenshot), the SQL-injection indicator characters (the tokens are missing from
  p57 itself), and the p70 filter-bar expression (readable in the image, excluded by rule).
- **p73 prints the Windows Management Instrumentation abbreviation as `(WM!)`** — garbled, left as
  printed, and deliberately kept out of the flashcards.
- **Screenshot pages are non-evidence throughout**: Wireshark captures on pp. 26–35, 43–50, 52–60,
  62–66, 68–70 and product dashboards on pp. 72, 73, 75, 76, 82–85, 87, 88, 90, 92, 93, 95–98, 101,
  102, 108, 110. No dashboard value, filter-bar string, panel label or version string was read from
  any of them.

## Quick review

How many learning objectives does module 14 have, and what is LO#04's span
?
Six. LO#01 the need for and advantages of monitoring · LO#02 setting up the monitoring environment · LO#03 baseline traffic signatures · LO#04 monitoring and analysis for suspicious traffic using Wireshark (pp. 23–70, the largest) · LO#05 network performance and bandwidth monitoring · LO#06 network anomaly detection with behavior analysis

Is network monitoring proactive or retrospective, and what is the printed process
?
Retrospective. It monitors a network for abnormal activities, performance issues and bandwidth issues. The process is: sniff the traffic flowing through the network, then capture the network packets, then conduct a signature analysis to identify any malicious activity

The four advantages of network monitoring
?
Proactive · Utilization · Optimization · Minimizing risk — the last being the one tied to service-level agreements (SLAs) and compliance

What must the NIC be set to before a sniffer can listen to all network data
?
Promiscuous mode — the system's network interface card must be set to promiscuous mode to listen to all the data transmitted in the network

What does Cisco call the switch feature that replicates traffic to a monitor port, and what does 3Com call it
?
Cisco: SPAN, the Switched Port Analyzer · 3Com: RAP, the Roving Analysis Port. The generic courseware terms are port monitoring and port mirroring

Which four IP/TCP header fields does the page name as the basis for passive OS fingerprinting
?
The initial time to live (TTL), the do-not-fragment flag, the maximum segment size, the window size, and the selective ACK (SACK) OK

What does a FIN probe do, and which OSes does the page say reply with RESET
?
The attacker sends a FIN packet without an ACK or a SYN flag to an open port; many broken OS implementations reply with RESET — the page names Microsoft Windows, BSDI, Cisco, HP/UX, MVS and IRIX

In a TCP half open/stealth scan, what do open, closed and firewalled ports return
?
Open returns SYN+ACK · closed returns RST or RST+ACK · a port behind a firewall returns an ICMP type-3 packet with a code of 1, 2, 3, 9, 10 or 13

How does a UDP scan differ from a TCP scan in what an open port returns
?
An open UDP port accepts the packet and sends no response at all, while a closed one answers with an ICMP packet printed as Type-3 Code-3 — which is why UDP scanning is harder to probe, since it gathers all the ICMP errors from closed ports instead of relying on acknowledgements

Why do attackers use an ARP sweep rather than a ping sweep, and what is the tell
?
An ICMP ping sweep will not work if a firewall is in place, so an ARP sweep is used to find hosts hidden behind the firewall; the tell is an unexpected number of broadcast ARP requests

Three of the illegal-packet tests printed on the page
?
SYN and FIN both set (variants add PSH or RST to avoid detection) · only a FIN flag · all six flags unset (NULL flags). The rest: source or destination port zero · ACK set with a zero acknowledgement number · only the SYN bit with any other data present · a broadcast destination address ending in 0 or 255 · either reserved-for-future-use bit set

The four attack signature analysis techniques, and the atomic vs composite difference
?
Content-based · Context-based · Atomic · Composite. Atomic analyzes a single packet and needs no knowledge of past or future activity; composite requires a series of packets over a long period and is exceedingly difficult to detect — the printed example is ICMP flooding

The four categories of suspicious traffic signature
?
Informational · Reconnaissance · Unauthorized access · Denial of service

The five metrics NBAD tracks, and the three techniques it uses
?
Metrics: packets, bandwidth, bytes, traffic volume, protocol usage. Techniques: machine learning, statistical analysis, heuristics

The seven steps of network anomaly detection and behavior analysis
?
Data collection → baseline establishment → anomaly detection → alert generation → alert correlation → incident investigation → response and mitigation

Which flow data standards NBAD consumes, and what exports them
?
NetFlow, jFlow, IPFIX and NetStream — the statistics are exported by routers, switches or network probes

Table 14.2: how do UBA and UEBA differ
?
UBA focuses on user behavior, relies on event logs, and is a stand-alone that cannot integrate with existing security systems, with limited visibility into network activity; UEBA focuses on user and entity behavior, integrates data from multiple sources, provides more visibility into network activity and context, and integrates with existing security products and systems