---
type: note
module: "14"
lo: "03"
tags: [process, threat, concept, protocol, bestpractice, mod/14]
topic: "Attack signature analysis techniques"
exam_weight: unknown
status: done
unresolved:
  - "p21 the figure text 'Attack signatures are contained in packet' for content-based analysis is split from 'payloads' on the context-based branch by the OCR; the diagram is read as content-based=payloads, context-based=headers, per the two callout texts ('Check for specific strings occurring in the suspicious payload' and 'Inspect packets for unusual/suspicious header information'). The reading is not stated in the source."
  - "p21 header field list prints 'IP options, protocols, and checksums'; p22 prints the same list as 'IP options, protocol, and checksums'. Both forms kept."
  - "p21 the context-based body list shows 5 bullet markers ('o o o o O') for 5 readable items; no reading inferred from the marker count."
  - "p22 a stray binary-garbage token precedes the header-field bullet list. Removed."
  - "p22 the example given for looking for shellcode exploitation is only 'Another method is to look for any exploitation of shellcode sequences in the payload' - no shellcode sequence is printed anywhere in the section. Not supplied."
---

[[MOC-Module-14]]

# Attack Signature Analysis Techniques (§14.03)

> **LO#03: Determine baseline traffic signatures for normal and suspicious network traffic** _(Mod 14 LO#03)_
> Covers pp21–22. *"Attack signature analysis techniques are classified into four different categories
> as follows."* _(Mod 14 p21)_

## The four techniques _(Mod 14 p21)_

| Technique | Figure text | Body text |
|-----------|-------------|------------|
| **Content-based signature** | attack signatures are contained in packet **payloads** — *"Check for specific strings occurring in the suspicious payload"* | *"detected by **analyzing the data in the payload and matching a text string to a specific set of characters**."* If undetected, *"these signatures can **open backdoors in a system, providing administrative controls to an outsider**."* |
| **Context-based signature** | **headers** — *"Inspect packets for unusual/suspicious header information"* | *"**Packets are usually altered using the header information.** Suspicious signatures in the header can include malicious data that can affect"* the header fields listed below |
| **Atomic signature** | *"**Single-packet analysis is sufficient** to detect attack signatures"* | *"network defender need to **analyze a single packet** to determine whether the signature includes malicious patterns. Network defenders **do not require any knowledge of past or future activities** to detect these signature patterns."* |
| **Composite signature** | *"**Multiple-packet analysis is required** to detect attack signatures"* | *"network defenders need to **analyze a series of packets over a long period of time** to detect composite attack signatures. Detecting these attack patterns is **exceedingly difficult**."* **Example: ICMP flooding** — *"multiple ICMP packets are sent to a single host so that the server remains busy responding to the requests."* |

Atomic vs composite = **one packet, no context** vs **a series of packets over time** — the only
structural difference the section draws.

## Header fields that can carry malicious data _(Mod 14 pp21–22)_

Listed twice, once under the context-based technique and once under header inspection:

| Header field |
|--------------|
| **Source and destination IP addresses** |
| **Source and destination port numbers** |
| **IP options, protocol(s), and checksums** _(p21 "protocols" · p22 "protocol")_ |
| **IP fragmentation flags, offset, or identification** |

## Unusual / suspicious information in the header _(Mod 14 p22)_

- *"The attacker can **alter the packet header information to bypass the filter and enter the
  network**."*
- *"To detect packets with malicious header formats, network defenders should **understand the header
  fields they can modify**."* Knowing the possible header signatures *"helps them take **remediation
  actions** against suspicious packets."*
- Key point: **"valid headers can have suspicious header values"** — an illegal header value is
  certainly a fundamental component of signatures, but legality alone is not sufficient.
  - *"suspicious connections to port numbers may provide a **quick method to identify possible trojan
    activity**"* — *"Unfortunately, **normal traffic may also use these odd port numbers**."*
  - *"A **detailed signature includes other traffic characteristics** and is needed to determine the
    true nature of this traffic."*
  - **"Suspicious but legal values such as a port number are best used in combination with other
    values."**

## Suspicious data in the payload _(Mod 14 p22)_

- **"Attacker signatures may be in either the header or payload of the packet."**
- *"They should **check for specific strings occurring in the payload of each packet** before allowing
  it through the network."*
- Examine the packet payloads **within TCP and UDP**; *"protocols such as **DNS are contained within
  TCP or UDP**."*
- Parse order:
  1. *"Decoding a packet's **IP header** information gives a clear indication of whether its payload
     contains **TCP, UDP, or another protocol**."*
  2. *"If the payload is in **TCP**, network defenders need to **process some of the TCP header
     information within the IP payload** before accessing the TCP payload."*
  3. *"**DNS data are contained within UDP and TCP payloads.**"*
- Printed example: *"an example is a **DNS buffer overflow attempt contained in the payload of a
  query**. By **parsing the DNS fields and checking the length of each**, network defenders can
  identify an attempt to perform a buffer overflow using a DNS field."*
- *"Another method is to **look for any exploitation of shellcode sequences in the payload**."* No
  shellcode sequence is printed in the section.






