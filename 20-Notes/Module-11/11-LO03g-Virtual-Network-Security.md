---
type: note
module: "11"
lo: "03"
tags: [bestpractice, mod/11, flashcard/11]
topic: "Virtual Network Security"
exam_weight: unknown
status: done
unresolved:
  - "p59: the slide shows 10 bullets, the prose list has 12 — 'Ensure security on open standards' and 'Provide manageable security controls' appear only in the prose."
  - "'Use virtual switches in random places/locations to monitor the network' is reproduced verbatim; the courseware gives no rationale for the word 'random'."
  - "Section is a single page (p59) with no accompanying figures; no further detail exists in the slice."
---

[[MOC-Module-11]]
# Virtual Network Security (§11.03)

Twelve recommendations, verbatim from the courseware. _(Mod 11 p59)_

## Cryptography, identity, boundaries

| # | Recommendation | Ref |
|---|---|---|
| 1 | Use cryptographic controls like **SSL encryption** on the network traffic between the **hosts and the clients** | _(p59)_ |
| 2 | Use **segregation in networks** | _(p59)_ |
| 3 | Clearly define **security dependencies and trust boundaries** | _(p59)_ |
| 4 | Assure a **robust identity** | _(p59)_ |
| 5 | Ensure security on **open standards** | _(p59)_ |
| 6 | **Protect operational reference data** | _(p59)_ |
| 7 | Make systems **secure by default** | _(p59)_ |
| 8 | Provide **accountability and traceability** | _(p59)_ |
| 9 | Provide **manageable security controls** | _(p59)_ |

## Hardening the virtual switching layer

| # | Recommendation | Ref |
|---|---|---|
| 10 | Use **virtual switches in random locations** to monitor the network | _(p59)_ |
| 11 | To protect switches from **MAC spoofing** attacks, enable **MAC address filtering** | _(p59)_ |
| 12 | **Disconnect NICs** (network interface controllers) to prevent outsiders from connecting to the network easily | _(p59)_ |

## Cards

Front: List the four virtual-network recommendations that concern identity, standards, data and accountability.
?
Assure a robust identity · Ensure security on open standards · Protect operational reference data · Provide accountability and traceability. _(Mod 11 p59)_

Front: Which recommendation covers data in transit between hosts and clients?
?
Use cryptographic controls like SSL encryption on the network traffic between the hosts and the clients. _(Mod 11 p59)_

Front: How do the recommendations counter MAC spoofing?
?
Enable MAC address filtering on the switches. _(Mod 11 p59)_

Front: What physical-layer recommendation prevents unauthorized device connections?
?
Disconnect network interface controllers (NIC) to prevent outsiders from connecting to the network easily. _(Mod 11 p59)_

Front: Name the four network-architecture recommendations.
?
Use segregation in networks · clearly define security dependencies and trust boundaries · make systems secure by default · provide manageable security controls. _(Mod 11 p59)_
