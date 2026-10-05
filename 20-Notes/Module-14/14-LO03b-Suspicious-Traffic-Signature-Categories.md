---
type: note
module: "14"
lo: "03"
tags: [concept, threat, protocol, mod/14]
topic: "Suspicious traffic signature categories"
exam_weight: unknown
status: done
unresolved:
  - "p18 the SYN FIN variant list prints 'SIN FIN PSH RST' and 'variants of SIN FIN' - SIN for SYN is left exactly as printed, not corrected."
  - "p18 the suspicious-characteristics list prints 9 bullet markers ('o o o o O o o o o') against 8 readable characteristics. The reading of the 9th bullet is not stated in the source; not invented."
  - "p19 the Reconnaissance body prints 'an unauthorized discovery of vulnerabilities, which maps of systems and services' - the sentence is ungrammatical in the source. Quoted as printed, not completed."
  - "p19 the reconnaissance example list prints 4 bullet markers against 3 readable examples."
  - "p19 the DoS category is printed 'Denial of service (DOS)' in the body and 'Denial of Service' in the p19 figure. Both forms kept."
---

[[MOC-Module-14]]

# Suspicious Traffic Signature Categories (§14.03)

> **LO#03: Determine baseline traffic signatures for normal and suspicious network traffic** _(Mod 14 LO#03)_
> Covers pp18–20.

## Normal TCP flag usage _(Mod 14 p18)_

Continuation of the normal-TCP-signature callout in
[[14-LO03a-Network-Traffic-Signatures-and-Baselining]].

| Flag combination | Printed meaning |
|------------------|-----------------|
| **FIN ACK and ACK** | used in **terminating a connection** |
| **PSH FIN and ACK** | **may also be used initially** in the same process |
| **RST and RST ACK** | used to **quickly end an on-going connection** |
| During a conversation — after a handshake, before termination | packets contain **only an ACK bit by default** |
| Occasionally | they may also have a **PSH or URG** bit set |

## A suspicious TCP packet _(Mod 14 p18)_

*"A suspicious TCP packet has one or more of the following characteristics:"*

| # | Characteristic | Note as printed |
|---|----------------|-----------------|
| 1 | **SYN + FIN both set** → the TCP packet is **illegal** | **"SYN FIN PSH, SYN FIN RST, and SIN FIN PSH RST are all variants of SIN FIN."** — *"An attacker sets these additional bits to avoid detection."* |
| 2 | **Only a FIN flag** → illegal | FIN can be used in **network mapping, port scanning, and other stealth activities** |
| 3 | **All six flags unset** → illegal | *"these are known as **NULL flags**"* |
| 4 | **Source or destination port is zero** | |
| 5 | **ACK flag set** → *"then the **acknowledgement number should not be zero**"* | |
| 6 | **Only the SYN bit** set, *"and any other data are present"* → illegal | SYN is *"set at the beginning to establish a connection"* |
| 7 | **Destination address is a broadcast address** — **ending with 0 or 255** → illegal | |
| 8 | **Two bits reserved for future use** set — either or both → illegal | *"Every TCP packet has two bits reserved for future use."* |

## The four suspicious traffic signature categories _(Mod 14 pp19–20)_

*"Network traffic deviating from normal behavior is categorized as a suspicious traffic signature. It is
classified into four categories as follows."* Figure text and body text are kept side by side — the
figure is much terser than the body.

### Informational

- Figure: **"Traffic containing certain signatures that may appear suspicious but might not be
  malicious."**
- Body: *"The informational traffic signature **detects normal network activity**. Although it may not
  appear suspicious, **the data gathered through the informational signature can be used for
  suspicious activities**."*
- Examples: **ICMP echo requests** · **TCP connection requests** · **UDP connections** _(Mod 14 p19)_

### Reconnaissance

- Figure: **"Traffic containing certain signatures that indicate an attempt to gain information."**
- Body: *"Reconnaissance traffic consists of signatures that indicate an attempt to **scan the
  network for possible weaknesses**. Reconnaissance is an unauthorized discovery of vulnerabilities,
  which maps of systems and services. Reconnaissance is also known as **information gathering**, and
  it **precedes a network attack in most cases**."*
- Examples: **ping sweep attempts** · **port scan attempts** · **DNS query attempts** _(Mod 14 p19)_

### Unauthorized access

- Figure: **"Traffic containing certain signatures that indicate an attempt to gain unauthorized
  access."**
- Body: *"Traffic may contain signs of someone attempting to gain **unauthorized access, unauthorized
  data retrieval, system access or privilege escalation**, etc. An attacker who does not have
  privileges to access an organization's network usually generates this type of traffic **with the
  intention of capturing sensitive data**."* _(Mod 14 pp19–20)_
- Examples: **password cracking attempts** · **sniffing attempts** · **brute-force attempts** _(Mod 14 p20)_

### Denial of service (DOS)

- Figure: **"Traffic containing certain signatures that indicate a DoS attempt that floods a server
  with a large number of requests."**
- Body: *"This type of traffic may contain **a large number of requests from a single source or
  multiple sources**, which are sent as an attempt to perform a DoS attack. This type of attack is
  performed to **disrupt the service of the target organization**."* _(Mod 14 p20)_
- Examples: **ping of death attempts** · **SYN flood attempts** _(Mod 14 p20)_

→ Traffic corresponding to these signatures in the captures: `[[14-LO04d-Nmap-Scan-Traffic-Ping-Sweep-ARP-Sweep-and-TCP-Scans]]`
· `[[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]]` · `[[14-LO04f-MiTM-Sniffing-and-Malformed-Packets]]`








![IMG-NEEDED: assets/14-illegal-packet-flags.png — illegal TCP flag combinations, Wireshark-style capture]

