---
type: note
module: "13"
lo: "03"
tags: [protocol, crypto, mod/13]
topic: "Open System Authentication"
exam_weight: unknown
status: done
unresolved:
  - "p45 callout reads 'Any wireless device can be authenticated with the APS'. 'APS' is the OCR form; the page calls the access point 'AP' everywhere else. Quoted as printed, not corrected."
  - "p45 process figure step 4 reads '?ysEm' between 'Open System Authentication Request' and 'Authentication Response'. Garbled figure label, not reconstructed."
  - "p45 process figure also carries the labels 'Switch or Cable', 'Modem' and 'Internet', which are not part of the wireless authentication flow. Reproduced as page furniture, not interpreted."
  - "p45 figure carries 'Security parameters' in the probe-response step and 'Security Parameters' in the association-request step, while the same page calls open system 'cleartext transmission' and says the device can gain access using only the SSID. The courseware does not reconcile the two. Both forms quoted as printed."
---

[[MOC-Module-13]]

# Open System Authentication (§13.03)

> **LO#03: Understand the authentication methods used in wireless networks** _(Mod 13 p44)_
> Covers pp44–45.

## Section objective _(Mod 13 p44)_

*"The objective of this section is to explain the various authentication methods such as the
**open system authentication**, **shared key authentication**, etc., used in wireless networks."*

Methods covered by LO#03 → **open system** (this note) · **shared key**
[[13-LO03b-Shared-Key-Authentication]] · **centralized authentication server**
[[13-LO03c-Centralized-Authentication-Server]]

## Courseware callout _(Mod 13 p45)_

> **Open System Authentication** — *"Any wireless device can be authenticated with the APS,
> allowing the device to transmit data only when its WEP key matches with the WEP key of the AP."*

## What it actually is _(Mod 13 p45)_

- *"Open system authentication is a **null authentication algorithm** that **does not verify whether
  it is a user or a machine** requesting network access."*
- *"It uses **cleartext transmission** to allow the device to associate with an AP."*
- *"In the absence of encryption, the device can use the **SSID** of an available WLAN to gain access
  to a wireless network."*
- *"This authentication mechanism **does not depend on a RADIUS server** on the network."*

## Authentication success ≠  transmission _(Mod 13 p45)_

- *"The **enabled WEP key** on the AP acts as an **access control** to enter the network."*
- **The trap:** *"Any user entering the **wrong WEP key cannot transmit messages** via the AP **even
  if the authentication is successful**."*
- *"The device can only transmit messages when its **WEP key matches** with the WEP key of the AP."*

Two independent gates — the **authentication frame exchange** (always "successful") and the **WEP key
match** (the real access control).

## Process figure — p45 labels (verbatim)

```text
[ p45 "Open System Authentication Process" — labels as captured, reading order ]

Probe Request
Probe Response (Security parameters)
Open System Authentication Request ?ysEm
Authentication Response
Association Request (Security Parameters)
Associatign Response to connect

figure furniture: Switch or Cable · Modem · Access point (AP) · Internet
```

## Body narration of the exchange _(Mod 13 p45)_

1. *"any wireless client that wishes to access a Wi-Fi network sends a **request to the wireless AP
   for authentication**."*
2. *"the station sends an **authentication management frame containing the identity of the sending
   station** for authenticating and connecting with the other wireless stations."*
3. *"The AP then returns an **authentication frame** to confirm access to the requested station and
   **completes the authentication process**."*

The body narrates only the authentication-frame exchange; the figure additionally shows the probe
and association steps.

## Advantage / Disadvantage _(Mod 13 p45)_

| | Courseware |
|---|---|
| **Advantage** | *"This mechanism can be used with wireless devices that **do not support complex authentication algorithms**."* |
| **Disadvantage** | *"There is **no way to check whether someone is a genuine client or an attacker**. Anyone who **knows the SSID** can easily access the wireless network."* |

Contrast with → [[13-LO03b-Shared-Key-Authentication]] · server-based →
[[13-LO03c-Centralized-Authentication-Server]] · the WEP key itself →
[[13-LO02a-WEP-Encryption]] · EAP/RADIUS instead of open system →
[[13-LO02b-WPA-Encryption]] · attack side →
[[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]]






