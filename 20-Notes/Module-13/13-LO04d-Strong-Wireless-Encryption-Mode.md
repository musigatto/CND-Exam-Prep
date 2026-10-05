---
type: note
module: "13"
lo: "04"
tags: [bestpractice, crypto, mod/13]
topic: "Strong wireless encryption mode"
exam_weight: unknown
status: done
unresolved:
  - "p56 the page carries two 'order of preference' lists of seven entries each and they disagree: the encryption-mode list ranks WEP 7th, the Wi-Fi security method list ranks WEP 6th and adds 'Open Network (no security at all)' as 7th. Both reproduced as printed; not reconciled."
  - "p56 the second list is captioned 'Order of preference for choosing a Wi-Fi security method' and the first 'Order of preference for choosing an encryption mode'. The source gives no statement that the two lists are the same ranking expressed two ways."
  - "p56 the LINKSYS Wireless-G walkthrough screenshot shows a radio-button list whose OCR order is: WPA personal, WPA, WPA2, WPA2 Enterprise RADIUS, WEP, A1 Disabled, Personal WPA Enterprise, NPA2 Personal, WPA2 Enterprise RADIUS, WEP. The OCR is not reliable enough to reconstruct the menu. Not transcribed as instructions."
  - "p56 'WPA2 Enterprise with RADIUS' (list 1) and 'WPA2 Enterprise RADIUS' (screenshot OCR) are the same phrase in different word order. Only the list wording is used."
  - "Cross-note, cited for a contradiction only: the p49 LO#04 measure list presents 'Implement WEP 128 enhanced encryption protocol combination of 104-bit & 24-bit key' as an activity that defends wireless security, while p56 ranks WEP last. Recorded rather than reconciled."
---

[[MOC-Module-13]]

# Selecting a Strong Wireless Encryption Mode (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers p56 — security measure **4** on the LO#04 list.

> **"A strong wireless encryption mode should be used for keeping the wireless network safe from various types of attacks."** _(Mod 13 p56)_

## Order of preference for choosing an encryption mode _(Mod 13 p56)_

| Rank | Encryption mode |
|------|-----------------|
| 1 | **WPA3** |
| 2 | **WPA2 Enterprise with RADIUS** |
| 3 | **WPA2 Enterprise** |
| 4 | **WPA2 PSK** |
| 5 | **WPA Enterprise** |
| 6 | **WPA** |
| 7 | **WEP** |

## Order of preference for choosing a Wi-Fi security method _(Mod 13 p56)_

A **second, different** seven-entry list on the same page:

| Rank | Wi-Fi security method |
|------|----------------------|
| 1 | **WPA3** |
| 2 | **WPA2 + AES** |
| 3 | **WPA + AES** |
| 4 | **WPA + TKIP/AES** |
| 5 | **WPA + TKIP** |
| 6 | **WEP** |
| 7 | **Open Network (no security at all)** |

**Traps visible only by comparing the two lists:**

- **WEP sits 7th in one list and 6th in the other** — the open network is the only entry present in one list and absent from the other.
- The first list ranks **Enterprise modes above PSK**; the second list does not distinguish PSK from Enterprise at all — it ranks **ciphers** (AES above TKIP).
- **WPA3 is #1 in both.** Nothing in the source ranks WPA3 against the open network explicitly, but the open network is last in the list that contains it.

## Related

- Mode-by-mode differences: [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]]
- Encryption mechanisms in detail: [[13-LO02a-WEP-Encryption]] · [[13-LO02b-WPA-Encryption]] · [[13-LO02c-WPA2-Encryption]] · [[13-LO02d-WPA3-Encryption]]
- RADIUS is the server behind **WPA2 Enterprise with RADIUS** — [[13-LO03c-Centralized-Authentication-Server]]
- Weaknesses that make mode choice matter: [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]]





