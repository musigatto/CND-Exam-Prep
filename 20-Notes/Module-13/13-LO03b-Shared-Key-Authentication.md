---
type: note
module: "13"
lo: "03"
tags: [protocol, crypto, mod/13]
topic: "Shared Key Authentication"
exam_weight: unknown
status: done
unresolved:
  - "p46 process figure step 5 reads 'Cient conn«ts to network'. Garbled figure label; the same figure reads 'Client encrypts challenge text and sends it back to AP' correctly. Quoted as printed, not corrected."
  - "p46 process figure also carries 'Client attempting 5 to connect', 'Switch or Cable', 'Modem' and 'Internet'. The stray '5' and the connectivity labels appear to be page furniture/logo bleed; reproduced without interpretation."
  - "p46 gives a Disadvantage for shared key authentication but no corresponding Advantage, unlike p45 which gives both an Advantage and a Disadvantage for open system authentication. The omission is in the source."
  - "p46 step 3 gives the challenge-text key size as '64-bit or 128-bit'. LO#03 does not define which WEP key lengths these correspond to, and does not reconcile them with the WEP key sizes listed in LO#02. Quoted as printed."
---

[[MOC-Module-13]]

# Shared Key Authentication (§13.03)

> **LO#03: Understand the authentication methods used in wireless networks** _(Mod 13 p44)_
> Covers p46.

## Courseware callout _(Mod 13 p46)_

> **Shared Key Authentication** — *"The station and the AP use the **same WEP key** to provide
> authentication. This indicates that this key should be **enabled and configured manually** on both
> the AP and the client."*

## Key distribution — out of band _(Mod 13 p46)_

- *"each wireless station receives a **shared secret key over a secure channel** that is **distinct
  from the 802.11 wireless network communication channels**."*
- The key is therefore **never negotiated over the 802.11 link** — it must be **configured manually**
  on both ends.

## Establishment of the connection — the steps _(Mod 13 p46)_

*"The following steps illustrate the establishment of a network connection using the shared key
authentication process:"*

1. *"The station sends an **authentication frame** to the AP."*
2. *"The AP sends the **challenge text** to the station."*
3. *"The station **encrypts the challenge text** by making use of its configured **64-bit or 128-bit
   key** and sends the encrypted text to the AP."*
4. *"The AP uses its configured WEP key to **decrypt** the encrypted text. It **compares the decrypted
   text with the original challenge text**."*
5. *"If the decrypted text **matches** the original challenge text, **the AP authenticates the
   station**."*
6. *"The station **connects to the network**."*

## Rejection path _(Mod 13 p46)_

- *"The AP can **reject** the station if the decrypted text **does not match** the original challenge
  text."*
- Consequence: the station *"will be unable to communicate with **either the ethernet network or the
  802.11 network**."*

## Process figure — p46 labels (verbatim)

```text
[ p46 "Shared Key Authentication Process" — labels as captured, reading order ]

Authentication request sent to AP
AP Sends challenge text
Client encrypts challenge text and sends it back to AP
AP decrypts challenge text, and if correct, authenticates client
Cient conn«ts to network

figure furniture: Client attempting 5 to connect · Switch or Cable · Modem
                 Access point (AP) · Internet
```

## Disadvantage _(Mod 13 p46)_

- *"This mechanism is **not suitable for large networks**, as it requires **long-key strings
  configured on each device**, which is a **highly cumbersome task**."*

The courseware lists **no advantage** for this method.

## Open System vs Shared Key _(Mod 13 pp45–46)_

| | Open System _(p45)_ | Shared Key _(p46)_ |
|---|---|---|
| Verifies the peer? | **No** — *"null authentication algorithm"*, *"does not verify whether it is a user or a machine"* | Yes — AP authenticates the station on a successful decrypt |
| Exchange | **Authentication frame only**, identity sent in the clear | **Challenge text**, then challenge text **encrypted by the client** |
| Shared secret | none | **Same WEP key** on AP and client, delivered over a **secure channel distinct from the 802.11 channels** |
| Key size | not stated | **64-bit or 128-bit** |
| Authentication server | *"does not depend on a RADIUS server on the network"* | not stated |
| Gate for traffic | **WEP key matches the AP's WEP key** | **decrypted challenge text matches the original** |
| Fits | devices that *"do not support complex authentication algorithms"* | small deployments — *"not suitable for large networks"* |

WEP key background → [[13-LO02a-WEP-Encryption]] · other method →
[[13-LO03a-Open-System-Authentication]] · server-based alternative →
[[13-LO03c-Centralized-Authentication-Server]] · attack side →
[[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]]





