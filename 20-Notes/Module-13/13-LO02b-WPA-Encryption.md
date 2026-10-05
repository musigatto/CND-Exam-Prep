---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "WPA encryption"
exam_weight: unknown
status: done
unresolved:
  - "p31 states 'WEP normally uses a 40-bit or 140-bit encryption key, whereas TKIP uses 128-bit keys for each packet.' The 140-bit WEP key is not stated anywhere else in the module; p29 gives WEP keys as 40/104/128/232-bit. Source contradiction, not reconciled - the p31 value is quoted as printed."
  - "p31 WPA diagram labels read 'Data to Transmit  MOW. WC Cipher' - MOW. and WC are garbled figure labels, not reconstructed."
  - "p32 step 1 states the hash/mixing function generates 'a 128-bit and a 104-bit key'. Two key sizes for one step is not explained anywhere in the module. Quoted as printed."
  - "p32 step 5 reads 'This cipher text may be XORed again by the client using the same keystream' - 'again' is the source's own wording, not an OCR artefact."
  - "p31 'Michael algorithm' feature says WPA 'identifies the algorithm that determines an 8-byte MIC with the help of the methods present in the wireless devices.' Awkward source wording; quoted verbatim, not rewritten."
  - "p31 'TKIP detects all of the identified weaknesses linked with WE-P' - WE-P is a typo in the courseware for WEP; left as printed inside the quotation."
---

[[MOC-Module-13]]

# WPA Encryption (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp31–32.

## Definition _(Mod 13 p31)_

- *"Wi-Fi Protected Access (WPA) is a security protocol defined by the **802.11i standard**."*
- *"a security standard for Wi-Fi connections. WPA provides **refined data encryption and user
  authentication** techniques."*
- *"WPA uses **TKIP** for data encryption, which **eliminates the weaknesses of WEP** by including
  **per-packet mixing functions, message integrity checks, extended IVs and re-keying
  mechanisms**."*
- *"WPA requires **802.1x authentication** and changes the **unicast and global encryption keys**."*
- Key behaviour: **unicast** — the key **changes for every packet**, coordinated between client and
  AP. **Global** — *"the APs **advertise the change in the key** to the connected wireless clients."*

## Crypto parameters _(Mod 13 p31)_

| Element | WPA / TKIP value |
|---------|-----------------|
| Stream cipher | **RC4** |
| Key | **128-bit** (per packet) |
| Integrity | **64-bit message integrity check (MIC)** |
| ICV | **32-bit**, computed for the MPDU |
| RC4 inputs | **temporal encryption key + transmit address + TKIP sequence counter (TSC)** |

Processing chain _(Mod 13 p31)_:
MSDU + MIC → combined with the **Michael** algorithm → fragmented → **MPDU** → **32-bit ICV**
computed for the MPDU → MPDU + ICV **bit-wise XORed with the keystream** → encrypted data → **IV
added** → MAC frame.

## WPA diagram — p31 labels (verbatim)

```text
[ p31 WPA encryption diagram — labels as captured, reading order ]

Data to Transmit  ->  MOW. WC  ->  Cipher
```

## What is TKIP? _(Mod 13 p31)_

*"TKIP is comprised of **three main elements** that increase encryption:"*

1. A **key integration function** for individual packets.
2. An **enhanced MIC function named Michael**.
3. An **improved IV** including the **sequencing guidelines**.

*"TKIP is a **short-term fix for WEP**, organized as a **simple software/firmware upgrade**. A number
of **design weaknesses have been incorporated** in order to sustain **reverse compliance** with the
large number of existing hardware in the field. TKIP detects all of the identified weaknesses linked
with WE-P."*

## Working of WPA — the steps _(Mod 13 p32)_

1. *"The **IV or the temporal key sequence**, the **transmit address or the MAC destination
   address**, and the **temporal key** are combined with a **hash function or a mixing function** to
   generate a 128-bit and a 104-bit key."*
2. *"This key is then combined with **RC4** to produce the **keystream** which should be **of the
   same length as the original message**."*
3. *"The **MAC destination and source addresses** and the **MIC keys** are combined with a **hash
   function** in order to produce the **MIC value**."*
4. *"The **MIC value is fragmented** to produce the **MAC protocol data unit (MPDU)**. The
   **checksum** is later attached to the MPDU."*
5. *"The MPDU along with the checksum is **XORed with the keystream** to produce the **cipher
   text**."*
6. *"This cipher text may be XORed again by the client using the same keystream in order to produce
   the original message."*

## Types of WPA _(Mod 13 p32)_

| Type | Courseware description |
|------|------------------------|
| **1. WPA-Personal** | *"makes use of **setup passwords** and protects **unauthorized network access**."* |
| **2. WPA-Enterprise** | *"**confirms the network user through a server**."* |

## Features of WPA _(Mod 13 p32)_

- **WPA authentication** — *"WPA requires **802.1x authentication**. It uses a **pre-shared key
  (PSK)** for the environment **without** the remote authentication dial-in user service (RADIUS)
  infrastructure and uses the **extensible authentication protocol (EAP) and RADIUS** for
  environments **with a RADIUS infrastructure**."*
- **WPA key management** — *"It is necessary to change both the **unicast and global** encryption
  keys while using WPA. **TKIP keeps changing the key for every frame** when using an unicast key.
  In the case of a global key, WPA enforces the wireless AP to **report the changed key to the
  connected wireless clients**."*
- **Temporal key management** — *"In WPA, **encryption with TKIP is required**. TKIP changes the
  WEP using a new encryption algorithm that is **stronger than the standard WEP algorithm**."*
- **Michael algorithm** — *"802.11 and WEP data uses a **32-bit integrity check value (ICV)** to
  check the message integrity. In WPA, the Michael technique **identifies the algorithm that
  determines an 8-byte MIC** with the help of the methods present in the wireless devices."*
- **AES support** — *"WPA supports **AES as a substitute for WEP encryption**. This support is
  **optional** and depends on the **vendor driver support**."*
- **Mixed WEP and WPA clients** — *"A wireless AP maintains **both WEP and WPA simultaneously** in
  order to help the **gradual transition** of WEP-based wireless networks to WPA."*

Predecessor → [[13-LO02a-WEP-Encryption]] · successor → [[13-LO02c-WPA2-Encryption]] ·
side-by-side → [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] · weaknesses →
[[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] · 802.1X/RADIUS server side →
[[13-LO03c-Centralized-Authentication-Server]] · 802.11i →
[[13-LO01c-Wireless-Network-Standards]]







