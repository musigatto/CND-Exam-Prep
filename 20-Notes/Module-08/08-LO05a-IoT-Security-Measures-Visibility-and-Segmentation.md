---

type: note
module: "08"
lo: "05"
tags: [process, tool, bestpractice, mod/08, flashcard/08]
topic: "IoT Security Measures — Visibility & Segmentation (M01–M05)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Measures — Complete Visibility & Segmentation (§8.5, M01–M05)
> 27 security measures for IoT-enabled IT environments (M01–M27)

## M01 — Ensure Complete Visibility of IoT Devices
- **Asset Manager / Discovery tools** of the IoT network
  - **AssetExplorer** (ManageEngine server/desktop inventory + asset management; auto discovery)
  - **Cloud-based IoT asset mgmt** (*ServiceNow ITSM*, Azure IoT Hub, AWS IoT Device Management, iDRAC)
- Bring IoT devices under IT control; prevent shadow IoT

## M02 — Create IoT Asset Maps
- Map all assets (device → gateway → cloud apps) to understand attack surface & trust relationships
- Tools: **Oracle IoT Asset Monitoring Cloud Service**, SolarWinds, Nagios, Zabbix; asset maps fed into SIEM

## M03 — Monitor IoT Device Behavior
- Watch baseline vs anomalous behavior (traffic, commands, access)
- Tools: **Domotz Pro**, **TeamViewer IoT**, Azure IoT Hub monitoring, AWS IoT Device Management, ServiceNow, GoToAssist

## M04 — Understand Interfaces in the IoT Ecosystem
- Web interface, mobile application, cloud interface, device interface, network interface
- Risk: insecure interfaces leak data (OWASP #3 insecure ecosystem interfaces)

## M05 — Network Segmentation
- Isolate IoT devices from corporate/IT network & other device groups
- **VLANs**, firewall zones, dedicated subnets, **IDPS** between segments
- Deny by default; allow only required north-south traffic

## Cards
Security measures M01–M05?
?
Complete visibility → IoT asset maps → behavior monitoring → ecosystem-interface understanding → network segmentation.

Asset discovery tools for IoT (M01)?
?
AssetExplorer (ManageEngine), ServiceNow ITSM, Azure IoT Hub, AWS IoT Device Management.

IoT asset map tool (M02)?
?
Oracle IoT Asset Monitoring Cloud Service.

IoT behavior monitoring tools (M03)?
?
Domotz Pro, TeamViewer IoT, Azure IoT Hub, AWS IoT Device Management.

OWASP #3 — insecure ecosystem interfaces?
?
Web/mobile/cloud → weak authentication, weak encryption, missing filtering.
