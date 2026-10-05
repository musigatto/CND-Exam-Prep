---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "WEP vs WPA vs WPA2 vs WPA3"
exam_weight: unknown
status: done
unresolved:
  - "p37 Table 13.2, WPA3 'IV Size' cell: the OCR prints 'Arbitrary length 1- 264' at the foot of the page and 'Arbitrary length I- 264' at the top. The exponent/superscript is lost, so the actual value is NOT recoverable. Quoted verbatim; not reconstructed as 2^64."
  - "p37 Table 13.2 has a row labelled 'Attributes' that carries NO cell values in either of the two OCR passes of the table. The row is kept with empty cells; nothing was invented for it."
  - "p37 after the Integrity Check Mechanism row the OCR prints a second header run 'WEP, WPA | WPA2 | WPA3' followed by three statements: 'Should be replaced with more secure WPA and WPA2', 'Incorporates protection against forgery and replay attacks' and 'Provides enhanced password protection, secured IoT connections and encompasses stronger encryption techniques'. Whether these are further table rows or caption/prose is NOT recoverable, so they are listed separately and not placed in the table."
  - "p37 Table 13.2 gives WPA3 'Encryption Key Length' as 192-bits while p35 describes WPA3 as using 256-bit GCMP. The source does not reconcile the two figures."
  - "p37 renders the section title with umlaut dots as 'WPÃ„2' and 'WPÃ„3'. Normalised to WPA2 / WPA3."
---

[[MOC-Module-13]]

# WEP vs WPA vs WPA2 vs WPA3 (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers p37 — Table 13.2 and the comparison prose.

## Table 13.2 — Differences between WEP, WPA, WPA2, WPA3 _(Mod 13 p37)_

> [!info] Alignment reconstructed from two consistent OCR passes
> p37 carries the **same table twice** (once at the head of the page, once above the caption).
> In both passes every row label is followed by **exactly four cell values in WEP → WPA → WPA2 →
> WPA3 order**, so the column alignment is recoverable and the table below is not invented. The
> raw row-value sequences are reproduced underneath for verification.

| Attribute | WEP | WPA | WPA2 | WPA3 |
|-----------|-----|-----|------|------|
| **Encryption Algorithm** | RC4 | RC4, TKIP | AES-CCMP | AES-GCMP 256 |
| **IV Size** | 24-bits | 48-bits | 48-bits | Arbitrary length 1- 264 *(OCR — exponent lost)* |
| **Attributes** | | | | |
| **Encryption Key Length** | 40/104-bits | 128-bits | 128-bits | 192-bits |
| **Key Management** | None | 4-way handshake | 4-way handshake | ECDH and ECDSA |
| **Integrity Check Mechanism** | CRC-32 | Michael algorithm and CRC-32 | CBC-MAC | BIP-GMAC-256 |

```text
[ p37 Table 13.2 — raw OCR row-value sequences, both passes ]

pass 1 (head of page)
  header              : WEP | WPA | WPA2 | WPA3
  Encryption Algorithm: RC4 | RC4, TKIP | AES-CCMP | AES-GCMP 256
  IV Size             : 24-bits | 48-bits | 48-bits | Arbitrary length I- 264
  Attributes          : (no values captured)
  Encryption Key Length: 40/104-bits | 128-bits | 128-bits | 192-bits
  Key Management      : None | 4-way handshake | 4-way handshake | ECDH and ECDSA
  Integrity Check Mechanism: CRC-32 | Michael algorithm and CRC-32 | CBC-MAC | BIP-GMAC-256

pass 2 (above the caption, 'Table 13.2: Differences between WEP, WPA, WPA2, WPA3')
  Encryption Algorithm: RC4 | RC4, TKIP | AES-CCMP | [AES-GCMP 256 interleaved mid-row]
  IV Size             : 24-bits | 48-bits | 48-bits | Arbitrary length 1- 264
  Attributes          : (no values captured)
  Encryption Key Length: 40/104-bits | 128-bits | 128-bits | 192-bits
  Key Management      : None | 4-way handshake | 4-way handshake | ECDH and ECDSA
  Integrity Check Mechanism: CRC-32 | Michael algorithm and CRC-32 | CBC-MAC | BIP-GMAC-256

[ trailing block in pass 1, row type NOT recoverable ]
  header run printed  : WEP, WPA | WPA2 | WPA3
  Should be replaced with more secure WPA and WPA2
  Incorporates protection against forgery and replay attacks
  Provides enhanced password protection, secured IoT connections and
    encompasses stronger encryption techniques
```

## The comparison prose _(Mod 13 p37)_

- *"**WEP** initially provided data confidentiality on wireless networks. However, it was **weak and
  failed to meet any of its security goals**."*
- *"**WPA** fixed **most of the problems of WEP**."*
- *"**WPA2** makes wireless networks **almost as secure as wired networks**. WPA2 **supports
  authentication**, so that only **authorized users** can access the network."*
- *"**WEP should be replaced with either WPA or WPA2** in order to secure a Wi-Fi network."*
- *"Though **WPA and WPA2** incorporate protection against **forgery and replay attacks**, **WPA3**
  can provide an **enhanced password protection** mechanism and **secured internet of things (IoT)
  connections**, and it encompasses **stronger encryption techniques**."*
- Scope of the table, per the courseware: *"a comparison between WEP, WPA, WPA2, and WPA3 in terms of
  the **encryption algorithm** used, **size of the encryption key**, the **IV** it produces, **key
  management**, and **data integrity**."*

## Exam traps visible in this page

- **WEP** is the only scheme with **no key management** (`None`) — and the only one whose IV is
  **24-bit**.
- **WPA and WPA2 share the 4-way handshake**; **WPA3 is the odd one out** with **ECDH and ECDSA**.
- **Integrity chain** CRC-32 → Michael + CRC-32 → CBC-MAC → **BIP-GMAC-256**; note the table puts
  **CRC-32 in both the WEP and WPA** cells.
- **Table says WPA2 = AES-CCMP**, but the WPA2 cell for the integrity mechanism is **CBC-MAC** only
  (no CRC-32).

Per-scheme detail → [[13-LO02a-WEP-Encryption]] · [[13-LO02b-WPA-Encryption]] ·
[[13-LO02c-WPA2-Encryption]] · [[13-LO02d-WPA3-Encryption]] · weaknesses →
[[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] · deployment measure →
[[13-LO04d-Strong-Wireless-Encryption-Mode]]






