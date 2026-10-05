---
type: note
module: "13"
lo: "04"
tags: [threat, bestpractice, tool, mod/13]
topic: "Wireless monitoring and WPA cracking"
exam_weight: unknown
status: done
unresolved:
  - "pp58-59 the minimum passphrase length CONTRADICTS ITSELF. The p59 body rule list says a WPA password 'should have at least 12 characters in length' while the p59 Passphrase Complexity callout on the same page says to 'Select a complex passphrase which contains a minimum of 20 characters'. Both reproduced as printed; NOT reconciled. Neither figure is presented as governing the other."
  - "p59 the callout reads 'The only way to crack WPA is to sniff the password pairwise master key (PMK) associated with the \"handshake\" authentication process.' The phrase 'password pairwise master key (PMK)' is the OCR form and is grammatically incoherent as printed. Quoted verbatim; the intended syntax is not recoverable."
  - "p59 the callout spells WPA3 as 'WAP3' in one line ('Use WPA3 /WAP2 encryption only'). Normalised to WPA3 / WPA2."
  - "p58 the Wireshark capture is a screenshot whose packet list, addresses and frame details are heavily OCR-garbled. Only the readable protocol label 802.11 and the standard frame labels were used; no packet values were transcribed."
  - "p58 the source states the sniffing workflow as selecting the user's wireless network interface and starting the sniff process, then looking for traffic based on the 802.11 standard wireless protocols and applying filters. No interface name, filter expression or command line is given."
  - "p59 the countermeasure list gives 'Use a virtual private network (VPN) such as a remote access VPN, Extranet VPN, Intranet VPN, etc.' The courseware names these VPN types but gives no configuration or protocol."
---

[[MOC-Module-13]]

# Wireless Monitoring and Defending Against WPA Cracking (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp58–59 — security measures **6** (monitor traffic) and **7** (defend against WPA cracking).

## Monitoring the Wireless Network Traffic _(Mod 13 p58)_

- *"**Wireless network traffic analysis helps in identifying intrusion attempts** on a wireless
  network."*
- *"**A continuous monitoring and analysis** of the wireless network traffic should be done for
  **scanning any abnormalities**."*
- *"The traffic of a wireless network should be monitored in order to find any **abnormalities or
  signs of an attack**."*
- Tool: **Wireshark** (`http://www.wireshark.org`) — *"Similar to a wired network, the network traffic
  on a wireless network can be monitored using **packet sniffing utilities such as Wireshark**."*

### How _(Mod 13 p58)_

1. **Select the user's wireless network interface** and start the sniff process on it.
2. Look for traffic based on the **802.11** standard wireless protocols denoting the wireless network traffic.
3. **Apply various filters** to filter out the traffic of the user's interest.

## Defending Against WPA Cracking _(Mod 13 p59)_

### The attack model _(Mod 13 p59)_

> **"The only way to crack WPA is to sniff the password pairwise master key (PMK) associated with the \"handshake\" authentication process. If this password is extremely complicated, it might be almost impossible to crack."**

**So the entire defence is the passphrase.** The callout is organised in three buckets:

| Bucket | Control _(Mod 13 p59)_ |
|--------|------------------------|
| **Client Settings** | Use **WPA3 / WPA2 encryption only**; set the client settings properly (e.g. **validate the server, specify the server address, do not prompt for new servers**, etc.) |
| **Passphrase Complexity** | Select a **random passphrase that is not made up of dictionary words**; select a complex passphrase which contains a **minimum of 20 characters** and **change the passphrase at regular intervals** |
| **Additional Controls** | Use a **VPN** such as a **remote access VPN, Extranet VPN, Intranet VPN**, etc.; implement a **network access control (NAC)** or **network access protection (NAP)** solution for additional control over end-user connectivity |

### What not to put in the key _(Mod 13 p59)_

*"The following countermeasures can help a user to defeat WPA cracking attempts:"*

- **Construct a strong WPA password/key.**
- **Do not use** words **from the dictionary**.
- **Do not use** words **with numbers appended at the end**.
- **Do not use** **double words** or **simple letter substitution** such as `p@55wOrd`.
- **Do not use** common sequences from your keyboard such as `qwerty`.
- **Do not use** common **numerical sequences**.
- **Avoid using personal information** in the key/password.

### The six construction rules _(Mod 13 p59)_

*"A WPA password should be constructed according to the following rules:"*

1. It should have a **random passphrase**.
2. It should have **at least 12 characters** in length. ⚠️
3. It should contain **at least one uppercase letter**.
4. It should contain **at least one lowercase letter**.
5. It should contain **at least one special character** such as `@` or `!`.
6. It should contain **at least one number**.

> ⚠️ **12 characters here vs 20 characters in the Passphrase Complexity callout on the same page.**
> Recorded in `unresolved`; not reconciled.

## Related

- The cracking tools themselves are catalogued in [[13-LO04i-Wireless-Security-Assessment-Tools]] — Aircrack-ng, WEPCrack, WepAttack, WepDecrypt
- Encryption weaknesses: [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]] · [[13-LO02b-WPA-Encryption]]
- Mode selection: [[13-LO04d-Strong-Wireless-Encryption-Mode]]
- NAC/RADIUS side: [[13-LO03c-Centralized-Authentication-Server]]






