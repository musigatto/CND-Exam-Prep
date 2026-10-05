---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "WPA2 encryption"
exam_weight: unknown
status: done
unresolved:
  - "p33 CONTRADICTION on the WPA2-Personal key size. The callout says 'each wireless network device encrypts the network traffic using a 128-bit key that is derived from a passphrase of 8 to 63 ASCII characters'; the body text on the same page says 'Each wireless device uses the same 256-bit key generated from a password'. 128-bit and 256-bit are both given for WPA2-Personal. Both are quoted as printed; neither is chosen."
  - "p33 the WPA2-Personal body also states 'The router uses a combination of a passphrase, a network SSID and a TKIP to generate a unique encryption key for each wireless client', which names TKIP inside the WPA2 section. The courseware does not explain why TKIP appears here. Quoted as printed."
  - "p33 the WPA2-Enterprise body ends 'WPA-Enterprise assigns a unique ciphered key to every system and hides it from the user' - the sentence says WPA-Enterprise inside the WPA2 section. Quoted as printed; the source does not reconcile the label."
  - "p33 renders the IEEE standard number as '802.1 li'. Normalised to 802.11i in prose; the raw form is kept in the verbatim card below."
  - "p34 Figure 13.1 labels read 'AES ority destination address' and 'Confwrator' style garbling - 'ority destination address' is a broken fragment, not reconstructed. Only the readable label tokens are listed."
  - "p33 the WPA2 callout prints 'WPA2-PersonaI' with a capital letter I for the l. Normalised to WPA2-Personal in prose."
---

[[MOC-Module-13]]

# WPA2 Encryption (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp33–34.

## Definition _(Mod 13 p33)_

- *"Wi-Fi protected access 2 (WPA2) is an **upgrade to WPA**."*
- *"Wi-Fi protected access 2 (WPA2) **depends on the IEEE 802.11i standard** for data encryption and
  has **replaced the WPA technology in 2006**."*
- *"This protocol provides **better protection compared to WPA and WEP**."*
- Encryption: **AES**, with the **counter mode cipher block chaining (CBC)-MAC protocol (CCMP)**
  — *"It includes **mandatory support** for counter mode cipher block chaining (CBC)-MAC protocol
  (control mode CBC-MAC protocol or CCMP), an **AES-based encryption mode** with strong security."*

| WPA2 element | Value |
|--------------|-------|
| Data encryption | **AES** |
| Encryption mechanism | **CCMP** — counter mode CBC-MAC protocol |
| Standard | **IEEE 802.11i** |
| Replaced WPA in | **2006** |
| Replay protection | **PN** in the CCMP header |
| Nonce | PN + a portion of the **MAC header** |

## Modes of authentication _(Mod 13 p33)_

| Mode | Courseware description |
|------|------------------------|
| **WPA2-Personal** | *"This mode is mostly used in **home networks**. It supports homes or locations where **authentication servers are not used**. Each wireless device uses the same **256-bit key** generated from a password. The router uses a combination of a **passphrase, a network SSID and a TKIP** to generate a unique encryption key for each wireless client. **These encryption keys keep changing constantly**."* |
| **WPA2-Enterprise** | *"This mode is mostly used for **securing wireless networks in organizations**. It supports networks that include the **authentication servers**. It uses **EAP or RADIUS** for **centralized client authentication** using multiple authentication methods, such as **token cards, Kerberos, certificates**, etc."* |

Callout figures for the same two modes _(Mod 13 p33)_:

- *WPA2-Personal* — *"uses a **setup password (pre-shared key (PSK))** to protect unauthorized network
  access."* · *"In the PSK mode, each wireless network device encrypts the network traffic using a
  **128-bit key** that is derived from a **passphrase of 8 to 63 ASCII characters**."*
- *WPA2-Enterprise* — *"Users are assigned **login credentials by a centralized server** which they
  must **present when connecting to the network**."*

> [!warning] 128-bit vs 256-bit for WPA2-Personal
> Both figures appear on p33 — the callout says **128-bit** derived from an **8–63 ASCII character**
> passphrase, the body says the **same 256-bit key** for every device. Not reconciled; see
> `unresolved`.

## Working of WPA2 (CCMP) _(Mod 13 pp33–34)_

1. *"additional authentication data (**AAD**) are generated using a **MAC header** and are included
   in the encryption process which uses both **AES and CCMP** encryptions. As a result, it
   **protects the non-encrypted portion of the frame** from alteration or distortion."*
2. *"The protocol uses a **sequenced packet number (PN)** and a portion of the **MAC header** to
   generate a **nonce** which it uses in the encryption process."*
3. *"The protocol gives **plaintext data, temporal keys, AAD, and nonce** as the input to the
   encryption process that uses the **AES and CCMP** algorithms."*
4. *"A **PN is included in the CCMP header** to protect against **replay attacks**."*
5. *"The results from the AES and the CCMP algorithms produce **encrypted text and an encrypted MIC
   value**."*
6. *"The assembled **MAC header, CCMP header, encrypted data, and encrypted MIC** forms the
   **WPA2 MAC frame**."*

Figure 13.1 _(Mod 13 p34)_ — *"Schematic showing the working of WPA2"*. Readable label tokens:
AES · MAC header · AAD · Nonce · CCMP header · Temporal key · CCMP · Encrypted data · Plaintext
data · Encrypted MIC · WPA2 MAC Frame. Caption text: *"Additional authentication data is taken
from the **MAC header** … The **packet number (PN)** attached in the CCMP header creates the
**nonce** used for the encryption process."*

```text
[ p34 Figure 13.1 — plaintext flow derived from the six numbered steps above ]

Plaintext data + Temporal key + AAD(from MAC header) + Nonce(PN || part of MAC header)
      -> AES + CCMP  ->  Encrypted data + Encrypted MIC
      frame = MAC header + CCMP header + Encrypted data + Encrypted MIC
```

Predecessor → [[13-LO02b-WPA-Encryption]] · successor → [[13-LO02d-WPA3-Encryption]] ·
side-by-side → [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] · weaknesses →
[[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] · RADIUS/EAP server side →
[[13-LO03c-Centralized-Authentication-Server]] · 802.11i →
[[13-LO01c-Wireless-Network-Standards]]







