---
type: note
module: "13"
lo: "04"
tags: [policy, bestpractice, mod/13]
topic: "Router administrative security"
exam_weight: unknown
status: done
unresolved:
  - "pp73-74 the two lists DISAGREE. The p73 slide has five settings and the p74 body list has eleven. 'Enable logging' appears on p73 only and is absent from the eleven p74 recommendations. The source gives no statement that the five are a subset of the eleven."
  - "pp73-74 all walkthrough screenshots (LINKSYS Wireless-G and CISCO administration pages) are heavily OCR-garbled. The only reliably legible control names are 'Administration Password', 'Local Access', 'Web Access', 'Remote Router Access', 'UPnP Access', 'Incoming Log', 'Outgoing Log', 'Save Settings', 'Cancel Changes', 'HTTP', 'HTTPS', 'Enable', 'Disable'. No UI text is transcribed as an instruction and no default value is read off the screenshots."
  - "p73 'Choose the HTTPS for secure communication' is reproduced with the article as printed; p74 gives the expansion 'hypertext transfer protocol secure (HTTPS)'."
  - "p74 'Disabling the demilitarized zone (DMZ) option' is listed as a router hardening step, but the section never explains what the DMZ option does on the router."
  - "p74 item 9 'Configuring the QoS settings' carries no stated security purpose; no QoS parameter or recommendation is given."
  - "p74 item 10 'Avoid using the default IP ranges' gives no subnet, CIDR block or default range."
---

[[MOC-Module-13]]

# Configuring the Administrative Security on Wireless Routers (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp73–74 — security measure **13**, *"Configure the security on wireless routers"*.

> **"In order to harden the wireless router, the recommended security configurations should be applied on the wireless router. These security configuration settings help minimize any wireless attacks and provide the best performance, security, and reliability when using Wi-Fi."** _(Mod 13 p74)_

## The five settings on the p73 slide _(Mod 13 p73)_

1. **Change the default password** on the wireless router
2. **Assign a strong and complex password** to the router
3. **Choose the HTTPS** for secure communication
4. **Disable remote router access**
5. **Enable logging**

## The eleven recommendations _(Mod 13 p74)_

*"The following are the security recommendations that must be considered:"*

| # | Recommendation | Group |
|---|----------------|-------|
| 1 | **Changing the default password** of the wireless router | credentials |
| 2 | **Assigning a strong and complex password** to the router | credentials |
| 3 | Choosing the **hypertext transfer protocol secure (HTTPS)** for secure communication | transport |
| 4 | **Disabling the remote router access** | exposure |
| 5 | **Enabling the firewall** to block certain **WAN requests** | filtering |
| 6 | **Configuring an internet access policy** | filtering |
| 7 | **Specifying the blocked services, URL, keywords**, etc. | filtering |
| 8 | **Disabling the demilitarized zone (DMZ)** option | exposure |
| 9 | **Configuring the QoS settings** | *(no security purpose stated)* |
| 10 | **Avoid using the default IP ranges** | addressing |
| 11 | **Keep the router firmware up-to-date** | patching |

> ⚠️ **List mismatch:** *"Enable logging"* is on the p73 slide but **not** among the eleven p74
> recommendations. The source does not reconcile the two lists. See `unresolved`.

### Grouping at a glance

| Group | Items |
|-------|-------|
| **Credentials** | default password → changed; strong and complex password → assigned |
| **Management transport** | HTTPS instead of HTTP |
| **Remote exposure** | remote router access disabled; DMZ option disabled |
| **Filtering** | firewall blocks certain WAN requests; internet access policy; blocked services / URL / keywords |
| **Addressing** | avoid the default IP ranges |
| **Patching** | keep the router firmware up-to-date |
| **Traffic control** | QoS settings |

## Related

- Firmware currency is also measure 15 of the LO#04 list — [[13-LO04a-Security-Measures-and-Wireless-Inventory]]
- Logging out of the router web interface is a further guideline — [[13-LO04l-Additional-Guidelines-and-Module-Summary]]
- Placing a firewall or packet filter between the AP and the corporate intranet — [[13-LO04l-Additional-Guidelines-and-Module-Summary]]






