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

## Cards (verified set 617277655)

> Matched word-for-word to the module PDF. See [[External-Flashcards-Verification]].

Q:: IoT User applications
A:: These applications help change the behavior of the application controls.  _(Mod 08 p13)_
#flashcard

Q:: IoT Control applications
A:: Control applications send automatic commands and alerts to actuators and helps in investigating problematic cases and enhancing security by identifying security breaches.  _(Mod 08 p12)_
#flashcard

Q:: IoT Gateways
A:: Gateways are devices through which data are transmitted from things to the cloud and vice versa.  _(Mod 08 p11)_
#flashcard

Q:: IoT Streaming data processors
A:: These processors ensure that no data can be lost or corrupted  _(Mod 08 p11)_
#flashcard

Q:: IoT Cloud layer
A:: his layer consists of servers hosted in the cloud that accept, store, and process the sensor data received from IoT gateways.  _(Mod 08 p15)_
#flashcard

Q:: IoT Communication layer
A:: The communication layer includes the components of communication protocols and networks used for connectivity and edge computing.  _(Mod 08 p14)_
#flashcard

Q:: IoT Process Layer
A:: The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.  _(Mod 08 p15)_
#flashcard

Q:: Device-to-Device model
A:: In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.  _(Mod 08 p16)_
#flashcard

Q:: Device-to-Cloud model
A:: In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.  _(Mod 08 p17)_
#flashcard

Q:: Device-to-Gateway model
A:: In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.  _(Mod 08 p17)_
#flashcard

