---
type: note
module: "12"
lo: "05"
tags: [bestpractice, policy, concept, mod/12]
topic: "Azure network security best practices and active geo-replication"
exam_weight: unknown
status: done
unresolved:
  - "p231 CONTRADICTION preserved, not repaired: the slide blurb says active geo-replication creates 'readable secondary copies of Windows Azure Storage in the same or different data center', while the body text on the same page says 'It is a feature of the Azure SQL Database that allows the creation of a readable secondary database on an SQL database server in the same or different region', and the walkthrough pp232-234 creates a SQL Database. Both readings kept."
  - "pp229-230 'Optimize Uptime and Performance' (load balancing) is a body heading on p230 but is NOT in the p229 slide list of nine best practices. Kept as a body-only item."
  - "p233 the geo-replication 'Create secondary' values (Region Central US · Database name · Secondary type Readable · Target server sqlex2 (Central US) · Elastic pool None · Pricing tier) are screenshot-only and are the lab's values, not defaults or required settings."
  - "p231 no limit other than 'Geo-replication supports four secondary databases that are used for read-only access queries' is printed. No replication mode, sync/async behaviour, latency or RPO figure is given anywhere in pp231-234."
  - "pp232-234 the walkthrough gives no step for granting read access on the secondary, for triggering a failover, or for removing a secondary. Failover is described only as a capability."
---

[[MOC-Module-12]]

# Azure Network Security Best Practices & Active Geo-Replication (§12.05)

> Covers pp. 229–234: Azure network security best practices (pp229–230) · Azure storage
> security — active geo-replication (pp231–234). Related:
> `[[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]`,
> `[[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]`.

## Best practices — the slide list, all nine as printed _(Mod 12 p229)_

1. Use **strong network controls**
2. **Logically segment subnets**
3. Adopt a **Zero-Trust approach**
4. **Control routing behaviour**
5. **Deploy perimeter networks** for security zones
6. **Avoid exposure to the internet with dedicated WAN links**
7. **Disable RDP/SSH access** to virtual machines
8. **Secure critical service resources** to only virtual networks
9. **Use virtual network appliances**

Body-only heading, not on the slide: **Optimize Uptime and Performance** _(Mod 12 p230)_.

## Best practices in detail

### Use strong network controls _(Mod 12 p229)_

- "To get **clear visibility** into the network and security of the network, **adopt a common set of
  management tools** for monitoring network and network security."
- "**Centralize the management of core network functions**, such as ExpressRoute, subnet
  provisioning, IP addressing, and virtual network, as well as the **governance of network security
  elements** such as subnet provisioning, IP addressing, Express route, and virtual network."

### Logically segment subnets _(Mod 12 p229)_

- "Create **network access controls between subnets**. Use **network security groups to protect
  Azure subnets against uninvited traffic**."
- "**Network security groups are simple, stateful packet inspection devices that create
  allow/deny rules for network traffic.**" → *stateful*, cf.
  `[[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]`.

### Adopt a Zero-Trust approach _(Mod 12 p229)_

- "Use **Azure AD Conditional Access** to resources based on **devices, identity, and network
  location** by applying the right access controls. It implements **automated access control
  decisions based on the required conditions**."
- "To **lock down inbound traffic to Azure VMs, use just-in-time VM access in Microsoft Defender
  for Cloud**. Doing this **reduces exposure to attacks on the VMs and provides easy access to
  connect to VMs when needed**." → cf. `[[12-LO05i-Azure-Inbound-Access-Control]]`,
  `[[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]`.

### Control routing behaviour _(Mod 12 pp229–230)_

- "**Even if the virtual machines are on different subnets, they can connect to other VMs on a
  similar virtual network.** To avoid this, **configure user-defined routes** when deploying a
  **security appliance for a virtual network**."
- → Different subnets alone are **not** an isolation boundary; user-defined routes + an appliance are.

### Use virtual network appliances _(Mod 12 p230)_

- Capabilities: "**firewalling, vulnerability management, application control, web filtering,
  antivirus, botnet protection, network-based anomaly detection, and intrusion
  detection/intrusion prevention**."
- "These are **delivered better by Azure network security appliances than by network-level
  controls**."

### Deploy perimeter networks for security zones _(Mod 12 p230)_

- "The perimeter network **adds an extra layer of protection between assets and the Internet**."
- "To strengthen network security and access control for Azure resources, **implement a perimeter
  network for all high-security deployments**."

### Avoid exposure to the internet with dedicated WAN links _(Mod 12 p230)_

- "Use **Azure ExpressRoute** for **cross-premises connectivity**."
- "ExpressRoute is a **dedicated WAN link between the Microsoft Exchange hosting provider and the
  on-premises location**."
- "It lets **connectivity providers establish a private connection** for the on-premises networks
  into the Microsoft cloud."
- "ExpressRoute enables the user to connect to services such as **Azure, Microsoft 365, and
  Dynamics 365**."

### Optimize Uptime and Performance _(Mod 12 p230, body heading)_

- "Use **load balancing to increase service availability and performance**."
- "Load balancing is the process of **distributing network traffic between servers that are part of
  a service**."
- "The load balancer's traffic distribution **improves availability** because when a web server
  goes down, it stops distributing traffic to that server and transfers it to the other server."
- "The performance also improves because the **processing, network, and memory overheads** for
  serving requests is **dispersed across all load-balanced servers**."

### Disable RDP/SSH access to virtual machines _(Mod 12 p230)_

- "Attackers can perform **brute-force attacks using RDP and SSH protocols**, to gain access to
  Azure virtual machines."
- "These protocols provide **remote management of VMs via the Internet**, but it is **preferable
  to disable this option**."

### Secure critical Azure service resources to only virtual networks _(Mod 12 p230)_

- "Secure critical Azure service resources to **only virtual machines** by using **Private
  endpoints**."
- "For accessing Azure PaaS Service via a private endpoint in the virtual network, use the **Azure
  private link**."
- "Internet access through a private endpoint **enhances security in the virtual network, thereby
  fully removing public Internet access to resources**."

## Active geo-replication — both readings preserved

| Source | Printed statement |
|---|---|
| Slide blurb _(Mod 12 p231)_ | "Use active geo-replication to create **readable secondary copies of Windows Azure Storage** in the same or different data center" |
| Body text _(Mod 12 p231)_ | "It is a **feature of the Azure SQL Database** that allows the creation of a **readable secondary database on an SQL database server** in the same or different region" |
| Walkthrough _(pp232–234)_ | creates an **SQL Database**, then `Settings > Geo-Replication` → **Create secondary** |

Recorded in `unresolved:` — the slide says Storage, the body and the walkthrough say SQL Database.
Nothing is rewritten.

### What active geo-replication does _(Mod 12 p231)_

- "**Business continuity strategy for the quick disaster recovery of individual databases during a
  regional disaster.**"
- "Geo-replication **supports four secondary databases** that are used for **read-only access
  queries**."
- "Geo-replication allows the application to **start failover to a secondary database**. After the
  failover, the **secondary database becomes the primary database with different connection
  endpoints**."

**Benefits of geo-replication** _(p231, three as printed)_

1. "Used in **disaster recovery**"
2. "Used in **database migration** to migrate databases from one server to another with **minimum
   downtime**"
3. "Used in **application upgrades as a failback copy**"

### Enabling active geo-replication — click path as printed _(Mod 12 pp232–234)_

1. "On the Azure homepage, click on **SQL databases**." _(Mod 12 p232)_
2. "In **Create SQL Database**, fill in the details and click on **Review + create**." _(Mod 12 p232)_
3. "After deployment, click on **Go to Resource**." _(Mod 12 p232)_
4. "In the **Settings** section, click on **Geo-Replication** to create a **readable secondary
   database**." _(Mod 12 p233)_
5. "Select **Target region** and fill in the details. Then, click on **Ok**." _(Mod 12 p233)_
6. "Thus, a **secondary database is created**." _(Mod 12 p234)_

Figures: 12.156 Navigate to "SQL databases" (p232) · 12.157 Create SQL Database (p232) · 12.158
Deployment Finished (p232) · 12.159 Create a Readable Secondary Database (p233) · 12.160 Fill the
Details for "Create secondary" (p233) · 12.161 Secondary Database Created (p234). The "Create
secondary" blade in Fig 12.160 is a real port of the text — see `unresolved:` for its values.







