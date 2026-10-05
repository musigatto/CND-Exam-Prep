---
type: note
module: "15"
lo: "05"
tags: [concept, process, bestpractice, port, mod/15]
topic: "firewall logging and the firewall log analysis procedure"
exam_weight: unknown
status: done
unresolved:
  - "p60 prints the logging range as 'level O to level 7' with a capital letter O; rendered here as 0."
  - "p60 gives the level names only as an ordered list ('They are arranged in the following order: emergency, alert, critical, error, warning, notification, informational, and debugging') and prints no number beside any name. The 0-7 mapping below is the page's own stated order, not a printed table; it is NOT repeated from any syslog standard."
  - "p62 carries a lone bullet 'Tear down in connection' that pp59–62 never define, expand or place in the 5-step list. Quoted as printed; no meaning inferred."
  - "p60 Figure 15.18 legend labels are OCR-damaged beyond legibility ('Seage prwate Area', 'Firewall Log pub\"c', 'Spec&d tramc Owed', 'Resmc&d unknown tramc'). The figure legend was NOT transcribed and no label was guessed."
---

[[MOC-Module-15]]

# Firewall Logging and Analysis Steps (§15.LO#05a)

> **LO#05: Discuss log monitoring and analysis in firewalls** _(Mod 15 p59)_
> Covers pp59–62.

## What LO#05 covers _(Mod 15 p59)_

> "The objective of this section is to explain monitoring and analysis of firewall logs. It describes **Windows, Linux, MAC, Cisco ASA, Check Point Firewall logs** and demonstrates how to monitor and analyze them."

⇒ per-platform notes: [[15-LO05b-Windows-Defender-Firewall-Logs]] · [[15-LO05c-Mac-OS-X-Firewall-Logs]] · [[15-LO05d-Linux-iptables-Logs]] · [[15-LO05e-Cisco-ASA-Firewall-Logs]] · [[15-LO05f-Check-Point-Firewall-Logs]] · the devices themselves → [[MOC-Module-04]]

## Firewall logging — what it is and why it is on _(Mod 15 p60)_

> "**The capability of a firewall to log users' activities in a network** is known as firewall logging." _(p60)_

| Point | As printed |
|---|---|
| Purpose | Logging **"allow" events** → "useful for **capturing potential security threats** to the network" |
| Why enable it | "**the most important source for determining post attack scenarios**" |
| Storage | "Some firewall logs are stored in **proprietary formats**, and others are **polled through SNMP**" |
| Content | "**source and destination IP addresses, port numbers, and protocols**" |
| Attack angle | "**Attackers ... leave their footprints**; these should be investigated to get basic information about the attack" |
| Rule validation | Logging "**helps confirm whether firewall rules are working as expected**"; if not, "they need to be **debugged** to determine the causes" |
| Granularity | "supports **multiple levels of logging to handle the most critical events first**" |

## Logging levels — level 0 to level 7 _(Mod 15 p60)_

> "The levels of logging are labeled from **level 0 to level 7**. The events at **level 0 are of the greatest importance** and those at **level 7 are of least importance**. They are arranged in the following order: **emergency, alert, critical, error, warning, notification, informational, and debugging**."

| Level | Event type (order as printed on p60) |
|---|---|
| 0 | emergency |
| 1 | alert |
| 2 | critical |
| 3 | error |
| 4 | warning |
| 5 | notification |
| 6 | informational |
| 7 | debugging |

Firewall-levelled logging → same idea as OS syslog severity → [[15-LO03b-Linux-Log-Format-and-Severity-Levels]]

## Monitoring and analysis of firewall logs _(Mod 15 p61)_

> "By monitoring and analyzing these logs, the **source IP addresses that accessed the network, bandwidth used, events occurred**, etc. can be known. **Unauthorized connection attempts, port scan attempts, actions from compromised systems**, etc. can also be **detected and documented**."

### Normalization — the first thing the page insists on

> "However, the firewall logs need to be **converted into a standard format (normalization), which simplifies the reviewing and analysis**." _(p61)_

### Order of work _(Mod 15 p61)_

1. "**Set the proper logging levels** and apply a **log maintenance policy**."
2. "**Determine the items needed to detect abnormal or malicious activities**."

⇒ "**IP addresses and port numbers play an important role in establishing a connection through the firewall.** The IP addresses determine the various systems involved during transmission, and **port numbers specify the types of applications or services** that are being used." By monitoring the logged port numbers and their corresponding services, suspicious activities can be identified.

### The 7 common items to look for in a firewall's log _(Mod 15 p61)_

- **IP addresses that are rejected and dropped**
- **Unsuccessful logins** to the firewall and other critical servers
- **Suspicious outbound activities from internal servers**
- **Source-routed packets**
- **Ports on which no application is running**
- **Stop/start/restart of firewall**
- **Change in firewall configuration**

## Firewall Log Analysis — the 5 printed steps _(Mod 15 pp61–62)_

Figure "Steps of Firewall Log Analysis" on p61 and the body list "The following steps are used to analyze firewall logs" on p62 print the same five:

1. "**Find the location of the log file in the local computer/server.**"
2. "**Identify and analyze the fields in the firewall logs to collect evidence.**"
3. "**Interpret the firewall log for incoming and outgoing connections from different sources.**"
4. "**Find out the source IP address, destination IP address, and the action performed by the firewall** to the incoming connection."
5. "**Identify the location of the source IP address using IP address tracking tools.**"

> **Note _(p61):** "Firewall logs are recorded only when firewall logging is enabled."







