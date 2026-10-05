---
type: note
module: "12"
lo: "05"
tags: [concept, process, policy, mod/12]
topic: "Azure Firewall, WAF and Network Security Groups"
exam_weight: unknown
status: done
unresolved:
  - "p214 the Azure Firewall walkthrough jumps straight from 'To create a firewall, click on Create' to 'Fill in the details and click on Review + create'. No printed step covers the Basics/Tags tabs or any field (subscription, region, vnet/subnet, SKU), so no field names are asserted here."
  - "pp214-215 all Azure Firewall portal values are screenshot-only and heavily garbled ('Mioosoft Anne Firewall', 'Vittul • Trial', 'P'bbc IP AddrÐµss', 'Availabibty zone'). Instance names ('example 125'), region ('South India'), virtual network/subnet ('VNet1 / AzureFirewaIlSubnet') and private IP ('10.0.0.4') are lab screenshot values, not defaults."
  - "p218 Fig 12.152 'Add inbound security rule' blade is unreadable except for the labels 'Properties', 'Locks', 'Add', 'Add inbound security rule' and a garbled token ('Po,-t_•»'). No NSG rule property (priority, port, protocol, source, destination) is printed anywhere in pp216-218."
  - "pp216-218 the courseware never names the default NSG rules, their priorities or the built-in rule set content. Only this is printed: 'The default NSG rules cannot be deleted, but they can be overruled by the customers.'"
  - "p218 the NSG walkthrough ENDS at 'Enter the details and Save to create an NSG'. No step confirms the saved rule, and no outbound-security-rule walkthrough is printed."
  - "pp213-218 the courseware does NOT print any WAF configuration walkthrough, WAF policy/sku name, or Application Gateway WAF mode selection. Only the CRS versions (3.1, 3.0, 2.2.9) and automatic updating are stated."
---

[[MOC-Module-12]]

# Azure Firewall, WAF & Network Security Groups (§12.05)

> Covers pp. 213–218: perimeter networks for security zones (p213) · Azure Firewall
> (pp213–215) · Azure WAF (p215) · logical subnet segmentation with NSGs (pp216–218).
> Related: `[[12-LO05i-Azure-Inbound-Access-Control]]`,
> `[[12-LO05j-Azure-Load-Balancing]]`, `[[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]`.

## Slide objectives — as printed _(Mod 12 p213)_

| Objective | Printed text |
|---|---|
| Perimeter | "To provide additional security to Azure resources, use a **perimeter network for all high-security deployments**" |
| Azure Firewall | "A **managed, cloud-based network security service** to protect the **Azure Virtual Network resources**" |
| WAF | "**WAF protects application from web vulnerabilities and attacks**" |

_(Mod 12 p216)_ slide objectives: "Use a **Network Security Group (NSG)** to control the **inbound and outbound access** to subnets, VMs, and network interfaces (NICs)"; "**NSG contains rules that determine if a traffic is allowed or denied**".

## Stated rules (not walkthrough) — Azure Firewall _(Mod 12 p213)_

- "It is an **easily manageable cloud-based network security service** that protects the **Azure virtual resources**."
- "It **implements network connectivity policies in virtual networks**."
- "The customers can create **allow or deny network filtering rules**."
- Perimeter network: "To provide additional security to the Azure resources, a perimeter network **should be used for all high-security deployments**." _(Mod 12 p213)_

## Azure Firewall — creation walkthrough (click path as printed) _(Mod 12 pp213–215)_

1. "On the Azure homepage, click on **create a resource**." _(Mod 12 p213)_
2. "Type **Firewall** in the search box and press enter." _(Mod 12 p213)_
3. "To create a firewall, click on **Create**." _(Mod 12 p214)_
4. "Fill in the details and click on **Review + create**." _(Mod 12 p214)_
5. "After successful validation (**Validation passed**), click on **Create**." _(Mod 12 p214)_
6. "After deployment, click on **Go to resource**." _(Mod 12 p215)_
7. "Thus, the firewall is **created**." _(Mod 12 p215)_

Figures: 12.142 Search for "Firewall" (p213) · 12.143 Create a Firewall (p214) · 12.144 Fill
Details for Firewall (p214) · 12.145 Validation Passed to Create Firewall (p214) · 12.146
Deployment Finished (p215) · 12.147 Firewall Created (p215). Portal values in those figures are
screenshot-only — see `unresolved:`. Between steps 3 and 4 the printed text supplies **no** field
names.

## Stated rules — Azure Web Application Firewall _(Mod 12 p215)_

- "It **protects web applications from attacks and vulnerabilities**."
- "Various web applications are **increasingly targeted by cybercriminals by exploiting their vulnerabilities**."
- "A web application firewall (WAF) **on an application gateway** is based on the **Core Rule Set
  (CRS) 3.1, 3.0, or 2.2.9 from OWASP**."
- "WAFs are **automatically updated** to provide protection against new vulnerabilities."

## Stated rules — Network Security Groups _(Mod 12 p216)_

- "Network security group (NSGs) **contain rules that permit or deny network traffic**."
- "The **default NSG rules cannot be deleted, but they can be overruled by the customers**."
- "NSGs can be used to **control the inbound and outbound access to subnets, VMs, and network
  interfaces (NICs)**."
- "**An NSG can be applied to multiple subnets or VMs.**"

| Reading, precisely as printed | Objects named |
|---|---|
| NSGs are **used to control inbound + outbound access to** | subnets · VMs · **NICs** |
| **An NSG can be applied to** | multiple subnets · VMs (NICs **not** named here) |

One NSG = many subnets/VMs. The "applied to" sentence omits NICs even though the scope sentence
lists them — both readings kept, no repair.

## NSG — creation walkthrough (click path as printed) _(Mod 12 pp216–218)_

1. "On the Azure homepage, navigate to **Network security group**." _(Mod 12 p216)_
2. "Click on **Create network security group**." _(Mod 12 p216)_
3. "Fill in the details and click on **Review + create**." _(Mod 12 p216)_
4. "After validation, click on **Create**." _(Mod 12 p217)_
5. "After deployment, click on **Go to resource**." _(Mod 12 p217)_
6. "Navigate to **Inbound security rules**, and click on **Add**." _(Mod 12 p218)_
7. "Enter the details and **Save** to create an NSG." _(Mod 12 p218)_

Figures: 12.148 Create a Network Security Group (p216) · 12.149 Validation Passed to Create NSG
(p217) · 12.150 Deployment Finished (p217) · 12.151 See the Network Security Group (p217) ·
12.152 Fill the Details for "Inbound security rules" (p218). Legible blade labels only:
`Properties` · `Locks` · `Add` · `Add inbound security rule` (p218) — the rule form's fields did not
OCR. Rules are added under **Inbound security rules**; no outbound equivalent is walked through.

## Exam traps _(from the printed text only)_

- NSG default rules: **cannot be deleted** — but **can be overruled by the customer**. They are not
  immutable.
- Azure Firewall = **policy enforcement + allow/deny filtering**; WAF = **web app layer, OWASP CRS,
  auto-updated**. Different jobs.
- Perimeter network is stated as the control for **high-security deployments** — not as a default.
- NSGs are **stateful** and do allow/deny (stated in the best-practices half of this LO, see
  `[[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]`).







