---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "WPA3 encryption"
exam_weight: unknown
status: done
unresolved:
  - "p35 states WPA3 'provides cryptographic consistency by using encryption algorithms such as AES, TKIP, etc., to defend against network attacks.' TKIP is named as a WPA3 encryption algorithm, but TKIP is defined on p31 as the WPA cipher and p37's Table 13.2 lists no TKIP under WPA3. Quoted as printed; not reconciled."
  - "p35 says WPA3 'disallows outdated legacy protocols' without naming any."
  - "p35 lists WPA3-Enterprise's signature primitive as 'the elliptic curve digital signature algorithm (ECDSA- 384) for exchanging keys' in the callout, while p36 describes it as 'elliptic curve digital signature algorithm (ECDSA) using a 384-bit elliptic curve' and pairs it with the ECDH exchange. The two wordings are kept as printed."
  - "p36 renders list bullets as the letter o (e.g. 'weak or o popular phrases'); normalised to the plain reading in prose - the glyph carries no meaning."
---

[[MOC-Module-13]]

# WPA3 Encryption (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp35–36.

## Definition _(Mod 13 p35)_

- *"Wi-Fi protected access 3 (WPA3) was **announced by Wi-Fi Alliance on January 2018** as the
  **advanced implementation of WPA2** and providing trailblazing protocols."*
- Cipher: *"uses **AES-Galois/counter mode protocol (GCMP) 256-bit** encryption algorithm"*.
- *"The WPA3 protocol provides **two variants** similar to WPA2, i.e., **WPA3-Personal** mode and
  **WPA3-Enterprise** mode."*
- *"provides cutting-edge features to simplify Wi-Fi security and provides capabilities necessary for
  supporting different network deployments ranging from **corporate networks to home networks**."*
- *"It provides **cryptographic consistency** by using encryption algorithms such as **AES, TKIP,
  etc.**, to defend against network attacks."*
- *"It provides **network resilience through protected management frames (PMF)** that delivers a
  high-level of **protection against eavesdropping and forging attacks**. It **disallows outdated
  legacy protocols**."*

## WPA3-Personal _(Mod 13 pp35–36)_

- *"mainly used to deliver **password-based authentication**."*
- Key establishment: *"the modern key establishment protocol, termed as **simultaneous
  authentication of equals (SAE)** which is also known as **dragonfly key exchange** that
  **replaces the concept of PSK** used in the WPA2-Personal mode."*
- *"It is **resistant to offline dictionary attacks** and **key recovery attacks**."*

| Feature | Courseware description |
|---------|------------------------|
| **Resistant to offline dictionary attacks** | *"It **prevents passive password attacks** such as brute-force passwords."* |
| **Resistant to key recovery** | *"Even when a password is determined, it is **highly impossible to capture and determine the session keys** maintaining the **forward secrecy** of network traffic."* |
| **Natural password choice** | *"It allows users to choose passwords such as **weak or popular phrases**, which are easier to remember."* |
| **Easy accessibility** | *"It can provide robust protection **without changing the previous methods** used by the users for connecting to a network."* |

## WPA3-Enterprise _(Mod 13 pp35–36)_

*"This mode is **based on WPA2**. It offers better security across the network and protects
sensitive data by using many cryptographic concepts and tools."* Four protocols _(Mod 13 p36)_:

| Security concept | Protocol used by WPA3-Enterprise |
|------------------|----------------------------------|
| **Authenticated encryption** | *"maintaining the **authenticity and confidentiality** of the data … **256-bit Galois/counter mode protocol (GCMP-256)**."* |
| **Key derivation and validation** | *"generating a **cryptographic key from a password or master key** … a **384-bit hashed message authentication mode (HMAC)** using the **secure hash algorithm**, termed as **HMAC-SHA-384**."* |
| **Key establishment and verification** | *"exchanging cryptographic keys among two parties … the **elliptic curve Diffie-Hellman (ECDH) exchange** and **elliptic curve digital signature algorithm (ECDSA)** using a **384-bit elliptic curve**."* |
| **Frame protection and robust administration** | *"**256-bit broadcast/multicast integrity protocol Galois message authentication code (BIP-GMAC-256)**."* |

Callout variant of the same list _(Mod 13 p35)_ — *"It protects sensitive data by using many
cryptographic algorithms. It provides **authenticated encryption using GCMP-256**. It uses the
**hashed message authentication mode using the secure hash algorithm (HMAC-SHA-384)** to generate
the cryptographic keys. It uses the **elliptic curve digital signature algorithm (ECDSA-384)** for
exchanging keys."*

Predecessor → [[13-LO02c-WPA2-Encryption]] · side-by-side →
[[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]] · weaknesses of the older schemes →
[[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] · passwordless provisioning alternative →
[[13-LO02g-Wi-Fi-Easy-Connect-DPP]]







