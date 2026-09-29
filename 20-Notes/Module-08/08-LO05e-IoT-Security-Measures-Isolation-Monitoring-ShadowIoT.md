---

type: note
module: "08"
lo: "05"
tags: [process, tool, bestpractice, mod/08, flashcard/08]
topic: "IoT Security Measures — Isolation, Monitoring, Shadow IoT (M20–M27)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Measures — Isolation, Monitoring, Shadow IoT (§8.5, M20–M27)

## M20 — Isolate Wi-Fi Traffic from IoT Devices
- Guest Wi-Fi / dedicated SSID on router; **client isolation** per VLAN
- Example: pcWRT guest network — isolate IoT traffic from main LAN

## M21 — Isolate Ethernet Traffic from IoT Devices
- VLAN ports on switches (X1 = trunk/gateway, X2 = main LAN, X3 = IoT subnet)
- Separate IoT ethernet segments; firewall between

## M22 — Control Internet Access for IoT Devices
- Allow only required destinations (whitelist domains/IPs); block everything else
- DNS filtering + egress firewall on the IoT subnet

## M23 — Monitor Network Activity for IoT Devices
- Watch abnormal traffic volume/patterns (pcWRT network activity view)
- Detect data exfiltration / botnet C2 beaconing

## M24 — Monitor Bandwidth Usage
- Identify bandwidth hogs (firmware updates, streaming, crypto-chaining)
- Tools: **SolarWinds NetFlow Traffic Analyzer / Network Performance Monitor**, **Paessler PRTG**

## M25 — Centralize IoT Access Logs
- Aggregate logs from gateways, devices, cloud into **Cloud IoT Core + Stackdriver Logging** (GCP)
- Also: SIEM, log analytics for audit + anomaly detection

## M26 — Ensure IoT Security on Public Wi-Fi
- VPN requirement, certificate pinning, no cleartext protocols; treat public Wi-Fi as hostile

## M27 — Manage Shadow IoT Devices
- Internet-connected devices not under IT control
- Discover via **Shodan** / network scanning; bring under M01 visibility; segment/disable or secure

## Cards
Security measures M20–M27?
?
Wi-Fi isolation → Ethernet isolation → internet-access control → network monitoring → bandwidth monitoring → log centralization → public Wi-Fi security → shadow IoT management.

VLAN port mapping example (M21)?
?
X1 = trunk/gateway, X2 = main LAN, X3 = IoT subnet.

Guest-network client isolation tool?
?
pcWRT guest network (isolate IoT traffic from LAN).

Bandwidth monitoring tools (M24)?
?
SolarWinds (NPM / NetFlow Traffic Analyzer), Paessler PRTG.

Logarithm centralization (M25)?
?
Cloud IoT Core + Stackdriver Logging (GCP); SIEM.

Shadow IoT discovery tool (M27)?
?
Shodan — Internet-facing IoT devices outside IT control.
