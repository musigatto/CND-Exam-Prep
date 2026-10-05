---
type: note
module: "14"
lo: "04"
tags: [protocol, port, threat, mod/14]
topic: "Plaintext protocol traffic: FTP, TFTP, UFTP, Telnet, HTTP"
exam_weight: unknown
status: done
unresolved:
  - "p33 the section is contradictory: the callout and heading expand UFTP as 'Unicast Fast Transfer Protocol' and describe it as 'a high-performance file transfer protocol', while the body calls it 'an encrypted multicast file transfer program'. Both are reproduced as printed; not reconciled."
  - "p31 states 'Individuals do not need authentication to access an FTP server in a network' but p52 states 'An FTP session requires the user to login to the FTP server with their username and password'. Both reproduced as printed."
  - "p35 prints no port number for HTTP; none supplied."
  - "pp31–35 each carry a Wireshark GUI capture. The packet lists, Info columns and hex dumps (e.g. the FTP 'USER'/'PASS'/'331'/'230' lines, the TFTP 'Read Request' / 'Data Packet. Block:' lines) are screenshot content and are not treated as evidence here."
---

[[MOC-Module-14]]

# Plaintext Protocol Traffic: FTP, TFTP, UFTP, Telnet, HTTP (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp31–35. One page per protocol; each page gives the transport and default port, whether the protocol is encrypted, and the filter the page names.

## Master comparison _(Mod 14 pp31–35)_

| Protocol | Transport / default port | Encryption & authentication | Filter named on the page | Why monitor |
|---|---|---|---|---|
| **FTP** | TCP, **default port 21** | **Cleartext**; no encryption in data transfer | `ftp` | Detect **unauthorized FTP sessions** running on the server |
| **TFTP** | UDP, **default UDP port 69** | **Plaintext**, **no authentication** | **Cannot be filtered directly** — filter on the UDP port instead | Detect **unauthorized or rogue TFTP servers or clients**; may indicate a security breach or misconfigured devices |
| **UFTP** | UDP, **default port 1044** | Described as an **encrypted** file transfer program | **Cannot be filtered directly while capturing**; display filters `uftp`, `uftp4`, `uftp5` | Unauthorized access attempts, unusual transfer volumes, atypical file types → security events and policy violations |
| **Telnet** | **Port 23** | **Not encrypted** — password and all other data as cleartext | Statistics → Conversations → TCP tab → port 23 → Follow | **Telnet traffic and credentials are viewable in cleartext** |
| **HTTP** | *(no port printed)* | **Cleartext** | `http` | Sensitive info sent over HTTP, malicious traffic, policy violations, applications using unnecessary/restricted services |

## FTP _(Mod 14 p31)_

- "FTP is used to transfer files over **TCP**, and its **default port is 21**." Sends data in a **cleartext** format.
- "FTP offers neither a secure network environment nor secure user authentication."
- "**Individuals do not need authentication to access an FTP server in a network.** This provides an easy method for attackers to enter the network and access resources."
- "FTP does not provide encryption in the data transfer process, and the data transfer between the sender and receiver is in **plain text**." → **critical information such as usernames and passwords is exposed to attackers.**
- "The implementation of FTP in an organization's network leaves the data accessible to external sources."
- Attacks the page names: **FTP bounce, FTP brute force, packet sniffing attacks**.
- Defence: applying an FTP filter helps detect unauthorized sessions running on the server. **Apart from monitoring traffic on the FTP server, the existing file contents and file sizes in the server should be monitored.**
- Filter: `ftp` — "to check whether any unauthorized FTP sessions have been established in the network".

## TFTP — Trivial File Transfer Protocol _(Mod 14 p32)_

- "Trivial File Transfer Protocol (TFTP) is a **plaintext** file transfer protocol used to send and receive data **without authentication**."
- Primary applications: **firmware upgrades** and related tasks, especially when the client requesting the data has **limited processing capabilities**.
- "Although efficient and easy to use, TFTP is **quite unsafe** due to its **lack of encryption and absence of authentication**."
- Monitoring goal: detect any **unauthorized or rogue TFTP servers or clients**; "Such unauthorized TFTP activity might indicate a **security breach or misconfigured devices**."
- **Capture caveat:** "TFTP protocols **cannot be captured directly**. However, you can filter on TFTP **if you know the UDP port used**, since TFTP uses **UDP** as its transport protocol. The **default UDP port for TFTP traffic is 69**."

## UFTP — Unicast Fast Transfer Protocol _(Mod 14 p33)_

- Heading/callout: "**Unicast fast transfer protocol (UFTP)** is a **high-performance** file transfer protocol commonly used for **fast file transfers for distributing large files across a network**."
- Body: "**Unicast Fast Transfer Protocol (UFTP), an encrypted multicast file transfer program**, securely transfers files to multiple receivers simultaneously. It is particularly useful for distributing large files over a **satellite link (with two-way communication)** to a large number of receivers."
- Monitoring goals: identifying potential security vulnerabilities or suspicious activity — **unauthorized access attempts, unusual transfer volumes, atypical file types**; by examining content and behaviour you can identify **security events and policy violations**.
- **Capture caveat:** "you **cannot directly filter UFTP protocols while capturing**. You can capture only the UFTP traffic over the **default port 1044**, since UFTP uses **UDP** as its transport protocol."
- Display filter fields are referenced in the **display filter reference**: `uftp`, `uftp4`, `uftp5`.

## Telnet _(Mod 14 p34)_

- "Telnet can provide access to **remote hosts including most network equipment and operating systems**."
- "The Telnet protocol works on a **client—server model**." Data transferred through Telnet is **not encrypted**, making it easy for intruders to eavesdrop.
- "If a person has access to a network device with Telnet configured, they can gain access to the network and user account information."
- "Telnet is a **session-oriented** protocol, which implies that the **connection must be open for the entire session**." → "Attackers can use Telnet open sessions to perform a network security breach."
- Recommendation: **Telnet should be disabled in an organization**; enabling it "poses huge security risks to the network". Monitoring Telnet sessions through Wireshark "can greatly minimize the risk for network intrusion".

### Checking for established Telnet sessions _(Mod 14 p34)_

1. Go to the **Statistics** menu and click on **Conversations**.
2. Go to the **TCP** tab and select the appropriate Telnet communication **indicated by port 23**, and click **Follow**.
3. The Telnet traffic and the credentials will be **viewable in cleartext**.

## HTTP _(Mod 14 p35)_

- "Applications implementing HTTP send data in **cleartext**." Sensitive information such as **usernames and passwords** is sent over as HTTP requests; "The attacker can easily sniff the traffic and steal sensitive information for malicious use."
- Mandate: defenders "must ensure that their HTTP traffic is sent over an **encrypted protocol such as HTTP Secure (HTTPS)**", and "monitor applications and ensure that they **do not send data over HTTP**".
- "Monitoring the HTTP traffic also helps **detect the volume of HTTP traffic** in the network."

### Four reasons to monitor HTTP traffic _(Mod 14 p35)_

- Check whether any **sensitive information** is sent using HTTP
- **Detect malicious traffic**
- Check the traffic against a **policy violation**
- **Detect applications using unnecessary/restricted services**

Filter: `http` — "to check the specific HTTP traffic".

## Related

- Credentials over the wire: [[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]] (FTP password cracking, `ftp.response.code` 230 / 530)
- Filters and the tool itself: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]
- Encrypted / handshake alternatives to these plaintext protocols: [[14-LO04j-Name-Service-Encrypted-and-Handshake-Traffic]]







