---
type: note
module: "14"
lo: "04"
tags: [protocol, port, threat, command, mod/14]
topic: "Name service, encrypted and handshake traffic"
exam_weight: unknown
status: done
unresolved:
  - "p68 the deauthentication filter is printed two ways: body 'wlan.fc.type_subtype 12\\'' and objective 'wlan.fc.type_subtype == 12'. Both forms quoted; no corrected syntax asserted."
  - "p69 the fake-AP-beacon section tells the reader to 'use the filter wlan.fc.type_subtype 8 to analyze client Disassociation traffic' while the section is about beacon frames — the page contradicts itself; both quoted as printed."
  - "p70 the Wireshark filter-bar expression visible in the Figure 14.24 screenshot ('(http.request or tls.handshake.type eq 1) and (ssdp)') is screenshot content and is deliberately NOT reproduced as courseware."
  - "p64/p65 NBNS hex/name bytes and p66 TLS hex bytes are not transcribed; the prose never walks through them."
  - "p65 the NBNS host names and p69 the SSID strings visible in the packet lists are screenshot-only values and are not read out."
---

[[MOC-Module-14]]

# Name Service, Encrypted and Handshake Traffic (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp64–70.

Tooling: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]. The wireless attacks analysed on pp68–69 belong to [[MOC-Module-13]]. Cleartext counterpart of HTTPS: [[14-LO04b-Plaintext-Protocol-Traffic-FTP-TFTP-UFTP-Telnet-HTTP]].

## Master table

| Protocol | Default port (as printed) | Filter printed in source | What the page says it reveals / enables |
|---|---|---|---|
| **NBNS** | **UDP/TCP 137** _(pp64–65)_ | `nbns` _(pp64–65)_ | host names, **IP and MAC addresses**, and the **services provided** by these entities |
| **SSL/TLS** | **TCP 443** _(p66)_ | `tls` — "a complete list of TLS display filter fields" _(p66)_ | encrypted traffic; content **not** readable; SSL now insecure |
| **Kerberos** | **88** _(p67)_ | `kerberos.CNameString` _(p67)_ | a **Windows/Linux user account and hostname** |
| **802.11 client deauthentication** | — | `wlan.fc.type_subtype == 12` _(p68)_ | forged deauth frames; attacker/victim **MAC addresses** + **reason code** |
| **Fake AP beacon flood** | — | `wlan.fc.type_subtype 8` _(p69)_ | beacon frames overrunning the real ones |
| **HTTPS** | **443** _(p70)_ | `https` _(p70)_ | metadata only: src/dst IP, ports, packet sizes, timing |

_(Mod 14 pp64–70)_

## NBNS — host information from NetBIOS Name Service (pp64–65)

- "NBNS (NetBIOS Name Service) is a protocol utilized for **NetBIOS name resolution**, which reveals significant information about network devices and hosts."
- Discloses: **host names**, **IP and MAC addresses**, and **the services provided by these entities**.
- Described as a **legacy protocol**; "NBNS traffic, operating on **UDP/TCP port 137**, is a vital component of network communication."
- Why monitor: **host discovery**, **detecting rogue devices**, **identifying misconfigurations in network infrastructure**; administrators "enhance their ability to **maintain network integrity** and swiftly **identify issues**."
- "In Wireshark, use the filter **`NBNS`** to examine host information from NETBIOS." _(Mod 14 pp64–65)_

## SSL/TLS (p66)

- "Transport layer security (**TLS**) secures internet traffic by **encrypting data** transmitted over the internet, making it **challenging for attackers to intercept and read**."
- "**Secure Sockets Layer (SSL), its predecessor, is now considered insecure.**"
- "To find a **complete list of TLS display filter fields**, use the `tls` filter in Wireshark."
- ⚠ Capture-time caveat: "Remember, **you cannot filter TLS protocols directly while capturing**; instead, **filter on the default TCP port 443**." _(Mod 14 p66)_

## Kerberos (p67)

- "Kerberos is designed to provide **secure authentication by encrypting authentication messages between clients and servers using shared secret keys**."
- "It facilitates **mutual authentication between users and services** in a network."
- "**The default port for Kerberos is 88.**"
- "In Wireshark, use the filter `kerberos.CNameString` to **obtain a Windows/Linux user account and hostname**." _(Mod 14 p67)_

## Client deauthentication (p68) — wireless

- "A **client deauthentication attack is a wireless attack** used to **disconnect clients from a network by sending forged deauthentication frames**."
- Impact: "can **force clients to reconnect**, potentially **exposing sensitive authentication information like passwords**"; can **disrupt a wireless network**, cause **denial of service (DoS) for legitimate users**, or enable other attacks such as **man-in-the-middle**.
- "Wireshark captures and analyzes the **802.11 management frames** sent during a deauthentication attack, revealing the **source and destination MAC addresses of the attacker and victim devices**, as well as the **reason code** for the deauthentication."
- Filter — the page prints two forms: `wlan.fc.type_subtype 12'` (body) and `wlan.fc.type_subtype == 12` (objective, "to analyze client deauthentication traffic"). See `unresolved:`. _(Mod 14 p68)_

## Fake AP beacon flood (p69) — wireless

- "The fake AP beacon flood is an attack where an attacker **transmits a large number of false beacon frames within the wireless range of a targeted Wi-Fi network**."
- "These frames, **normally used by Wi-Fi devices to find and connect to networks**, can be **overrun** by the attacker's false frames."
- Consequence: "**confusion among devices and potentially disables wireless connectivity**"; the attack "floods the area with fake access point beacons, causing **connectivity issues (jamming)** or even **crashing some clients' networks (DOS)**, ultimately leading to a **network crash**."
- Filter: "use the filter `wlan.fc.type_subtype 8` to analyze client Disassociation traffic, which is instrumental in identifying such attacks." _(contradicts itself — see `unresolved:`)_
- Defensive value: helps **identify vulnerabilities**, **recognize weak security setups**, **understand attack patterns**, and **implement additional security measures**. _(Mod 14 p69)_

## HTTPS (p70)

- "Hypertext Transfer Protocol Secure (**HTTPS**) secures the communication between a user's website and web browser within a network." "HTTPS traffic **typically operates on port 443**."
- Visibility limit: "it is **impossible to directly analyze the content** of encrypted HTTPS communications" — but you "can still monitor **metadata** like **source/destination IP addresses, ports, packet sizes, and timing details**".
- Decryption: "**If you are using a proxy server, decrypting the traffic with the proxy's SSL/TLS keys is possible.**"
- Risk: "**Poorly encrypted** HTTPS traffic is vulnerable to attacks, potentially allowing attackers to perform **man-in-the-middle attacks** and intercept network traffic."
- Reasons to monitor: **ensure sensitive information is not sent over HTTP**, **detect malicious traffic** (e.g. data exfiltration, malware infections, command and control), **check compliance with policy violations**, **identify applications using unnecessary or restricted services**.
- "In Wireshark, use the filter **`https`** to examine specific HTTPS traffic." _(Mod 14 p70)_






