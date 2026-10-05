---
type: note
module: "13"
lo: "04"
tags: [bestpractice, policy, mod/13]
topic: "Additional guidelines and module summary"
exam_weight: unknown
status: done
unresolved:
  - "p77 the Module Summary CONTRADICTS ITSELF on what an AP connects through. Its first bullet says 'A wireless network uses the IEEE standard of 802.11', and its next bullet says an AP connects devices 'by using the wireless standards such as Bluetooth, Wi-Fi, etc.' Bluetooth is placed alongside Wi-Fi as a wireless-network standard on the same page. Recorded, not reconciled."
  - "p77 the Module Summary names only WPA as the encryption method ('WPA is a data encryption method used for WLANs based on the 802.11 standards'). WPA2, WPA3 and WEP are not mentioned, although p56 ranks WPA3 first and WEP last of seven modes. Not reconciled."
  - "p77 the Module Summary's six key-concept bullets cover the IEEE 802.11 standard, the AP, WPA, open system authentication, traffic analysis and wireless/wired scanning. None of the LO#04 measures - AP and antenna placement, SSID broadcast, MAC filtering, rogue AP location, RF interference, WIDS/WIPS, router hardening - appears in the summary list. Recorded as coverage, not as a contradiction."
  - "p75 the monitoring guideline calls the product 'wireless intruder detection-prevention system (WIDPS) sensors'. p72 uses 'prevention system (WIPS)' in its heading and 'protection systems (WIPS)' in its body, and pp60/63 define WIDS as wireless access points. Four forms of the name appear in the module. Not harmonised."
  - "p75 the guideline list says 'Place a firewall or packet filter in between the AP and the corporate intranet'. The module contains no other statement on AP-to-intranet segmentation."
  - "p76 the sentence reads 'Security of the link THOUGH which information is passed' - 'though' is the printed word, kept as printed."
  - "p76 'the laptops that are being illegitimately used as APS' prints APS in capitals, where the rest of the module uses APs. Quoted as printed."
  - "p75 the SSID guidance 'The SSID value should be changed such that only the user understands it' is a third SSID statement in the module alongside 'Change the default SSID' and 'Broadcasting of SSIDs should be avoided'. All three are consistent and are kept separate because the source separates them."
  - "pp75-76 the guideline list and the body list overlap but are not identical: 'Implement a different technique for encrypting traffic such IPSec over the wireless network', 'Disable the network when not required', 'Keep the drivers on all wireless equipment updated', 'Place the wireless APs in a secured location' and 'Use a centralized server for authentication' appear only on the slide; 'Everything should be password protected', 'log out of the router's web interface' and 'The wireless access point should be password protected' appear only in the body."
---

[[MOC-Module-13]]

# Additional Wireless Network Security Guidelines and Module Summary (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp75–77 (p77 = Module Summary).

## Additional guidelines — the slide list _(Mod 13 p75)_

1. **Do not use the SSID, company name, network name, or any easy to guess string in the passphrases**
2. **Place a firewall or packet filter** in between the AP and the corporate intranet
3. **Change the default SSID**
4. **Regularly check the wireless devices** for configuration or setup problems
5. **Implement a different technique for encrypting traffic** such **IPSec** over the wireless network
6. **Regularly change the passphrases**
7. **Disable the network when not required**
8. **Place the wireless APs in a secured location**
9. **Keep the drivers** on all wireless equipment updated
10. **Use a centralized server for authentication**

## Additional guidelines — the body list _(Mod 13 pp75–76)_

*"The following list contains the security recommendations and guidelines for additional wireless
network security:"*

| # | Guideline | Page |
|---|-----------|------|
| 1 | *"The user should **log out of the router's web interface** when it is not in use."* | p75 |
| 2 | *"**Everything should be password protected** in order to avoid unauthorized access of the content in the system."* | p75 |
| 3 | *"The **wireless access point should be password protected**."* | p75 |
| 4 | *"The **SSID value should be changed such that only the user understands it**."* | p75 |
| 5 | *"The APs should be **kept in the middle of the building** in order to **avoid wardriving**."* | p75 |
| 6 | *"**Broadcasting of SSIDs should be avoided** as this can make it easy for an intruder to enter the network."* | p75 |
| 7 | *"The **physical location of the WLAN threat** should be identified."* | p75 |
| 8 | *"Information about the **source and destination IP addresses, ports, MAC address, login names/IDs, duration, and timestamps** for analysis and investigation should be gathered."* | p75 |
| 9 | *"**Collection of connection logs** can help in determining the **unnecessary utilization** of a wireless network in the organization."* | p75 |
| 10 | *"The network should be monitored using **wireless intruder detection-prevention system (WIDPS) sensors** and **WLAN scanners** in order to detect a **rogue WLAN connection**."* | p75 |
| 11 | *"**Locations within close proximity** of the organization **must be scanned**."* | p75 |
| 12 | *"**Security of the link** though which information is passed among the components in the network should be **monitored**."* | p76 |
| 13 | *"A detection should be made of the **laptops that are being illegitimately used as APS**."* | p76 |

**Exam thread:** items 3, 4, 6 + slide 3 all concern the **SSID** → [[13-LO04c-Disable-SSID-Broadcasting]].
Item 1 → [[13-LO04k-Router-Administrative-Security]]. Item 10 → [[13-LO04j-WIDS-WIPS]].
Item 13 and item 10 → [[13-LO04g-Rogue-Access-Point-Detection]].

## Module summary _(Mod 13 p77)_

> Reproduced as printed. Where it conflicts with the module body it is recorded, **not reconciled** —
> see `unresolved`.

### Introductory paragraph _(Mod 13 p77)_

*"This module covered several fundamental concepts of wireless network security such as the **security
standards, topologies, encryption types, and different security measures** that should be implemented
in order to achieve a **robust Wi-Fi security**. With the skills learned in this module, you will be
able to:"*

- **Configure a wireless router** to provide a robust and secure wireless network
- **Identify all the possible vulnerabilities and threats** to the wireless network
- **Defend against most wireless attacks** on the wireless network

### Key concepts on the summary page _(Mod 13 p77)_

| # | Statement as printed |
|---|----------------------|
| 1 | *"A wireless network uses the **IEEE standard of 802.11** and uses **radio waves** for communication"* |
| 2 | *"An AP is a **hardware device** that permits wireless communication devices to connect to a wireless network by using the **wireless standards such as Bluetooth, Wi-Fi**, etc."* |
| 3 | *"**WPA is a data encryption method** used for WLANs based on the 802.11 standards"* |
| 4 | *"In the **open system authentication** technique, **any wireless device can be authenticated with the AP**, allowing the device to transmit data **only when its WEP key matches the WEP key of the AP**"* |
| 5 | *"**Wireless traffic analysis** helps a user to **identify intrusion attempts** on a wireless network"* |
| 6 | *"**Active wireless network scanning and wired network scanning** should be conducted in order to detect the presence of wireless APs **in close proximity to an organization**"* |

### Summary vs body — contradictions recorded

| Summary says _(p77)_ | Module body says | Status |
|-----------------------|------------------|--------|
| An AP connects devices using *"the wireless standards such as **Bluetooth**, Wi-Fi"* | Same page, statement 1: a wireless network *"uses the **IEEE standard of 802.11**"* | ⚠️ internal contradiction, unresolved |
| *"**WPA** is a data encryption method"* — WPA is the only encryption mode named | p56 ranks **WPA3** first and **WEP** last of seven modes; WPA2 is never named on p77 | ⚠️ unresolved |
| Six key concepts only — none of the LO#04 measures appears | pp49–76 carry fifteen measures and thirteen further guidelines | coverage gap, not a contradiction |

## Related

- The full measure list this summary closes out: [[13-LO04a-Security-Measures-and-Wireless-Inventory]]
- Encryption mechanisms behind summary point 3: [[13-LO02e-WEP-vs-WPA-vs-WPA2-vs-WPA3]]
- Open system authentication behind summary point 4: [[13-LO03a-Open-System-Authentication]]
- Scanning behind summary point 6: [[13-LO04g-Rogue-Access-Point-Detection]]






