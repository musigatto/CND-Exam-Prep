---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "WEP encryption"
exam_weight: unknown
status: done
unresolved:
  - "p29 summary line reads 'The 64-, 1280 and 256-bit WEP versions use 40-, 104-, and 232-bit keys respectively' - '1280' is an OCR artefact and three key values are given against four WEP sizes, so 'respectively' does not align one-to-one in that sentence. The size-to-key mapping below is taken from the p29 prose (64/128/152/256-bit WEP against 40/104/128/232-bit keys), not reconstructed from the broken summary line."
  - "p29 WEP diagram label reads 'WEP Key Store (RI, KZ, K3,K4)' - RI, KZ, K3 and K4 are garbled identifiers, not reconstructed. Quoted verbatim only."
  - "p30 'Problems with WEP' is numbered 1-9 in the PDF but the OCR emitted the nine numerals as a single run ahead of the text, detached from their items. Only eight distinct statements were captured, so item-to-number alignment is NOT recoverable; the statements are listed in reading order and are NOT numbered."
  - "p30 renders bullet glyphs as the letter o, e.g. 'decrypt WEP packets in o real-time' and 'IV values can be reused'. Normalised to the plain reading in prose; the glyph itself carries no meaning."
  - "p30 'Denial-of-service' and the 24 GB decryption-table item are adjacent but the PDF's numbering, which would show whether they are one item or two, is unrecoverable. Kept as separate bullets."
---

[[MOC-Module-13]]

# WEP Encryption (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp28–30.

## Section objective _(Mod 13 p28)_

*"explain the various encryption mechanisms used in wireless networks, such as **WEP encryption,
wireless fidelity (Wi-Fi) protected access (WPA) encryption, Wi-Fi protected access 2 (WPA2)
encryption, Wi-Fi protected access 3 (WPA3) encryption**. This section also describes the
**limitations** of these encryption mechanisms."*

## Definition and purpose _(Mod 13 p29)_

- *"Wired Equivalent Privacy (WEP) is a security protocol defined by the **802.11b standard**; it
  was designed to provide a wireless LAN with a level of security and privacy **comparable to a
  wired LAN**."*
- Specified by the **802.11 MAC implementation**. Objective: make WLAN communication **as
  trustworthy as a wired LAN** communication.
- *"WEP contributes **two vital segments** to the architecture of wireless security. They are the
  **validation of data** and the **secrecy of the data**."*
- Cipher: **Rivest cipher 4 (RC4)**, used with a key → *"a symmetric"* mechanism.

## Key construction _(Mod 13 p29)_

- A **24-bit arbitrary number** called the **initialization vector (IV)** is added to the WEP key.
- *"The WEP key and the IV together are called as a **WEP seed**."*
- WEP seed → input for **RC4** → **keystream**. The keystream is **bit-wise XORed** with the
  combination of **data + integrity check value (ICV)** → encrypted data.
- **CRC-32** checksum → **32-bit ICV** for the data, added to the data frame.
- **IV field (IV+PAD+KID)** added to the cipher text → **MAC frame**.

| WEP version | Secret key | Hex characters | With 24-bit IV |
|-------------|-----------|----------------|----------------|
| 64-bit | **40 bits** | 10 hex digits — 4 bits | 40 + 24 = 64 |
| 128-bit | **104 bits** | 26 hex digits — 4 bits | 104 + 24 = 128 |
| 152-bit | **128 bits** | not stated | 128 + 24 = 152 |
| 256-bit | **232 bits** | not stated | 232 + 24 = 256 |

*"A standard **64-bit WEP** is used as a string of **10 hexadecimal (base 16) characters (0-9, A-F)**.
Each character has 4 bits and 10 digits of 4 bits is 10 x 4 = 40 bits (**WEP-40**)."* _(Mod 13 p29)_
*"the **128-bit WEP** … uses a 104-bit key. The 128-bit key is entered as a **26 hexadecimal
character**."* _(Mod 13 p29)_

## WEP diagram — p29 labels (verbatim)

```text
[ p29 WEP encryption diagram — labels as captured, reading order ]

WEP Key Store (RI, KZ, K3,K4)  ->  WEP Seed  ->  WEP Key  ->  Cipher  ->  XOR Algorithm
CRC.32  ->  PAD  ->  KID  ->  Ciphertext  ->  WEP-encrypted Packet (Frame body Of MAC Frame)
```

## Working of WEP (RC4) — the steps _(Mod 13 pp29–30)_

1. Packets to be transmitted are passed through an **integrity check algorithm** to generate a
   **checksum** — *"the checksum avoids a message from being changed"*.
2. The **24-bit IV** together with a **40-bit WEP key** produces the **64-bit key**. RC4 uses this
   key to generate the **key stream**, which has the **same length as the plain text** (original
   message with the checksum included).
3. *"The keystream is **exclusive ORed (XORed)** with the original message or the plain text along
   with the checksum. This generates a **cipher text** or an encrypted packet."*
4. *"The client on the other hand, receives the encrypted text and **XORs it with the same key
   stream** to generate the plain text or the original message. The client **validates with the
   checksum** in order to authenticate the message."*

## Problems with WEP _(Mod 13 p30)_

> [!warning] Item numbers lost
> The PDF numbers these **1–9**; the OCR emitted the nine numerals as one run detached from the
> text. The eight captured statements are listed in reading order, **unnumbered**.

- **CRC32 insufficient** — *"By capturing two packets, an attacker can reliably **flip a bit** in the
  encrypted stream and **modify the checksum** so that the packet is accepted."*
- **IVs are 24-bit** — *"An AP broadcasting **1500 byte packets at 11 Mb/s** would **exhaust the
  entire IV space in five hours**."*
- **Known plaintext attacks** — *"When there is an **IV collision**, it becomes possible to
  **reconstruct the RC4 key stream** based on IV and the decrypted payload of the packet."*
- **Dictionary attacks** — *"WEP is based on a password. The **small space of the IV** allows the
  attacker to create a **decryption table**, which is nothing but a dictionary attack."*
- **Denial-of-service** — *"**Associate and disassociate messages are not authenticated**."*
- **Decryption table** — *"With about **24 GB of space**, an attacker can use this table to decrypt
  WEP packets in **real-time**."*
- **No centralized key management** — *"makes it difficult to **change the WEP keys with any
  regularity**."*
- **IV definition / weak randomness** — *"IV is a value that is used for **randomizing the key
  stream** value, and each packet has an IV value: The standard allows only 24 bits that can be used
  **within hours at a busy AP**."* Sub-points: **IV values can be reused**; *"The standard **does
  not dictate that each packet must have a unique IV**, and thus vendors use only a small amount of
  the available 24-bit possibilities"*; *"A mechanism that depends on **randomness is not truly
  random** and attackers can easily figure out the key stream and decrypt other messages."*

Full treatment of the WEP/WPA/WPA2 weaknesses → [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] ·
successors → [[13-LO02b-WPA-Encryption]] · [[13-LO02c-WPA2-Encryption]] ·
[[13-LO02d-WPA3-Encryption]] · side-by-side → [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] ·
standard history → [[13-LO01c-Wireless-Network-Standards]]







