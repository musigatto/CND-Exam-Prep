---
type: note
module: "14"
lo: "04"
tags: [threat, command, mod/14]
topic: "SYN/FIN DDoS, UDP scan and password cracking traffic"
exam_weight: unknown
status: done
unresolved:
  - "p49 the SYN/FIN filter is printed as 'tcp.flags==Ox003' in the callout and 'tcp.fIags==OX003' in the body; the leading character of the hex literal is the letter O in both. Reproduced verbatim, not corrected."
  - "p50 the callout filter is garbled — 'Use the following filter to view packets with an ICMP Type-3 Code-3 port to detect a UDP scan attempt: icmp . and .' — and is not reconstructed. The body on the same page gives icmp.type==3 and icmp.code==3."
  - "p52 the body opens 'FFTP is a standard protocol to transmit files between systems over the Internet using the TCP/IP suite'. The token 'FFTP' is a source typo; the note body refers to it as FTP and the rest of the paragraph is quoted from the same page."
  - "p50 the callout says a large number of ICMP Type 3 Code 3 responses means 'then the port is unavailable', while the body says no response received means the port is either open or filtered. Both reproduced from their own page."
  - "pp49, 50, 52 carry Wireshark GUI captures (the SYN/FIN packet list, the 'Port unreachable' ICMP listing, the FTP password-cracking listing). Not treated as evidence here."
---

[[MOC-Module-14]]

# SYN/FIN DDoS, UDP Scan and Password Cracking Traffic (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp49–52.

## Master table _(Mod 14 pp49–52)_

| Attack | What the attacker does | What the traffic shows | Filter the page names |
|---|---|---|---|
| **SYN flood** | Sends a **succession of SYN requests**; then **does not respond with an ACK** as expected in the last step of the three-way handshake | "The server **waits indefinitely for the ACK, causing network congestion**" | — |
| **SYN/FIN DDoS** | "The attacker floods the network by **setting both SYN and FIN flags**" | "In a typical TCP communication, **SYN and FIN are not set simultaneously**. Traffic with **both SYN and FIN flags set is a sign of a SYN/FIN DDoS attempt**" | `tcp.flags==Ox003` |
| **UDP scan** | Sends **UDP packets to a target port** and waits for the response | **ICMP Type-3 Code-3** ⇒ port **closed** · **no response** ⇒ port **open or filtered**. "If any machine replies with **bulk ICMP type-3 responses**, it is a sign of a UDP scan attempt" | `icmp.type==3` and `icmp.code==3` |
| **Password cracking** | Trial and error (**brute-force**) or guessing from commonly used words (**dictionary**) against services such as **FTP, SSH, POP3, HTTP, Telnet, RDP** | "the **number of login attempts made from the same IP address or username**" | `ftp.request.command`; `ftp.response.code==230` (success) · `ftp.response.code==530` (failure) |

## SYN / SYN-FIN DDoS _(Mod 14 p49)_

- **SYN attack:** "the attacker sends a **succession of SYN requests** to the target's system **to make the system unavailable for legitimate users**. It exploits a known weakness in the TCP connection."
- **TCP three-way handshake**, as printed:

  1. The client sends a **SYN** packet to request a connection.
  2. The server responds with **SYN/ACK**.
  3. The client then responds with an **ACK** to establish the connection.

- **SYN flood:** "initiated by **not responding to the server with an ACK** as expected in the last step of the TCP three-way handshake. The server **waits indefinitely for the ACK, causing network congestion**."
- **Flag semantics:** "**The SYN flag establishes a connection, while the FIN flag terminates a connection.**"
- **SYN/FIN DDoS:** "the attacker floods the network by **setting both SYN and FIN flags**. In a typical TCP communication, **SYN and FIN are not set simultaneously**. Traffic with both SYN and FIN flags set is a **sign of a SYN/FIN DDoS attempt**, which **can exhaust the firewall on the server by regularly sending packets**."
- Detection: use the filter `tcp.flags==Ox003` "to determine whether these traffic entries are in the same packet".

## UDP scan _(Mod 14 p50)_

- "The **UDP service can receive packets without establishing a connection**." When an attacker sends a UDP packet to the target:

| Target port state | Result |
|---|---|
| **Open** | The target **accepts the packet and does not send any response** |
| **Closed** | "an **ICMP packet is sent in response**" — printed as an **ICMP Type-3 Code-3** response |

- "**UDP scanning is more difficult to probe than TCP scanning** as it does not depend on the acknowledgements received. **A UDP scan gathers all the ICMP errors received from closed ports.**"
- Detection: "if any machine replies with **bulk ICMP type-3 responses**, it is a sign of a UDP scan attempt on the network." Use the filters `icmp.type==3` and `icmp.code==3`.
- "Network defenders should take proper measures to **handle open UDP ports** to avoid any intrusion in the network."

## Password cracking _(Mod 14 p51)_

- "Password cracking is a process of **gaining or recovering passwords** either through **trial and error** or by making **password guessing attempts with the most commonly used passwords**; these techniques are called **brute-force attacks** and **dictionary attacks**, respectively."
- **Brute-force:** "Though brute-force attacks can be a lengthy process, attackers use **various tools** to implement them on networks."
- **Dictionary:** "the attacker uses a **limited set of words**." "It is **easier for attackers to perform a dictionary attack with SSH services running in the network**." "**SSH dictionary attacks rely on log files or network traffic.**" "A dictionary attack can be accomplished easily on an account that has a **weak password**." It is performed on a **single target machine or on a network**.
- **Detection:** "Network defender can detect this type of attack by **monitoring the number of login attempts made from the same IP address or username**."
- Services the page lists: **FTP, SSH, POP3, HTTP, Telnet, RDP**.

### Example — FTP password cracking _(Mod 14 p52)_

- FTP context as printed: "a standard protocol to transmit files between systems over the Internet using the **TCP/IP suite**"; a "**client server protocol relying on two communication channels** between a client and server — **one manages conversations, and the other is responsible for the actual content transmission**". A client initiates a session with a **download request**, to which the server responds with the requested file. "An FTP session **requires the user to login** to the FTP server with their username and password."
- "In an FTP password attack, the attacker attempts to gain the user's password."

| Purpose | Filter |
|---|---|
| Detect an FTP password cracking attempt / list all FTP requests / show the **number of attempts** made to gain access to the FTP server | `ftp.request.command` |
| **Successful** FTP password cracking attempt | `ftp.response.code==230` |
| **Unsuccessful** FTP password cracking attempt | `ftp.response.code==530` |

## Related

- Scanning techniques and their filters: [[14-LO04d-Nmap-Scan-Traffic-Ping-Sweep-ARP-Sweep-and-TCP-Scans]]
- Credentials in cleartext over FTP/Telnet/HTTP: [[14-LO04b-Plaintext-Protocol-Traffic-FTP-TFTP-UFTP-Telnet-HTTP]]
- The tool and its filters: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]







