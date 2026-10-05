---
type: note
module: "13"
lo: "02"
tags: [threat, crypto, mod/13]
topic: "Issues in WEP, WPA and WPA2"
exam_weight: unknown
status: done
unresolved:
  - "p39 reads 'A busy AP can use all 224 available IV values within hours'. 224 is printed as a plain number where the context (a 24-bit IV space) suggests a power of two. NOT corrected to 2^24; quoted verbatim and flagged."
  - "p40 names 'The Hole 96 vulnerability in WPA2' as the cause of the man-in-the-middle and DoS attack. 'Hole 96' is a garbled or vendor-specific identifier; no expansion, CVE number or year is given anywhere in the module. Quoted verbatim, not reconstructed."
  - "p40 writes 'Clients using WPA-TKIP' - WPA-TKIP is the courseware's own wording (TKIP is the WPA cipher). Left as printed inside the quotation."
  - "p30 of the preceding slice (13-LO02a) prints the same WEP problem list numbered 1-9 but with the nine numerals emitted as a detached run, so no item-to-number mapping is recoverable there. This note covers the same ground from the fuller p38-39 text, which is not numbered in the OCR."
  - "p38 spells 'occurance' in the known-plaintext item. Corrected to 'occurrence' as an obvious spelling slip inside a quoted phrase; the wording is otherwise unchanged."
  - "p41 'Exam 312-38' page marker appears in the OCR stream between the WPA2 DoS item and the WPS PIN item; no content was lost there."
---

[[MOC-Module-13]]

# Issues in WEP, WPA and WPA2 (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp38–41.

## Issues in WEP _(Mod 13 pp38–39)_

*"Why is WEP encryption inefficient in securing wireless networks? The answers lie in the following
issues and anomalies of WEP:"*

| # | Issue | Courseware explanation |
|---|-------|------------------------|
| 1 | **CRC32 inefficient integrity** | *"By capturing two packets, an attacker can reliably **flip a bit** in the encrypted stream and **modify the checksum** so that the packet is accepted."* |
| 2 | **IVs are 24-bit** | *"The IV is a **24-bit field, which is too small**, and is **sent in the cleartext portion of a message**. An AP broadcasting **1500-byte packets at 11 Mb/s** would **exhaust the entire IV space in five hours**."* |
| 3 | **Known plaintext attacks** | *"In the case of **occurrence of an IV collision**, it becomes possible to **reconstruct the RC4 key stream** based on the IV and the decrypted payload of the packet."* |
| 4 | **Dictionary attacks** | *"WEP is based on a password and is **prone to password cracking attacks**. The small space of the IV allows the attacker to create a **decryption table**, which is a dictionary attack."* |
| 5 | **Denial-of-Service** | *"**Associate and disassociate messages are not authenticated**."* |
| 6 | **Decryption table** | *"With about **24 GB of space**, an attacker can use this table to **decrypt WEP packets in real-time**."* |
| 7 | **No centralized key management** | *"A lack of centralized key management makes it **difficult to change WEP keys with any regularity**."* |
| 8 | **IV randomizes the keystream** | *"The standard IV allows only a **24-bit field, which is too small**, and is **sent in the cleartext portion of a message**. It is used **within hours at a busy AP**. IV is a part of the **RC4 encryption key** and leads to an **analytical attack that recovers the key** after intercepting and analyzing a relatively small amount of traffic."* |
| 9 | **Identical keystreams on IV reuse** | *"**Identical key streams are produced with the reuse of the same IV** for data protection, since the IV short key streams are **repeated within a short time**. **Wireless adapters from the same vendor may all generate the same IV sequence.** This enables attackers to determine the key stream and decrypt the ciphertext."* |
| — | **Vendors ignore the IV space** | *"The standard **does not dictate that each packet must have a unique IV**, and thus vendors use only a **small part of the available 24-bit possibilities**: A mechanism that depends on **randomness is not truly random**."* |
| — | **RC4 was a one-time cipher** | *"**Use of RC4 was designed to be a one-time cipher and not intended for multiple message use.**"* |

### The randomness argument in detail _(Mod 13 p39)_

- *"**An attacker can construct a decryption table of the reconstructed key stream** and can use it
  to decrypt the WEP packets in **real-time**."*
- *"Since most organizations have configured their network clients and APs to use the **same shared
  key, or the four default keys**, the randomness of the key stream relies on the **uniqueness of
  the IV value**."*
- *"The use of IV and a key ensures that the key stream for each packet is different. However, **in
  most cases, the IV changes, whereas the key remains constant**. Since there are only **two main
  components** to this encryption process and **only one remains constant**, the randomization of
  the process **decreases to an unacceptable level**."*
- *"A busy AP can use **all 224 available IV values within hours**, which requires the **reuse of IV
  values**. **Repetition in a process that relies on randomness, leads to failure.**"*
- *"the **802.11 standard does not require each packet to have a different IV value**. This is
  similar to having a '**Beware of Dog**' sign posted, but only a **Chihuahua** to provide a barrier
  between intruders and the valued assets."*
- *"In many implementations, the IV value **changes only when the wireless NIC reinitializes**,
  usually **during a reboot**. IV values having 24 bits provide enough possible IV combinations,
  however most implementations **use a handful of bits**, not even utilizing all the available bits
  completely."*

### Reasons for weak IVs in WEP _(Mod 13 p39)_

- *"To generate different packets in WEP, the **RC4 algorithm uses a key scheduling algorithm (KSA)
  to create an IV and adds it to the base key**, which makes the **first few bytes of the plaintext
  easily predictable**."*
- *"The **IV value is not explicit to the network**, and thus the same IV can be used with the same
  secret key on multiple wireless devices."*
- *"The way in which the IV is **appended to the beginning of the security key** makes it vulnerable
  to the **Fluhrer-Mantin-Shamir (FMS) attacks**, which allow attackers to execute script tools to
  **crack the secret key by examining the link**."*
- *"Most of the **weak IVs depends on a WEP key** and reveal accurate information about the key bytes
  from the **first RC4 output byte** as well as smaller clues from other bytes. Using **additional
  processing on the recovered bytes**, parts of the **pseudo-random generation algorithm (PRGA)**
  can be emulated to extract the key information in the byte of an IV."*

### No effective detection of message tampering _(Mod 13 p39)_

- *"Although methods such as **checksum and ICV can check the message integrity**, they have certain
  **drawbacks**."*
- *"Some **secure methods for computing MIC require high computational processing** when introduced
  to **TKIP**."*
- *"WEP **directly uses the master key** and has **no built-in provision to update the keys**."*
- *"A security flaw in the **WEP implementation of RC4** results in the generation of **weak IVs**,
  which attackers can easily exploit to **deduce the base WEP key**."*
- Attack chain: *"An attacker can use **WLAN sniffing tools** to capture packets encrypted with the
  same key and use tools such as **Aircrack-ng, WEPCrack**, etc., to **decrypt the weak IVs**,
  thereby exposing the **base WEP key**."*

## Issues in WPA _(Mod 13 p40)_

*"WPA improves over WEP in many ways by using TKIP for data encryption … However, WPA also suffers
from various security issues."*

- **Weak password** — *"If users depend on **weak passwords**, the **WPA pre-shared key** is
  vulnerable to various **password cracking attacks**."*
- **Lack of forward secrecy** — *"If an attacker is able to **capture a pre-shared key**, they can
  **decrypt all the packets** encrypted with that key (i.e., **all the packets transmitted or being
  transmitted can be decrypted**)."*
- **Vulnerable to packet spoofing and decryption** — *"Clients using **WPA-TKIP** are vulnerable to
  **packet injection attacks and decryption attacks** and this further allows attackers to
  **hijack the transmission control protocol (TCP) connections**."*
- **Predict the group temporal key** — *"An **insecure random number generator (RNG)** in WPA allows
  attackers to discover the **group temporal key (GTK)** generated by the AP. This further allows
  attackers to **inject malicious traffic** in the network and **decrypt all the traffic** that is
  being transmitted over the internet."*
- **Guessing an IP address** — *"**Vulnerabilities in TKIP** allow attackers to **guess the IP address
  of the subnet and inject small packets** onto the network to **downgrade the network
  performance**."*

## Issues in WPA2 _(Mod 13 pp40–41)_

*"WPA2 is more secure than WEP and WPA, but also has some security issues."*

- **Weak password** — *"the **WPA2 pre-shared key** is vulnerable to various attacks such as
  **eavesdropping, dictionary, and password cracking attacks**."*
- **Lack of forward secrecy** — *"If an attacker is able to capture a pre-shared key, they can
  decrypt all the packets encrypted with that key."*
- **Man-in-the-middle and DoS** — *"The **Hole 96 vulnerability** in WPA2 allows attackers to
  exploit a **shared GTK** to perform **man-in-the-middle and denial-of-service (DoS) attacks**."*
- **Predict the GTK** — *"An **insecure RNG** in WPA2 allows attackers to discover **GTK** generated by
  the AP. This further allows the attackers to **inject malicious traffic** in the network and
  decrypt all the traffic that is being transmitted over the internet."*
- **Key reinstallation attack (KRACK)** — *"WPA2 has a significant vulnerability known as a **key
  reinstallation attack (KRACK)**. This exploit may allow attackers to perform **packet sniffing,
  hijacking connections, injecting malware, and decrypting the packets**."*
- **Wireless DoS attack** _(Mod 13 p41)_ — *"Attackers can exploit the **WPA2 replay attack detection
  feature** to send **forged group addressed data frames with a large PN** to perform a **DoS
  attack**."*
- **Wi-Fi protected setup PIN recovery** _(Mod 13 p41)_ — *"In some cases, **disabling WPA2 and
  Wi-Fi protected setup (WPS)** can be a time-consuming process, where the attacker needs to control
  the **WPA2 PSK** used by the clients. When the WPA2 and WPS are enabled, the attacker can easily
  **disclose the WPA2 key by finding out the WPS PIN** by using simple steps."*

## Cross-cutting pattern

| Recurring weakness | WEP | WPA | WPA2 |
|--------------------|-----|-----|------|
| Weak / crackable password | • | • | • |
| No forward secrecy (PSK capture ⇒ decrypt everything) | not stated | • | • |
| GTK predictable via insecure RNG | not stated | • | • |
| No / weak key management | • (no centralized key management) | re-keying only | not stated |

Schemes → [[13-LO02a-WEP-Encryption]] · [[13-LO02b-WPA-Encryption]] ·
[[13-LO02c-WPA2-Encryption]] · the fix → [[13-LO02d-WPA3-Encryption]] ·
side-by-side → [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] · cracking in practice →
[[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]] · tooling → [[13-LO04i-Wireless-Security-Assessment-Tools]] ·
response measure → [[13-LO04d-Strong-Wireless-Encryption-Mode]]







