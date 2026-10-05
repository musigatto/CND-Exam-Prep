---
type: note
module: "13"
lo: "04"
tags: [bestpractice, mod/13]
topic: "MAC address filtering"
exam_weight: unknown
status: done
unresolved:
  - "p57 the closed/open wording is counterintuitive and contradicts the everyday reading of the words. 'In a closed MAC filter, only the listed addresses are permitted to access the network' and 'In an open MAC filter, the addresses listed in the filter are prevented from accessing the network'. Both reproduced exactly as printed; NOT swapped to the conventional sense."
  - "p57 the source claims MAC-based client authentication 'is more secure compared to an open and shared authentication method'. That is the courseware's claim as printed; no supporting argument is given."
  - "p57 the bypass is named only as 'a MAC spoofing attack'. No technique, tool or countermeasure is given anywhere in the section."
  - "p57 the LINKSYS Wireless-G / CISCO walkthrough screenshots are largely illegible in the OCR ('Wireless Wekss MAC Finer', 'MAC Pemi', 'Prevent PCs the Pernit onw PCs Ã¦d to access me'). The only reliably legible UI values are the setting name and 'Disable'. Not transcribed as instructions."
  - "p57 'This authentication method minimizes the number of unauthorized users accessing the network.' is the closing sentence of the section and is not tied to any specific filter option."
---

[[MOC-Module-13]]

# MAC Address Filtering (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers p57 — security measure **5** on the LO#04 list.

## What it does _(Mod 13 p57)_

> **"MAC address filtering enables the administrator to block all unauthorized devices from accessing the network and only allow known MAC addresses to connect to the network."**

- *"**Most wireless routers have MAC address filtering capabilities.** This filtering feature permits
  access to **known MAC addresses only** and restricts all others."*
- Mechanism: *"If MAC address filtering is enabled, the **AP or the router stores and maintains a
  list of MAC addresses** for the wireless clients. When a client tries to connect to the network,
  the AP **compares the list of stored MAC addresses with the client's MAC address** and allows
  network connection **only if the MAC address is found in the stored list**."*
- *"In this technique, the **client authentication is based on MAC addresses**."*
- Closing claim: *"This authentication method **minimizes the number of unauthorized users** accessing
  the network."*

## Open vs closed filter _(Mod 13 p57)_

> **Exam trap — the printed definitions are inverted relative to the everyday meaning of the words.
> Reproduce them as printed.**

| | **Closed MAC filter** _(as printed)_ | **Open MAC filter** _(as printed)_ |
|---|---|---|
| Effect | *"only the **listed addresses are permitted** to access the network"* | *"the addresses **listed in the filter are prevented** from accessing the network"* |
| Courseware verdict | *"This option is a **more secure** way of accessing the network."* | *"This is **not always practical in a large network**."* |

## Limitation — stated plainly _(Mod 13 p57)_

> **"However, an attacker can bypass this filtering technique with the help of a MAC spoofing attack."**

The source gives no further detail on the bypass and no compensating control.

## Related

- The courseware's own comparison: MAC filtering is *"more secure compared to an **open** and
  **shared** authentication method"* — [[13-LO03a-Open-System-Authentication]] · [[13-LO03b-Shared-Key-Authentication]]
- MAC address monitoring is also listed as a rogue-AP detection technique — [[13-LO04g-Rogue-Access-Point-Detection]]
- Checking whether MAC filtering is on is item 9 of the assessment checklist — [[13-LO04i-Wireless-Security-Assessment-Tools]]





