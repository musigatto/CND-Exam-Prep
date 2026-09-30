---
type: note
module: "12"
lo: "05"
tags: [crypto, process, mod/12, flashcard/12]
topic: "Azure encryption in transit — HTTPS, SAS, SMB 3.x, client-side, Site-to-Site VPN"
exam_weight: unknown
status: done
unresolved:
  - "p201 the 'secure transfer required' walkthrough is printed as a single run-on chain: 'Open Microsoft Azure Menu>Click on All Services>Click on Storage Account>Create Storage Account — Enter the details>Go to Menu Tab Advanced Option and enable secure transfer required.' It is reproduced as printed; whether 'Advanced Option' is a tab or a checkbox is not resolvable. Fig 12.131's own text OCRs to 'Advanced Dataprotection Encryption Review C one.... the impact En.\" .cco•unt key O N,mewe control CACO) ...m mo.\"' — not transcribed."
  - "pp200-202 the Site-to-Site VPN values appear as 'VNet1toSite2' in the p200 figure and 'VNet ItoSite2' in Fig 12.132; the leading character after 'VNet' is an OCR digit/letter confusion (1 vs I). 'VNet1GW' and 'Site2' are clear."
  - "pp200-202 the 'Shared key (PSK)' value prints as 'abci23' in both figures — an obvious placeholder in the screenshot, not a stated default or a real key. Reproduced as a screenshot value only."
  - "p201 the portal path 'Open the virtual network gateway page (Name of VNet -> Overview -> Connected devices -> Name of gateway)' is the only path printed before the connection steps; no virtual-network-gateway creation step exists in this range (pp200-202). No gateway SKU, subnet or public-IP step is given."
  - "pp200-202 no numbered steps are printed for practice 1 (HTTPS), practice 3 (SMB 3.x) or practice 4 (client-side encryption) beyond the prose; only practice 2 (secure transfer required) and practice 5 (Site-to-Site VPN) have click paths."
---

[[MOC-Module-12]]

# Azure Encryption — In Transit (§12.05)

> Covers pp. 200–202: the five practices the courseware lists · secure transfer required on a storage
> account · SMB 3.x · client-side encryption · Site-to-Site VPN creation.
> At rest: `[[12-LO05g-Azure-Encryption-Data-at-Rest]]`. Inbound hardening:
> `[[12-LO05i-Azure-Inbound-Access-Control]]`.

## The five practices — rules the courseware states _(Mod 12 p200)_

| # | Practice (as printed) | Detail printed |
|---|---|---|
| 1 | **Use HTTPS** | "for accessing objects in the **Azure Storage** and calling **REST APIs**" |
| 2 | **Use Shared Access Signatures** | "and enable **Secure Transfer Required** on the storage accounts" |
| 3 | **Use SMB 3.x** | "connections in the **Azure File Storage**" |
| 4 | **Use client-side encryption** | "to encrypt data **before transferring into Azure Storage** and decrypt **before receiving on the client side**" |
| 5 | **Use Azure Site-to-Site VPN** | "Create a **site-to-site or point-to-site** virtual private network (VPN) to **encrypt between a corporate network and the Azure virtual network**" |

Detail per practice _(pp200–201)_:

- **1 — HTTPS**: "Azure storage data can be secured by encrypting the data between the storage and
  client. To establish a secure communication channel, users should **always use the HTTPS protocol**
  while accessing an object from Azure storage or calling the REST APIs."
- **2 — SAS + secure transfer required**: "Shared access signatures **can use the HTTPS protocol** for
  secure communication. In the storage account, the **secure transfer required** option should be
  enabled, which **enforces the HTTPS protocol** when using the REST APIs."
- **3 — SMB 3.x**: "**SMB 3.0 uses encryption during transit**; it is available in **Windows Server
  2012 R2, Windows 8, Windows 8.1, and Windows 10**, which allows **cross-region access**."
- **4 — client-side encryption**: "encrypts the data **before transferring** to Azure storage and
  decrypts the data **when the client wants to retrieve** them. It encrypts the data **at rest** and
  stored in the **encrypted form**."

### Enable "secure transfer required" — walkthrough _(Mod 12 p201, Fig 12.131)_

1. Open the Microsoft Azure Menu.
2. Click on **All Services**.
3. Click on **Storage Account**.
4. **Create Storage Account** — enter the details.
5. "Go to **Menu Tab Advanced Option** and enable **secure transfer required**."

_(printed as one run-on chain; see `unresolved:`)_

## Site-to-Site vs Point-to-Site VPN — the rule _(Mod 12 p201)_

| | Site-to-Site VPN | Point-to-Site VPN |
|---|---|---|
| Scope | "connects the **entire network** (e.g., on-premise network) to the Azure virtual network" | "connects a **single device** to the Azure virtual network" |
| Crypto | "trustworthy and uses a **highly secure IPsec tunnel mode** VPN protocol" | — |

Both "site-to-site and point-to-site VPNs enable **cross connectivity**." _(p201)_

## Create a Site-to-Site VPN — walkthrough _(Mod 12 pp201–202)_

1. "Open the **virtual network gateway page** (Name of VNet → Overview → Connected devices → Name
   of gateway)." _(p201)_
2. "Click on **Connections**, followed by **+Add**." _(p201)_
3. "Fill the details in the **Add connection** page → **Connection type** and select
   **Site-to-Site (IPsec)**." _(p201)_
4. "Click on **OK** to create connection." _(p202)_

**Values printed in the connection figure** _(p200, p202 Fig 12.132)_

| Field | Value |
|---|---|
| Name | `VNet1toSite2` |
| Connection type | `Site-to-site (IPsec)` / `(IPsec)` |
| Virtual network gateway | `VNet1GW` |
| Local network gateway | `Site2` |
| Shared key (PSK) | `abci23` _(screenshot placeholder — not a default)_ |

## Cards

The five practices the courseware gives for encrypting data in transit in Azure
?
Use HTTPS for Azure Storage objects and REST APIs · use Shared Access Signatures and enable Secure Transfer Required on storage accounts · use SMB 3.x for Azure File Storage · use client-side encryption before transfer into Azure Storage and decrypt on receipt · use Azure Site-to-Site (or point-to-site) VPN to encrypt between the corporate network and the Azure VNet

What does "secure transfer required" actually do on an Azure storage account
?
It enforces the HTTPS protocol — including when Shared Access Signatures and the REST APIs are used — so storage traffic cannot fall back to unencrypted HTTP

What the courseware states about SMB 3.x in Azure File Storage
?
SMB 3.0 uses encryption during transit, is available in Windows Server 2012 R2, Windows 8, Windows 8.1 and Windows 10, and allows cross-region access

Site-to-Site VPN versus Point-to-Site VPN in Azure — the scope difference
?
Site-to-Site connects the entire network (e.g., on-premise) to the Azure virtual network over a highly secure IPsec tunnel mode; Point-to-Site connects a single device to the Azure virtual network; both enable cross connectivity

The values printed in the Azure Add-connection form for a Site-to-Site VPN
?
Name VNet1toSite2 · connection type Site-to-site (IPsec) · virtual network gateway VNet1GW · local network gateway Site2 · shared key (PSK) — then click OK to create the connection