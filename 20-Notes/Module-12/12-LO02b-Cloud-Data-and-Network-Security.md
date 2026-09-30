---
type: note
module: "12"
lo: "02"
tags: [threat, bestpractice, mod/12, flashcard/12]
topic: "Cloud data storage security and network security"
exam_weight: unknown
status: done
unresolved:
  - "p26: the p26 body sentence beginning 'Key management involves generating, using, protecting, storing, backing up, and deleting the encryption keys.' is complete in the slice, but the sentence immediately after it on p26 ('Strengthen passwords and change them at regular intervals…') has no figure-side counterpart; only the readable prose is used."
  - "p28: the final body sentence is cut off mid-clause in the slice — 'Using standard secure encapsulation protocols such as IPSEC, deployment SSH, and SSL during'. Nothing is asserted beyond that fragment."
  - "p28: the p28 figure's 'Network Security' checklist is transcribed as printed; the figure shows it as a plain bullet list with no per-item mapping to the five layers, so no layer assignment is inferred."
  - "p28: 'Virtual Network SSTP' in the p28 layer figure is garbled (SSTP is most likely a mis-OCR of SSH/TLS but the token is not resolvable with certainty) — the Azure PSTP/virtual-network item is not asserted here."
---

[[MOC-Module-12]]

# Cloud Data and Network Security (§12.02)

> **LO#02 — Understanding cloud security insights**
> Section scope: enterprise roles in securing cloud elements — data storage security, network
> security, monitoring, logging, compliance _(Mod 12 p20)_

## Data storage security _(Mod 12 p26)_

- In the cloud, data are stored on **internet-connected servers in data centers**, and it is the
  responsibility of the **data centers** to secure the data — **but customers should protect their
  data** to ensure comprehensive data security. _(p26)_
- **Data loss ⇒ financial loss as well as legal actions.** Hence essential for an organization to
  **locally back up** the data. _(p26)_
- **Avoid saving sensitive information (patents, copyrights) on the cloud** — compromising with
  its storage there may create problems for the organization. _(p26)_
- **Local encryption before uploading** to the cloud protects data from threats. Better: pick a
  provider that can supply **prerequisite data encryption**, or a primary encryption service,
  for consumers who already have an encrypted cloud service. _(p26)_
- Cloud key management must **generate, use, protect, store, back up and delete** the encryption
  keys; cloud key management gives strict key security because of the **increased possibility
  of key exposure**. _(p26)_
- Harden on top of encryption: **strong passwords changed at regular intervals**, a
  **two-step verification process**, **updated patches**, and cloud-offered **antivirus programs,
  admin privileges and local encryption**. _(p26)_

### Data storage security techniques (p26 figure, as printed)

| Technique | Purpose |
|---|---|
| **Local data encryption** | Ensuring confidentiality of sensitive data in the cloud |
| **Key management** | Generating, using, protecting, storing, backing up, and deleting encryption keys |
| **Strong password management** | Using strong passwords and changing them at regular intervals |
| **Periodic security assessment of data security controls** | Continuously monitoring and reviewing the implemented data security controls |
| **Cloud data backup** | Taking **local** backups of the cloud data prevents possible data loss in the organization |

_(Mod 12 p26)_

## Testing cloud data security _(Mod 12 p27)_

- It is **essential to test the cloud data security** to determine its **performance**. _(p27)_
- Testing can help in **finding security loopholes**. _(p27)_
- Ensuring data security on the cloud **required constant action**. _(p27)_

## Network security — main challenges _(Mod 12 p28)_

| Item | Statement |
|---|---|
| **Main challenge in cloud network security** | The **lack of network visibility in monitoring and managing suspicious activities by the consumer** |
| Additional features needed | Cloud network security requires **additional** security features compared to traditional network security features |

_(Mod 12 p28)_

### Additional cloud network security features (p28 figure, as printed)

```
Encrypt data-in-transit                 Implement layers of firewall
Provide multi-factor authentication    Install firewalls
Enable data loss prevention            Using DMZs
Isolating resources with subnets, firewalls, and routing tables
Securing DNS configurations             Limiting inbound/outbound traffic
Securing accidental exposures           Intrusion detection and prevention systems
```

_(Mod 12 p28)_

### Provider vs. consumer network layer

- **Provider side:** CSPs ensure network-level protection by implementing network security
  controls — e.g. **Network Access Control List (NACL)** in the **AWS** cloud, while
  **Endpoint** and **NSG** are implemented in the **Azure** cloud. _(p28)_
- **Consumer side:** use **additional** network-security levels for network-layer protection via
  **firewall** and **web application firewall (WAF)**; the use of firewalls **guarantees
  isolation between multiple zones**. _(p28)_
- Principles to satisfy the technology and security principles established by the providers
  _(p28)_:
  - Network control for **traffic flow**
  - **End-to-end transport level encryption**
  - "Using standard secure encapsulation protocols such as **IPSEC**, deployment **SSH**, and
    **SSL** during" — sentence truncated in the source; nothing further asserted.

## Cards

Main challenge in cloud network security, per the courseware
?
Lack of network visibility in monitoring and managing suspicious activities by the consumer

Five data storage security techniques
?
Local data encryption · Key management · Strong password management · Periodic security assessment of data security controls · Cloud data backup

Why must organizations keep local backups of cloud data?
?
Loss of data may imply financial loss as well as legal actions, so a local backup is essential to prevent possible data loss

Two-step verification and updated patches — what do they defend against?
?
They prevent hackers from attacking the systems easily

Which network security control does each cloud use — AWS vs Azure?
?
AWS: Network Access Control List (NACL) · Azure: Endpoint and NSG

Cloud network security — what does the firewall usage guarantee?
?
Isolation between multiple zones
