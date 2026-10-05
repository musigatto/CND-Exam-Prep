---

type: note
module: "08"
lo: "04"
tags: [threat, process, protocol, mod/08]
topic: "IoT Device and Communication Layer Attacks & Countermeasures"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Device & Communication Layer Attacks + Countermeasures (§8.4)

## IoT Device Layer — Attacks
| Attack | Vector |
|---|---|
| **Node tampering** | access/alter/replace node; keys stolen |
| **Jamming** | inject interfering RF signals |
| **RF interference** | out-of-band RF → DoS |
| **Malicious node / node replication injection** | insert malicious node with duplicated identity |
| **Physical damage** | intentional damage breaks service |
| **Social engineering** | trick users |
| **Spoofing** | spoof protocol; tag cloning |
| **Tag cloning** | copy RFID tag memory |
| **Malicious code injection** | wireless/wired injection |
| **Unauthorized access** | access without rights |
| **Replay attack** | delay/capture → replay n-Steps later |
| **Timing attack / Side-Channel Attack (SCA)** | observe crypto execution (leakage) |
| **Eavesdropping** | tap = tagged as legitimate |
| **Object replication / responsiveness Looping** | duplicate legitimate object |
| **Hardware Trojan** | malicious hardware |
| **Outage attack** | battery draining, resource exhaustion |

## IoT Device Layer — Countermeasures
| Layer | Countermeasure |
|---|---|
| **Physical layer** | limit/inter-network jamming defense · frequency hopping spread spectrum (FHSS) · spread spectrum · increase transmit power |
| **Logical layer** | lightweight authentication using Perrig et al. protocol (confidentiality, completeness, freshness of data) |
| **Network layer** | per-node access control (AES, Elliptic-Curve) |
| **Generic** | avoid side-channel exploitation (differential multiple-level keys) |

## IoT Communication Layer — Attacks & Countermeasures
### RFID Attacks
- Tag cloning/spoofing (copy tag) → counter: kill commands, hash password protection
- Eavesdropping → radiofrequency shielding + encryption
- **Relay attacks** (reader+tag MITM) → counter: timers, challenge-response, distance-bounding protocols
- DoS → counter: on-tag access control
- **Cryptographic attacks (crypto smartcard)** → counter: random ID, protection frequency, back-end protection uses RSA/AES/TDES

### NFC Attacks
- **Relay attacks**, **eavesdropping** (RF shield), NFC **tag/clone/spoof**, **data corruption** (checksums, powerful RF field), **man-in-the-middle** (out-of-network reader channel), worn/torn tags (RFID shields)

### Bluetooth Attacks
| Attack | Description |
|---|---|
| **Bluesnarfing** | via Bluetooth, gain access to phone/Laptop data (exploit OBEX Push). Counter: put bluetooth in invisible mode, share nothing |
| **BlueBugging** | remote control of device (unrestricted access), can execute AT commands, connect to Internet, place calls (exploit OBEX Push profile / personal-area-network FTP). Counter: keep bluetooth off when not in use |
| **Bluejacking** | send unsolicited messages to nearby Bluetooth devices (spoofed via OBEX files). Counter: turn OFF bluetooth |
| **BlueSmack** | DoS "ping of death" via L2CAP packet; malformed packets you reply |
| **Car Whisperer** | obfuscated Bluetooth PIN/keys intercept; MDA crisis |
| **KNOB attack** | weaken encryption entropy (8 bytes → 1 byte) |

### Wi-Fi & Network Attacks
- WEP attacks: **Korek**, **Chopchop**, **Fragmentation**, **FMS**, **PTW**; **Google Replay attack** (recapture/replay WLAN packets)
- **Michael attack** (TKIP countermeasure flaw → forge fragmented packets), **dictionary attack**
- Countermeasures: short rekey, deactivate QoS, disable TKIP → switch to CCMP (CCMP/AES), IPsec, DTLS

### ZigBee / IEEE 802.15.4 attacks
- **KillerBee** (tools: zbdump, zbconvert, zbreplay, zbstumbler, zbfind, zbinject, zbopenear)
- **ZigBee spoofing** (jamming, frame detection; beacons swap; PAN ID / key theft; network keys in cleartext over-the-implementation while pairing)
- **Recommended:** encrypt with **AES-128**

### Z-Wave / 6LoWPAN / routing & network attacks
- Z-Wave **jamming/replay** of S2 messages (counter: **S2 security**)
- **RPL** attacks: DOG (Denial-of-Game), global repair attack, version number attack/modification, DAO (Destination Advertisement Object) inconsistencies
- **6LoWPAN** attacks: DoS(buffer full), fragmentation, intra/ext hammering
- **TCP/UDP attacks:** TCP SYN flood, UDP flooding, XMAS packets, Smurf attack, IP spoofing; counter: SYN cookies, firewalls, etc.
- **Application-protocol attacks** (CoAP/MQTT): DDoS high-bandwidth amplification; counter: authentication token, TLS/DTLS








