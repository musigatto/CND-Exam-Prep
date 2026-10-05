---
type: note
module: "14"
lo: "04"
tags: [threat, command, protocol, mod/14]
topic: "Scan traffic: ping sweep, ARP sweep, TCP half open/stealth, full connect, null"
exam_weight: unknown
status: done
unresolved:
  - "pp43–48 the prose never names Nmap; it attributes the sweeps and scans only to 'attackers'. The filename follows MANIFEST-14.md. Nmap is named in this module only at pp40–41 (OS fingerprinting). Not added here."
  - "p43 the ICMP ping sweep filter is printed as 'icmp.type==8 or icmp.type==O' — the OCR renders the second zero as the letter O. Reproduced verbatim, not corrected. p50 prints the same zero as a clean '0' in icmp.type==3."
  - "p48 the OCR renders certain digits as the letter O: the null-scan filter is printed as 'tcp.flags==OxOOO' and the packet 'sequence number of O'. Reproduced verbatim in the filter and read as 0 in the prose; not corrected."
  - "p48 the callout filter is garbled — 'Use the following filter to view the packets moving without a flag set: TCP.' — and is not reconstructed."
  - "p43 the callout prints 'Use the filter tap. to detect a TCP ping sweep attempt'; the body text on the same page gives tcp.dstport==7. Both reproduced as printed."
  - "p45 the callout says a 'stealth scan or TCP full connect scan attempt is recognized if there are a large amount of RST or ICMP type 3 packets', while the p46 body describes a full connect scan as a complete three-way handshake that legitimately completes. Contradiction is the source's; not resolved here."
  - "p45 prints the open-port reply as 'SYN+ACK' and the closed-port reply as 'RST or RST+ACK'; p46 prints the closed-port reply as 'RST/ACK' and the open-port reply as 'SYN/ACK'. Each is quoted from its own page."
  - "pp43, 44, 45, 46, 48 carry Wireshark GUI captures (ICMP Echo reply lines, ARP Who-has/Tell lines, the SYN/SYN+ACK/RST+ACK diagrams, the 512 null-scan packets). Not treated as evidence here."
---

[[MOC-Module-14]]

# Scan Traffic: Ping Sweep, ARP Sweep and the TCP Scans (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp43–48.

## Master table — one row per scan technique _(Mod 14 pp43–48)_

| Technique | What the attacker does | What the traffic shows | Detection the page names |
|---|---|---|---|
| **ICMP ping sweep** | Sends an **ICMP type-8 echo request** followed by an **ICMP type-0 request**, then analyses the echo reply | A **series of echo requests to every IP in a specified range**; live hosts answer | Find the **ICMP type-8 and ICMP type-0** echo requests in the traffic. Filter `icmp.type==8 or icmp.type==O` |
| **TCP/UDP ping sweep** | Sends an **echo request packet to TCP/UDP port 7** | Echo requests to **port 7**; replies only where the port supports an echo reply | Detect TCP echo requests to port 7 and UDP echo requests to port 7. Filters `tcp.dstport==7`, `udp.dstport==7` |
| **ARP sweep / ARP scan** | **Broadcasts ARP packets to all hosts in the selected subnet** and waits for a response | "An **unexpected number of broadcast ARP requests** indicates an ARP sweep attempt"; an **ARP response** means the host is live | Filter `arp` |
| **TCP half open / stealth scan** | Sends a **SYN** packet, exactly like normal TCP communication, and waits | **SYN+ACK** → port **open** · **RST or RST+ACK** → port **closed** · **ICMP type-3 with code 1, 2, 3, 9, 10 or 13** → target behind a firewall | "**Excessive RST packets or ICMP type-3 response packets**"; "a **large amount of RST or ICMP type 3** packets". Statistics → Conversations → TCP tab. **Communication of less than 4 packets is a sign of a TCP port scan** |
| **TCP full connect scan** | **Complete three-way handshake** — SYN probe, SYN/ACK received, then an **ACK flag** to complete; session terminated with an **RST flag** | Successful three-way handshake ⇒ port open · **RST/ACK** ⇒ port closed · **ICMP type-3, code 1, 2, 3, 9, 10 or 13** ⇒ firewalled | "the **same methods as those used to detect a stealth scan**": check for **SYN+ACK, RST, and RST+ACK** packets or **ICMP type 3** packets |
| **TCP null scan** | Sends a TCP packet with a **sequence number of 0 and no set flag**; **all TCP headers (ACK, FIN, RST, SYN, URG, PSH) set to NULL** | **RST** returned → port **closed** · **no response** → port **open** (or **open or filtered**, per the callout) | Filter `tcp.flags==OxOOO` — stated to work **on Unix servers**; "**TCP null scans do not support Windows**" |

## Ping sweep _(Mod 14 p43)_

- Purpose: "determine the **live hosts within a specified IP range**". "It is accomplished using **ICMP, TCP, or UDP**" — "a series of ICMP, TCP, or UDP **echo requests** to the specified IP range".
- "A ping sweep scan helps attackers **discover active systems** in a network. It involves sending multiple ICMP, TCP, or UDP echo requests to target ports and then analyzing the **echo reply** obtained from the port."
- **ICMP variant:** the network defender "must find the **ICMP type-8 and ICMP type-0 echo requests** in the network traffic. The use of a filter is recommended."
- **TCP/UDP variant:** echo request to **port 7**; both the TCP and UDP echo request packets to port 7 must be found in the traffic.
- **Limitation printed:** "If the target port does not support an echo reply, then **this technique will not work**."

## ARP sweep / ARP scan _(Mod 14 p44)_

- "**An ICMP ping sweep will not work if a firewall is implemented in the network.** Thus, attackers attempt to execute an ARP sweep technique to **scan hidden hosts behind the network firewall**."
- "In an ARP sweep, an attacker **broadcasts ARP packets to all the hosts in the selected subnet** and waits for a response. **If an ARP response is received from a specific host, then the host is live.**"
- "**ARP communications cannot be disabled** to restrict an ARP sweep attempt on the network as **all TCP/IP communication is based on it**."
- "An **unexpected number of broadcast ARP requests** indicates an ARP sweep attempt on the network." The ARP sweep is a common substitute for ping sweep wherever a firewall blocks ICMP.

## TCP half open / stealth scan _(Mod 14 p45)_

- "This scan involves sending a **SYN packet to the target port exactly like normal TCP communication** and waiting for a response."

| Target state | Response the page prints |
|---|---|
| Port **open** | **SYN+ACK** |
| Port **closed** | **RST** or **RST+ACK** |
| Port **behind a firewall** | **ICMP type-3** packet with a **code 1, 2, 3, 9, 10, or 13** |

- "The **TCP half connection can act as an open gate for attackers to enter the network**."
- "**Excessive RST packets or ICMP type-3 response packets** in Wireshark indicate a TCP half open/stealth scan attempt on the network."
- Manual view the page names: **Statistics → Conversations → TCP tab**, to view and analyze multiple TCP sessions. "**If the communication is of less than 4 packets, then it is a sign of a TCP port scan** on the network."

## TCP full connect scan _(Mod 14 pp46–47)_

- "A TCP full connect scan or a TCP connect scan is the **default scan** that establishes a **complete three-way handshake** connection. **A successful three-way handshake implies that the port is open.**"
- Sequence printed: the attacker sends a **SYN probe packet** → if the port is open, receives a **SYN/ACK** → "completes the communication by **sending an ACK flag and receiving an RST flag to terminate the session**".
- **If the port is closed**, the attacker receives **RST/ACK** as the response. **If the target port is behind a firewall**, they receive an **ICMP type-3 packet with a code 1, 2, 3, 9, 10, or 13**.
- Detection: recognised "using the **same methods** as those used to detect a stealth scan" — **SYN+ACK, RST, and RST+ACK** packets, or **ICMP type 3** packets.

## TCP null scan _(Mod 14 p48)_

- "A TCP null scan helps attackers **identify listening ports** in the network."
- "A TCP null scan is a series of TCP scan packets containing a **sequence number of 0 and no set flag**." It "sets **all the TCP headers (ACK, FIN, RST, SYN, URG, and PSH) to NULL**."
- Evasion: "Since the null scan does not contain any set flags, it can **penetrate a router and a firewall that filter incoming packets with particular flags set**."
- Result: closed port → **RST flag**; open port → **no response**, "because the packet lacks a flag". Callout phrasing: "**If there is no response, then the port is open or filtered**".
- "network defenders can detect a TCP null scan **on Unix servers** by applying the filter `tcp.flags==OxOOO` in Wireshark. **TCP null scans do not support Windows.**"

## Related

- Nmap's OS-fingerprinting probes, same tool family: [[14-LO04c-OS-Fingerprinting-Passive-ICMP-and-TCP-Based]]
- Further attack traffic: [[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]]
- Filters and menu items used above: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]







