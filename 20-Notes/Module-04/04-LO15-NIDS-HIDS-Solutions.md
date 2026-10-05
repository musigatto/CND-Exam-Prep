---

type: note
module: "04"
lo: "15"
tags: [tool, concept, mod/04]
topic: "NIDS & HIDS Solutions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# NIDS and HIDS Solutions (§4.15)

## NIDS: Snort
- Open-source NIDS for Linux + Windows; detects emerging threats
- Capabilities: real-time traffic analysis + packet logging on IP networks, protocol analysis, content matching
- Rule-based language combining **signature, protocol, anomaly** inspection methods
- Detects: DoS attacks, OS fingerprinting attempts, buffer overflows, semantic URL attacks, stealth port scans, SMB probes, CGI attacks
- Example rule: `alert tcp $EXTERNAL_NET any -> $HOME_NET 1433` — flags TCP scan attempt (MSSQL port), alert on detection

## NIDS: Zeek (formerly Bro)
- **Behavioral-based** IDS + network analysis framework; detects network anomalies; targets **high-performance networks**, used operationally at large sites
- Features:
  - Comprehensively logs what it sees; high-level archive of network activity
  - Protocol analyzers → high-level **semantic (application-layer) analysis**
  - Keeps extensive **application-layer state**
  - Domain-specific scripting language → site-specific monitoring policies
- Zeek logs integrate with **SIEM**: ELK stack (Kibana) to analyze/visualize; notification framework limited in scope — use tools like **X-Pack, Logz.io** for alerting

## NIDS/IPS: Suricata
- Open-source-based IDS/IPS engine: real-time intrusion detection, **inline intrusion prevention**, network security monitoring (NSM), offline pcap processing
- Features:
  - Single instance inspects **multi-gigabit** traffic
  - Auto-detects protocols (e.g., HTTP on any port), applies proper parser
  - **Lua scripting** for advanced analysis beyond ruleset syntax
  - Industry-standard logging output **"Eve" (JSON)** → easy integration with Logstash etc.
  - Supports **YAML + JSON** I/O → SIEM integration (Splunk, Logstash/Elasticsearch, Kibana)

## HIDS: OSSEC
- **OSSEC (Open Source HIDS SECurity)** — HIDS: log analysis, integrity checking, Windows registry monitoring, rootkit detection, time-based alerting, active response
- Extensive configuration: custom alert rules, scripts for alert actions; detects e.g. login-failure patterns (FTP brute force via ET rules)
- Features: log-based intrusion detection (LIDs), rootkit/malware detection, active response via firewall policies + 3rd-party (CDNs, support portals) + self-healing, file integrity monitoring (FIM)
- Logs monitored via Suricata, AlienVault USM, etc.

## HIDS: Wazuh
- **Fork of OSSEC HIDS**; performs log analysis, integrity checking, Windows registry monitoring, rootkit detection, time-based alerting, active response
- Agent runs at host level, combining **anomaly + signature-based** technologies
- Also monitors user activities, assesses system configuration, detects vulnerabilities






