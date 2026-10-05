---
type: note
module: "13"
lo: "04"
tags: [bestpractice, mod/13]
topic: "Disable SSID broadcasting"
exam_weight: unknown
status: done
unresolved:
  - "p55 the disabled state shows the literal string 'unnamed network' in the source. Quoted as printed; the wording of any client UI is not verified against the PDF artwork."
  - "p55 the LINKSYS Wireless-G router walkthrough screenshot text is only partly legible ('Wireless-G two', 'Cancel Changes', 'Security Save Settings', 'SVRT54Gv8'). Not transcribed as instructions."
  - "p55 the source calls the AP 'WLAN' in one sentence and 'wireless router' in the two state descriptions. Both used as printed; no distinction is drawn in the courseware."
---

[[MOC-Module-13]]

# Disable SSID Broadcasting (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers p55 — security measure **3** on the LO#04 list.

## The rule _(Mod 13 p55)_

> **"Network defenders should always disable SSID broadcasting on their devices."**

*"A wireless network SSID can either be **broadcast or hidden**. By broadcasting the SSID, **anyone
can find and access it**. If the SSID is hidden, the user has to **know the exact SSID** in order to
connect to the wireless network."*

## Broadcast vs disabled _(Mod 13 p55)_

| | **SSID Broadcast in the Enabled State** | **SSID Broadcast in the Disabled State** |
|---|---|---|
| What the AP announces | *"the wireless router will broadcast its **presence and name**"* | *"the wireless router will broadcast its **presence**, but will **not display the name**"* |
| What a scan shows | *"the **name and presence** of the network will be identified"* | *"Instead **'unnamed network'** will be displayed as a connection present within a user's range"* |
| Password | *"It may be **locked with a password**, but **anyone will be able to see it**"* | *"The user can connect to the wireless network **after naming it** and providing it with the **correct authentication credentials**"* |

## What disabling actually buys you _(Mod 13 p55)_

*"If the SSID is broadcast, the AP will announce its presence and name, **allowing everyone to
attempt to authenticate and connect** to the wireless network."*

With the broadcast disabled — *"an AP will **only broadcast its presence, but not its name**"*:

- *"This **discourages unauthorized association requests** to the network"*
- *"and **permits connections from legitimate users** to the wireless network **who have the correct
  SSID**"*

**Not stated in the source:** that disabling SSID broadcast is a security control on its own, or that
it prevents authentication. It only removes the name from the announcement; the source frames it as
*"discouraging"* unauthorized association requests.

## Related

- The measure list also carries **change the default SSID** and **do not use the SSID, company name or network name in passphrases** — [[13-LO04l-Additional-Guidelines-and-Module-Summary]]
- The router-side settings are in [[13-LO04k-Router-Administrative-Security]]





