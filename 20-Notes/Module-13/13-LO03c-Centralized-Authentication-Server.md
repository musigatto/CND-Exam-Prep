---
type: note
module: "13"
lo: "03"
tags: [protocol, crypto, mod/13]
topic: "Wi-Fi authentication with a centralized authentication server"
exam_weight: unknown
status: done
unresolved:
  - "p47 renders the standard as '802.1x' with a lowercase x. Reproduced as printed; not changed to any other rendering."
  - "p47 figure step reads 'AP sends an EAP-request to determine the EAP' - the sentence is cut off and EAP is never expanded or defined anywhere in LO#03. Not reconstructed."
  - "p47 figure step 'The RADIUS server sends a request to the wireless client the AP.' has words missing and reordered. Quoted as printed."
  - "p47 figure step 'The AP sends a multicast/global authentication key encrypted with a per-station unicast session' ends mid-phrase, with no word after 'session'. Quoted as printed; the phrase is not completed."
  - "p47 figure step 'The RADIUS server sends an encrypted authentication key to the AP if the credentials' is cut off mid-clause and interleaved with 'authentication mechanism to be \"d'. Marked as truncated in the verbatim block; not stitched back together."
  - "p47 figure names the 'uncontrolled port' for forwarding the identity to RADIUS but LO#03 (pp44-47) gives no port number anywhere. No port number supplied."
---

[[MOC-Module-13]]

# Wi-Fi Authentication Process Using a Centralized Authentication Server (§13.03)

> **LO#03: Understand the authentication methods used in wireless networks** _(Mod 13 p44)_
> Covers p47.

## Courseware statement _(Mod 13 p47)_

- *"The **802.1x** standard provides **centralized authentication**."*
- *"For 802.1x authentication to work on a wireless network, **the AP must be able to securely
  identify the traffic from a specific wireless client**."*
- *"a centralized authentication server, namely **RADIUS**, sends the **authentication keys** to both
  the AP and the clients that want to authenticate with the AP."*
- *"This key enables the AP to **identify a particular wireless client**."*

Key management is therefore **not** the AP's alone: RADIUS issues the keys to **both** ends.

## Actors named on p47

| Actor | What the courseware says it does |
|---|---|
| **Client** | *"Client requests connection"*; *"responds to the RADIUS server with its credentials **via the AP**"* |
| **Access point (AP)** | sends an **EAP-request**; *"The identity is forwarded to the RADIUS server **using the uncontrolled port**"*; *"sends a **multicast/global** authentication key **encrypted with a per-station unicast** session"* [truncated] |
| **EAP** | *"[EAP] responds with identity details"*; the server *"sends a request to the wireless client"* [garbled] |
| **RADIUS server** | *"sends an encrypted authentication key to the AP if the credentials …"* [truncated]; *"sends the authentication keys to both the AP and the clients"* |

## Process figure — p47 labels (verbatim)

```text
[ p47 "Wi-Fi Authentication Process Using a Centralized Authentication Server"
  labels as captured;  [...]  marks text the source / OCR drops ]

Client requests connection
AP sends an EAP-request to determine the EAP [truncated]
[?] responds with identity details
The wireless client responds to the RADIUS server with its credentials via the AP
The AP sends a multicast/global authentication key encrypted with a per-station
    unicast session [truncated]
The identity is forwarded to the RADIUS server using the uncontrolled port
The RADIUS server sends a request to the wireless client [...] the AP.
    authentication mechanism to be "d [truncated / interleaved]
The RADIUS server sends an encrypted authentication key to the AP if the
    credentials [truncated]

figure furniture: Access Point (AP) · RADIUS Server · Client
```

## Three gates, three methods _(Mod 13 pp45–47)_

| | Open System _(p45)_ | Shared Key _(p46)_ | Centralized server _(p47)_ |
|---|---|---|---|
| Peer verified by | nobody — *"null authentication algorithm"* | the **AP**, on a challenge-response | the **RADIUS server**, via the AP |
| Shared secret | none | **same WEP key** on AP and client, set up over a **separate secure channel** | **authentication keys issued by RADIUS** to the AP *and* the clients |
| Traffic | cleartext | challenge text encrypted with a **64-bit or 128-bit** key | the AP must *"securely identify the traffic from a specific wireless client"* |
| Server needed | *"does not depend on a RADIUS server"* | not stated | **802.1x + RADIUS are the mechanism** |

## What LO#03 does not state _(Mod 13 pp44–47)_

- **No port number** — the figure names only *"the **uncontrolled port**"*.
- **No EAP method** is named, and **EAP is never expanded or defined** in LO#03.
- No key lifetime, RADIUS attribute list, message-authenticator or accounting detail.
- The p47 figure is the **only** description of the process; the body is four sentences.

EAP/RADIUS in the WPA modes → [[13-LO02b-WPA-Encryption]] ·
[[13-LO02c-WPA2-Encryption]] · no-server alternative →
[[13-LO03a-Open-System-Authentication]] · out-of-band shared secret →
[[13-LO03b-Shared-Key-Authentication]] · 802.11i →
[[13-LO01c-Wireless-Network-Standards]]





