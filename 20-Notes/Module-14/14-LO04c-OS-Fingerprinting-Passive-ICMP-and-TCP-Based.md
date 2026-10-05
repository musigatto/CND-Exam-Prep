---
type: note
module: "14"
lo: "04"
tags: [threat, protocol, tool, mod/14]
topic: "OS fingerprinting: passive IP-header analysis, active ICMP/TCP probes, Nmap indicators"
exam_weight: unknown
status: done
unresolved:
  - "p39 the callout prints 'ICMP address mask requests (917)' while the body text on the same page prints 'ICMP address mask requests (17)'. Both reproduced as printed; not reconciled."
  - "p39 the callout filter is garbled: 'Use the following filter to locate unusual ICMP requests: (icmp. ( ! e (icmp. I I . 1 .' — reproduced verbatim, not reconstructed."
  - "p40 the callout filter list is garbled: '(tcp. (tcp. window size <1025) tcp. tcp. O tcp. options .wscale tcp. options . ms' — reproduced verbatim, not reconstructed."
  - "p37 Table 14.1 is recovered from a scrambled OCR grid; the Default Value and Operating System cells are listed in printed order and are not claimed to pair 1:1. p36 prints a second copy of the same table in which Initial Time to Live appears as the three separate values 64 / 128 / 255 and SACK OK appears as 'Variable' / 'Not set'."
  - "p36 the prose lists 'window size, and selective ACK (SACK) OK' among the fields of 'the IP header', while Table 14.1 groups those two under TCP. Reproduced as printed."
  - "p41 the indicator '120- or 150-byte payload of OxOOs' and 'timestamp value set to OxFFFFFFFF' are printed with the letter O for the leading hex zero; not corrected."
  - "p41–42 the page states Nmap 'sends eight different packets' and then lists nine test names (Tseq, T1–T7, PU). Both reproduced as printed."
---

[[MOC-Module-14]]

# OS Fingerprinting: Passive, ICMP-Based and TCP-Based (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp36–42.

Goal: **detect the OS type and version running on the target system** from traffic alone. Three forms — passive, active ICMP-based, active TCP-based (the last almost always via **Nmap**).

## Passive vs active at a glance _(Mod 14 pp36, 38)_

| | Passive OS fingerprinting | Active OS fingerprinting |
|---|---|---|
| Attacker behaviour | "the attacker **does not send any packets** in the traffic; rather, they **sniff TCP/IP ports**" | "the attacker **sends packets to the target and waits for a reply**" |
| Basis | Verification of various **IP header fields** | Analysis of the **reply** → "an educated guess to determine the OS" |
| Probes | none | **ICMP probes** or **TCP probes** |
| Detectability | "**very difficult to detect** a passive fingerprinting attempt. **Firewalls or other security devices cannot detect passive OS fingerprinting either**" | "**much easier to detect** than passive OS fingerprinting attempts" |
| Defender action | "essential to detect these attempts **manually with the help of packet sniffing tools**" | "**Specific Wireshark filters can be used to filter out OS fingerprinting traffic**" |

Caveat the page prints on the passive method: "the default values for these fields **may vary when the packet traverses two routers**." _(Mod 14 p36)_

## Fields inspected for passive fingerprinting _(Mod 14 p36)_

"The IP header consists of fields such as the **initial time to live (TTL)**, **do-not-fragment flag**, **maximum segment size**, **window size**, and **selective ACK (SACK) OK**." Their default values help defenders detect fingerprinting attempts. Callout: "Monitor and analyze packet fields such as **TTL and window size**". _(Mod 14 p36)_

### Table 14.1 — Default Values of IP Header for Different OSes _(Mod 14 p37)_

Printed column headers: **Protocol · Field · Default Value · Operating System**. Values and OS lists in printed order:

| Field | Default value(s) as printed | Operating System(s) as printed |
|---|---|---|
| **Initial Time to Live** | 64 to 128–255 | Nmap · BSD · macOS 10 · Linux · Novell, Windows · Cisco IOS · Palm OS, Solaris |
| **Do-not-fragment Flag** | Set · Not set | BSD, macOS 10, Linux, Novell, Windows, Palm OS, Solaris |
| **Maximum Segment Size** | 1460 | Nmap, Cisco IOS |
| **Window Size** | 1024-4096 · 65535 · 2920-5840 · 16384 · 4128 · 24820 | Nmap · BSD, macOS 10, Linux, Solaris · BSD, macOS 10, Linux · Novell · Cisco IOS · Solaris |
| **SACK OK** | Set · Not set | Linux, Windows, Open BSD · Nmap, FreeBSD, macOS 10, Novell, Cisco IOS |

"This table can help compare and identify OS fingerprinting attempts." _(Mod 14 p37)_

## ICMP-based OS fingerprinting _(Mod 14 p39)_

Tools "send a **specific ICMP probe** to the target" and "manipulate the ICMP probe in different ways to detect the target OS":

- Some tools use **unique ICMP probes**.
- Some tools use **ICMP echo requests with an unusual ICMP code**.
- Some tools use **ICMP timestamp requests (13)**, **ICMP information requests (15)**, **ICMP address mask requests (17)**, etc.

Defence: "use various traffic filters on ICMP and check for these types of ICMP requests **being received from the outside**." _(Mod 14 p39)_

## TCP-based OS fingerprinting _(Mod 14 p40)_

"The attacker sends **TCP probe packets** to the target and then waits for a response." Tools named: **Nmap** and **Queso**.

Fields that indicate OS fingerprinting attempts (callout): **the initial sequence number, timestamp, IP ID sequence, and TCP options**.

| Probe / method | What the attacker does | Response detail the page gives |
|---|---|---|
| **FIN probe** | Sends a **FIN packet without an ACK or a SYN flag** to an open port | "Many broken OS implementations such as **Microsoft Windows, Berkeley Software Design Inc. (BSDI), Cisco, Hewlett Packard Unix (HP/UX), Multiple Virtual Storage (MVS), and IRIX** reply to a FIN probe with **RESET**" |
| **BOGUS flag probe** | Sends a **SYN packet with an undefined TCP "flag"** in the TCP header | "**Linux OS versions prior to 2.0.35** respond to this packet **with the flag set**" |
| **TCP initial window** | Checks the **size of the window field** in the response | — |
| **TCP initial sequence number (ISN) sampling** | Sends a connection request, then finds **specific patterns in the ISNs** of the response | — |
| **Interface pointer identifier (IPID) sampling** | Checks the **IPID value for each packet** in the response | "**Most OSes increment a system-wide IPID value**" |
| **TCP timestamp** | Checks the **TCP timestamp option values** in the response | "It may be at frequencies of **2, 100, or 1000 Hz**, and still others return **O**" |
| **Do-not-fragment bit** | Some OSes set a **"do not fragment" bit** in the response | — |
| **ACK value** | Checks the **ACK field** in the response | — |

## Nmap's OS fingerprinting process _(Mod 14 pp41–42)_

- "**OS fingerprinting is one of the main features of Nmap.**" Nmap "sends a **series of TCP and UDP packets** to remote hosts and **examines every bit in the response**."
- Results for all tested fields are compared with its database **`nmap-os-db`**. "If the database finds a match for the tested fields, it gives the OS information."
- The database holds "a complete description of the OS, including the **vendor name, OS generation, OS type, and device type**".
- Nmap "investigates the TCP/IP stack of systems by sending them **eight different packets**" _(printed; nine tests are then listed)_. The target responds with **different or the same TCP/IP stacks**, which lets Nmap "determine accurate information on the OS running on the target machine **and its version**".
- "**All the matched OS fingerprints are saved in a text file in Nmap called `nmap-os-fingerprints`.**"

### Nmap test packets _(Mod 14 pp41–42)_

| Test | Packet sent |
|---|---|
| **Tseq** | A series of **SYN packets** to the targets to analyze their TCP sequence numbers |
| **T1** | A **SYN** packet with the options **(WNMTE)** to an **open** TCP port |
| **T2** | A **NULL** packet with the options (WNMTE) to an **open** TCP port |
| **T3** | A **SYN, FIN, PSH, and URG** packet with the options (WNMTE) to an **open** TCP port |
| **T4** | An **ACK** packet with the options (WNMTE) to an **open** TCP port |
| **T5** | A **SYN** packet with the options (WNMTE) to a **closed** TCP port |
| **T6** | An **ACK** packet with the options (WNMTE) to a **closed** TCP port |
| **T7** | A **FIN, PSH, and URG** packet with the options (WNMTE) to a **closed** TCP port |
| **PU** | A packet sent to a **closed UDP port** |

### Methods attackers use to determine the target OS _(Mod 14 p42)_

- Did the **target host respond**?
- Did the target host have the **"do not fragment" bit set**?
- What is the **window size** of the target host?
- What is the **status of the ACK number** for the TCP packet sent to Nmap?
- Which **flags are set** in the TCP packet?

"These methods can be applied to **any version of any OS**." _(Mod 14 p42)_

## Indicators to monitor in Wireshark for Nmap _(Mod 14 p41)_

- **ICMP echo request (type 8) with no payload**
- ICMP echo request (type 8) with a **120- or 150-byte payload of `OxOOs`**
- **ICMP timestamp request with the origin timestamp value set to `O`**
- **TCP SYN with a 40-byte options area**
- TCP SYN with the **window scale shift count set to 10**
- TCP SYN with the **maximum segment size set to 256**
- TCP SYN with the **timestamp value set to `OxFFFFFFFF`**
- **TCP packet with options and SYN, FIN, PSH, and URG bits set**
- **TCP packet with options and no flags set**
- **A non-zero TCP acknowledgement number field without the ACK bit set**
- **TCP packets with unusual window size field values**

## Filters the page names but does not print legibly

Both callouts on the ICMP and TCP fingerprinting pages introduce a filter and then print it garbled; the strings are not reconstructed here. _(Mod 14 pp39–40)_

```
Use the following filter to locate unusual ICMP requests:
(icmp. ( ! e (icmp. I I . 1 .

Use the following filter to find OS fingerprinting attempts:
(tcp. (tcp. window size <1025) tcp. tcp. O tcp. options .wscale tcp. options . ms
```

## Related

- Nmap as a *scanner* rather than a fingerprinter: [[14-LO04d-Nmap-Scan-Traffic-Ping-Sweep-ARP-Sweep-and-TCP-Scans]]
- The tool and its filters: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]







