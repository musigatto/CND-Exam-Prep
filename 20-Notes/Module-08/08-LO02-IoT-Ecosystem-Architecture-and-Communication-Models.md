---
type: note
module: "08"
lo: "02"
tags: [concept, process, protocol, mod/08]
topic: "IoT Ecosystem, Architecture, and Communication Models"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Ecosystem, Architecture, and Communication Models (§8.2)

## IoT Architecture
- **Gateway:** transmits data things↔cloud; pre-processing + filtering (lesser data volumes); sends control commands from cloud to things' actuators
  - **Cloud gateway:** data compression · securing field-gateway↔cloud transfer · protocol compatibility · multi-protocol communication with field gateways
- **Streaming data processors:** effective input→data lake transition; application control
- **Data lakes:** store device data in natural format; extracted → big data warehouse on demand
- **Big data warehouse:** only cleaned/structured/matched data; stores context info (sensor locations) + commands sent by control apps
- **Data analytics:** trends/actionable insights (device performance, inefficiencies); schemas/diagrams/infographics; feeds control-app algorithms
- **Machine learning:** builds/updates models for control apps from warehouse data (e.g., employee behavior → light control)
- **Control applications:** send automatic commands + alerts to actuators; pre-failure notification to system engineers; stored commands aid investigation + breach detection
  - Types: **rule-based** (rules set by specialists) · **machine-learning-based** (models updated regularly)
- **User applications** (web/mobile): let users change behavior of control applications

## Layers of the IoT Architecture (4)
| Layer | Contents |
|---|---|
| **Layer 1 — Device Layer** | hardware: sensors (temperature, gyroscope, pressure, light, GPS, electrochemical, RFID), mobile devices, microcontroller units, networking gear, single-board computers |
| **Layer 2 — Communication Layer** (connectivity/edge computing) | protocols + networks: TCP/IP for Internet-based; LAN, RF, Wi-Fi, Li-Fi for intranet; gateways manage traffic (level-5 gateways for monitoring) |
| **Layer 3 — Cloud Platform Layer** | cloud servers accept/store/process sensor data from gateways; dashboards for monitoring/analyzing/proactive decisions |
| **Layer 4 — Process Layer** | people, businesses, collaborations; decision making from policies/procedures of IoT computing |

- Ecosystem components: dashboards, remotes, gateways, analytics, networks, data storage, security

## IoT Communication Models
| Model | Description | Notes |
|---|---|---|
| **Device-to-Device** | connected devices interact via the Internet but primarily directly (Bluetooth, Z-Wave, Zigbee, Wi-Fi) | smart home (thermostats, bulbs, locks, CCTV, refrigerators), wearables; ECG/EKG paired to smartphone |
| **Device-to-Cloud** | device↔cloud directly (Wi-Fi, Ethernet, cellular) | CCTV camera example: device→cloud→user after credentials |
| **Device-to-Gateway** | device → local gateway (smartphone/hub) → cloud; gateway adds security + data/protocol translation | protocols: ZigBee, Z-Wave; app-layer gateway (smart TV app); IEEE 802.11 (Wi-Fi), IEEE 802.15.4 (LR-WPAN) |
| **Back-end Data-Sharing** (cloud-to-cloud) | extends device-to-cloud; data from devices accessed/analyzed by **authorized 3rd parties** | e.g., analyzer of monthly/yearly energy consumption; HTTPS, OAuth 2.0, JSON; multiple service providers |

## IoT-enabled IT Environment
- Tiers: **things/devices** (smartphones, wearables, autonomous machines, tags — RFID, NFC, QR; sensors for air quality, humidity, light, pressure) → **gateway/control tier** (pre-processes data, proxy/edge for legacy + low-power devices, routes commands; PAN/LAN, Bluetooth, Zigbee, MQTT/TCP, micro-computing) → **communication/data center/cloud platform tier** (event processing + analysis, data storage, message/connectivity routing, app integration; SaaS, business data analysis, user access controls, remote web servers, Linux)
- Cloud gateway **authenticates + authorizes** devices; handles different protocols/data formats; devices + local gateways register (SOAP, REST, AMQP)
- Tiers scale horizontally (more devices) + vertically (different solutions)

## IoT-Enabled IT Environment Features
- **Real-time monitoring** (assets/products/flow, detect issues, act immediately)
- **Real-time analytics** (graphs + streaming analytics)
- **Multi-layer security** (MFA, TLS, device identity management)
- **Data collection** (lightweight, low-bandwidth protocols)
- **Communication among multiple devices** (remote access anytime/anywhere)

## Cards
Q:: Four layers of the IoT architecture (top-down)?
A:: Device → Communication → Cloud Platform → Process.
#flashcard
Q:: IoT device-layer components?
A:: Sensors (temp, gyroscope, pressure, light, GPS, electrochemical, RFID) · mobile devices · microcontroller units · networking gear · single-board computers.
#flashcard
Q:: Four IoT communication models?
A:: Device-to-Device · Device-to-Cloud · Device-to-Gateway · Back-end Data-Sharing (cloud-to-cloud).
#flashcard
Q:: Protocols characteristic of device-to-gateway communication?
A:: ZigBee, Z-Wave (local), IEEE 802.11 (Wi-Fi), IEEE 802.15.4 (LR-WPAN).
#flashcard
Q:: Back-end data-sharing model?
A:: Extends device-to-cloud: device data is accessed/analyzed later by authorized third parties (HTTPS, OAuth 2.0, JSON).
#flashcard
Q:: Cloud gateway functions?
A:: Authenticate/authorize devices · data compression · secure device↔cloud transfer · protocol compatibility gateway.
#flashcard