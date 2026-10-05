---
type: note
module: "13"
lo: "02"
tags: [crypto, protocol, mod/13]
topic: "Wi-Fi Easy Connect / DPP"
exam_weight: unknown
status: done
unresolved:
  - "p42 callout OCR renders several common words with accent artefacts: 'pubEc key cryptog*y', 'transÃ‰r', 'conWatbn', 'Secure commu notion', 'Resistant to o figure'. The clean form of each phrase is present in the p42 body text, so the callout was normalised from the body wording - no new fact was added."
  - "p42-43 the OCR prints the noun as both 'enrolees' and 'Enrollee' and the caption for Figure 13.3 uses 'Confwrator'. Kept as 'enrolee' / 'configurator'; the figure caption garble is not quoted."
  - "p43 Figure 13.3's numbered labels are readable and are transcribed; the label for step 2 is split across the page in the OCR ('2. Scan the Client device to enroll device') and is reproduced in that wording."
---

[[MOC-Module-13]]

# Wi-Fi Easy Connect / DPP (§13.02)

> **LO#02: Understand the encryption mechanisms used in wireless networks** _(Mod 13 p28)_
> Covers pp42–43.

## Overview _(Mod 13 p42)_

*"Wi-Fi Easy Connect (Device Provisioning Protocol (DPP)), **simplifies and enhances the security of
Wi-Fi device provisioning and network setup while minimizing security risks**. It incorporates the
**highest security standards** as well. It brings **consistency, flexibility, simplicity** to Wi-Fi
network management."*

## DPP security features _(Mod 13 pp42–43)_

| # | Feature | Courseware description |
|---|---------|------------------------|
| 1 | **Secure communications** | *"establishes secure communications between the **device being provisioned** and the **provisioning device (such as a smartphone or tablet)** with **public key cryptography**."* |
| 2 | **PKI** | *"uses **public key infrastructure (PKI)** to manage and distribute public key and **ensures the authenticity of the public keys** used for secure communication."* |
| 3 | **QR code transfer** | *"utilizes **QR codes** to transfer network information such as **network SSID, network credentials, and cryptographic keys** between the provisioning device and the new device. This **prevents eavesdropping compared to manual entry**."* |
| 4 | **Passwordless configuration** | *"enables the setup of Wi-Fi connections **without pre-shared keys (PSKs) or passwords**. This **reduces the risk of password-related attacks**."* |
| 5 | **Mutual authentication** | *"both the **provisioning device** and the **device being added to the network** verify **each other's authenticity** and **prevent rogue devices from joining the network**."* |
| 6 | **Forward secrecy** | *"generates **unique keys for each provisioning session**. Hence, if a **long-term key is compromised**, it **cannot be used to decrypt past or future provisioning sessions**."* |
| 7 | **Tamper-resistant storage** _(Mod 13 p43)_ | *"Some DPP implementations leverage **tamper-resistant hardware, such as hardware security modules (HSMs)**, to store and protect **sensitive cryptographic keys**."* |
| 8 | **Network segment creation** _(Mod 13 p43)_ | *"allows network segment creation, so **IoT devices can be provisioned securely and isolated from more sensitive network segments**."* |

## Working of Wi-Fi Easy Connect _(Mod 13 p43)_

- *"one device which is **rich in user interface (such as a smart phone)** is chosen as the
  **central point of configuration**."*
- *"This device must have the capability to **scan a QR code, or NFC tag, or download device
  information from the cloud**."*
- Roles: *"This selected device is called a **configurator** and other devices are called
  **enrolees**."*
- *"A **secure connection is established between the configurator and enrolee** by scanning the
  **NFC tag or QR code** or **downloading data associated with the device from the cloud**. This
  **initiates the protocol, triggering the automated provisioning of the necessary credentials** for
  the enrolee to **gain network access**."*

Figure 13.3 _(Mod 13 p43)_ — *"Connected Devices on the Network"*. Readable numbered steps:

1. Scan the QR code to establish a network
2. Scan the Client device to enroll device
3. Connected devices on network

Entities in the figure: **Configurator**, **Enrollee**, **access point**, **clients**.

Password-key contrast → [[13-LO02d-WPA3-Encryption]] (SAE / dragonfly replaces PSK) ·
rogue-device defence → [[13-LO04g-Rogue-Access-Point-Detection]] ·
module map → [[13-LO01e-Components-of-a-Wireless-Network]]







