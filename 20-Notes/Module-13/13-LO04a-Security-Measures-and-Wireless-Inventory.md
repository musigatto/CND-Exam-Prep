---
type: note
module: "13"
lo: "04"
tags: [policy, bestpractice, mod/13]
topic: "Security measures and wireless inventory"
exam_weight: unknown
status: done
unresolved:
  - "p48 prints the LO#04 section header as 'Discuss the various security measures that must be implemented in wireless networks' (preposition 'in'), while the module objective list on p3 reads 'Discuss the security measures that must be implemented for wireless networks'. Both forms preserved; the header below uses the p3 wording."
  - "p49 carries a 15-item measure list and p50 carries a 13-item 'activities' list of the same subject. 'Implement WEP 128 enhanced encryption protocol combination of 104-bit & 24-bit key' and 'Update to the latest available firmware' appear on p49 only. The source does not explain the difference."
  - "p49 presents 'Implement WEP 128 enhanced encryption protocol combination of 104-bit & 24-bit key' as an activity that defends and maintains wireless security, while the order of preference for choosing an encryption mode on p56 ranks WEP last of seven. The source does not reconcile the two; both reproduced as printed."
  - "p49 the measure 'Implement a wireless intrusion detection system (WIDS)/wireless intrusion prevention system (WIPS' has an unclosed parenthesis in the source as printed."
  - "p49 'Detect ro ue APs' carries an OCR split inside the word rogue. Normalised to rogue."
  - "p50 the sentence introducing the activity list is 'The following activities help in defending and maintaining the security of a wireless network:' - the word 'activities' is the only label the list carries; it is not called the measures list."
  - "p51 the product name reads 'Acrylic Wi-Fi HeatMaps (a 20'. The trailing '(a 20' is garbled and the full product name is NOT recoverable. Quoted up to 'HeatMaps'; nothing supplied."
  - "p51 'A network is only as secure as its weakest link.' appears as a standalone sentence with no elaboration or attribution."
  - "pp49-50 the wireless-security-implementation list straddles the page break: 'Furthermore, a successful and effective wireless security implementation should involve the following:' and its first two items are on p49, the last two on p50."
---

[[MOC-Module-13]]

# Security Measures and Wireless Inventory (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp48–51.

*"The objective of this section is to explain the various security measures that must be implemented to secure the wireless network."* _(Mod 13 p48)_

> **"A wireless network can be insecure if proper care has not been taken while configuring it. Insecure configurations can pose a great risk to the wireless networks. Thus, a wireless network should be configured as per the wireless security policy of the organization."** _(Mod 13 p49)_

## The LO#04 measures list _(Mod 13 pp49–50)_

p49 prints it as 15 measures; p50 reprints it as 13 "activities". Differences marked below.

| # | Measure (p49 wording) | Activity (p50 wording) | Detail |
|---|----------------------|----------------------|--------|
| 1 | Create an inventory of wireless devices | Creating an inventory of the wireless devices | see *Creating an Inventory* below |
| 2 | Placement of the wireless AP and antenna | Placement of the wireless AP and antenna | [[13-LO04b-AP-and-Antenna-Placement]] |
| 3 | Disable SSID broadcasting | Disable SSID broadcasting | [[13-LO04c-Disable-SSID-Broadcasting]] |
| 4 | Select a strong wireless encryption mode | Selecting a strong wireless encryption mode | [[13-LO04d-Strong-Wireless-Encryption-Mode]] |
| 5 | Implement MAC address filtering | Implementing MAC address filtering | [[13-LO04e-MAC-Address-Filtering]] |
| 6 | Monitor wireless network traffic | Monitoring wireless network traffic | [[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]] |
| 7 | Defend against WPA cracking | Defending against WPA cracking | [[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]] |
| 8 | Detect rogue APs | Detecting rogue APs | [[13-LO04g-Rogue-Access-Point-Detection]] |
| 9 | Locate rogue APs | Locating rogue access points | [[13-LO04g-Rogue-Access-Point-Detection]] |
| 10 | Protect from denial-of-service (DOS) attacks: interference | Protecting from DoS attacks | [[13-LO04h-RF-Interference-Protection]] |
| 11 | Assess wireless network security | Assessing the wireless network security | [[13-LO04i-Wireless-Security-Assessment-Tools]] |
| 12 | Implement a WIDS / WIPS *(paren unclosed in source)* | Deploying a WIDS and WIPS | [[13-LO04j-WIDS-WIPS]] |
| 13 | Configure the security on wireless routers | Configuring the security on wireless routers | [[13-LO04k-Router-Administrative-Security]] |
| 14 | Implement WEP 128 enhanced encryption protocol — combination of 104-bit & 24-bit key | *(absent on p50)* | [[13-LO02a-WEP-Encryption]] |
| 15 | Update to the latest available firmware | *(absent on p50)* | [[13-LO04k-Router-Administrative-Security]] |

## What the wireless security policy must state _(Mod 13 p49)_

*"The following points should be clearly stated in the organization's wireless security policy:"*

- **Identity of the users** who are using the network
- Whether the user is **allowed access or not**
- **Who can and cannot install the APs** and other wireless devices in the enterprise
- **The type of information** users are allowed to communicate over the wireless network
- **Limitations on APs** such as location, cell size, frequency, etc. — *"in order to overcome the wireless security risks"*
- The **standard security settings** for wireless components
- **The conditions** in which wireless devices are allowed to use the network

## What an effective implementation involves _(Mod 13 pp49–50)_

*"Furthermore, a successful and effective wireless security implementation should involve the following:"*

1. **Centralized implementation** of security measures for all wireless technology
2. **Security awareness and training programs** for all employees
3. **Standardized configurations** to reflect the security policies and procedures of the organization
4. **Configuration management and control** to make sure the latest security patches and features are available on wireless devices

## Creating an Inventory of Wireless Devices _(Mod 13 p51)_

Callout: *"Identify and document all the client devices according to the **make/models/applications, encryption, firmware, wireless channel, etc.** This helps the network defenders to manage and monitor the wireless devices in the network."* — tool shown: **Acrylic Wi-Fi HeatMaps**, `http://www.acrylicwifi.com` _(name garbled — see `unresolved`)_

*"The use of wireless devices in various organizations is continuously growing."*

- **Track and manage wireless assets for security purposes** — *"Maintaining an accurate and up-to-date inventory of wireless devices is required for proper security."*
- A device inventory **consolidates all the updated network data and devices**.
- It helps **quickly identify non-functioning devices** as well as **rogue network devices** present on the network.
- **Trap:** also keep a list of devices **not connected** to the network — *"This helps in detecting unknown devices in the network."*
- **Regular scanning of the inventory** surfaces: rogue network devices · problematic devices · potential vulnerabilities · devices needing a patch/update.
- *"A network is only as secure as its weakest link."*
- Maintain records for **all** devices — *"regardless of their configuration settings or the vendor."*
- Maintain it **manually or with the help of an effective inventory tracking solution**.
- *"At times, an inventory tool may not auto-update the network device. In such scenarios, information of a device should be manually added in the inventory list."*

## Related

- Detection depends on the inventory — the AP-not-in-inventory rule is the core of [[13-LO04g-Rogue-Access-Point-Detection]]
- Firmware updates are measure 15 here and item 11 in [[13-LO04k-Router-Administrative-Security]]





