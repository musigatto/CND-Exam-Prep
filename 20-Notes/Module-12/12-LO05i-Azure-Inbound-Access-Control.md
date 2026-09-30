---
type: note
module: "12"
lo: "05"
tags: [bestpractice, policy, mod/12, flashcard/12]
topic: "Azure inbound access control — SSL, endpoint ACLs, disabling RDP/SSH, VPN, ExpressRoute"
exam_weight: unknown
status: done
unresolved:
  - "p204 the PowerShell block OCRs EVERY hyphen as an em-dash and confuses lowercase l with the digit 1: 'New—AzureAc1Config', '—AddRu1e—ACL', 'user%l'. The commands are reproduced with hyphens but the ambiguous characters are kept as printed (New-AzureAc1Config, -AddRu1e); they are NOT normalised to the real cmdlet spellings. Likewise $ac11/$acll appear as $ac1l / $ac11 across the two renderings of the same page."
  - "p204 the p204 figure version of the endpoint-creation line prints as 'Get—AzureVM —ServiceName $serviceName —Name $vmName —Name \"web\" —Protocol tcp —- Publicport 80 -ACL $acll' while the body prints 'Get—AzureVM —ServiceName $serviceName —Name $vmName I Add—AzureEndpoint —Name \"web\" —Protocol tcp —Localport 80 80 -ACL $acll'. The body reading is used; the figure version is not asserted."
  - "pp204-205 Figures 12.133/12.134 are partially garbled. Readable column headers: Name, Protocol, Public port, Private port, Floating IP address, Access control list; a rule row 'myHTTP TCP 82 82 Disabled UDP *' on VM 'myServer'; ACL order values that OCR as '1001' and '200'; remote subnets 10.0.0.0/8, 0.0.0.0/0 and 10.1.0.0/8; action 'permit'. Which remote subnet belongs to which order value is NOT asserted."
  - "p206 the surrounding screenshot of TestVNet4 shows navigation labels only ('Connections', 'Point-to-site configuration', 'Site-to-site connection', 'Virtual Network Gateway', 'Point-to-site is not configured', 'ExpressRoute'). No configuration step is printed for any of them in this range."
  - "p207 CONTRADICTION / tension on ExpressRoute: it 'works like Site-to-Site VPN' and its dedicated WAN link 'does not go through the internet', yet it is said to offer 'faster speed, lower latency, and higher reliability than other **Internet** connections'. Both readings preserved; not reconciled."
  - "pp206-207 the three S2S VPN security benefits are announced on p206 ('Site-to-Site VPN provides the below security benefits') and printed on p207. No other S2S benefits are listed, and no quantitative or configuration detail is given for them."
  - "pp203-207 the courseware never states which ports (3389/22) are involved, and never states whether disabling RDP/SSH is enforced by a network security group, an Azure Bastion service or any other control. No such mechanism is asserted."
---

[[MOC-Module-12]]

# Azure Inbound Access Control (§12.05)

> Covers pp. 203–207: SSL for inbound internet communications to VMs (p203) · endpoint ACLs
> (pp204–205) · disabling RDP/SSH direct access (p206) · Site-to-Site VPN and ExpressRoute
> (pp206–207). ACL concepts: `[[03-LO01-Access-Control-Models]]`. Related:
> `[[12-LO05h-Azure-Encryption-in-Transit]]`, `[[12-LO05j-Azure-Load-Balancing]]`.

## Secure inbound internet communications to VMs using SSL _(Mod 12 p203)_

- Rule: "Implement **Secure Socket Layer (SSL) encryption** to secure data transfer." "SSL
  encryption is implemented for secured data transfer." _(p203)_

**Steps to configure SSL for applications** _(p203, four as printed)_

1. **Get an SSL certificate**
2. **Modify the service definition and configuration files**
3. **Upload a certificate**
4. **Connect to the role instance via HTTPS**

**Steps to configure SSL in Microsoft Azure** _(p203)_

1. "On the Azure portal, click on **All resources** and select the cloud service."
2. "Click on **Certificates**."
3. "Click on **Upload**."
4. "Provide the **File and Password**; click on **Upload** at the bottom of the data entry area."

## Configure endpoint Access Control Lists _(Mod 12 pp204–205)_

"In Microsoft Azure, the customers can **create and manage network ACLs for endpoints** with
**PowerShell or through the Management Portal**." _(p204)_

**Configure the endpoint ACL to** _(p204)_

- "**Restrict access on public endpoint IP addresses**"
- "**Restrict the traffic to specific IP address sources**"

### PowerShell — as printed _(Mod 12 p204)_

> Command glyphs reproduced as printed; hyphens normalised from em-dashes, ambiguous
> characters kept as OCR'd. See `unresolved:`.

```
$ac1l = New-AzureAc1Config
Set-AzureAc1Config -AddRu1e -ACL $ac1l -Order 100 -Action permit -RemoteSubnet "10.0.0.0/8"  -Description "SharePoint ACL config"
Set-AzureAc1Config -AddRu1e -ACL $ac1l -Order 200 -Action permit -RemoteSubnet "157.0.0.0/8" -Description "web frontend ACL config"
Get-AzureVM -ServiceName $serviceName -Name $vmName
Add-AzureEndpoint -Name "web" -Protocol tcp -Localport 80 -Publicport 80 -ACL $ac1l
Update-AzureVM
```

### Azure Management Portal — walkthrough _(Mod 12 pp204–205)_

"The portal can be used to **add, modify, or remove an ACL from an endpoint**." _(p204)_

1. "**Sign into the Azure portal**."
2. "Select **Virtual machines** and click on the **VM** that required to be configured."
3. "Select **Endpoints**."
4. "Use the rows in the list to **add, delete, or edit rules for an ACL and change their order**."
5. "Click on **Save**."

Endpoint/ACL grid columns visible _(p205, Figs 12.133–12.134)_: **Name · Protocol · Public port ·
Private port · Floating IP address · Access control list**; ACL rules carry an **order**, an
**action** (`permit`) and a **remote subnet** (`10.0.0.0/8`, `0.0.0.0/0`, `10.1.0.0/8`).

## Disable RDP/SSH direct access to VMs — why the courseware says it is a risk _(Mod 12 p206)_

"The remote desktop protocol (RDP) and secure shell (SSH) protocol help to **connect with Azure VMS
remotely**." _(p206)_

Risk chain, as printed:

1. "Using **RDP/SSH protocol over the internet** and adopting **brute-force techniques**, the
   attacker can **gain access to Azure VMs**."
2. "**If attackers access a VM**, then they could **use it as a launch point** to compromise other
   VMS on the virtual network or **attack network devices outside the Azure cloud**."
3. "Therefore, **disable RDP/SSH direct access to VMS over the internet**."

Replacement paths printed: "Cloud consumers can use other options such as **Point-to-Site VPN,
Site-to-Site VPN, and Express Route** to access VMS for remote management." _(p206)_

**Point-to-Site VPN** _(p206)_ — "a **remote access VPN client/server connection**" that lets
"**a single user/organization** connect to an Azure virtual network over the internet"; "**Initially,
establish the point-to-site connection. Later, the user who has connected to Azure virtual network
via Point-to-Site VPN can access Azure VMs**." Protocols printed: **SSTP (Secure Socket Tunneling
Protocol)**, **Open VPN Protocol**, **IKEv2 VPN**. Use cases: people connecting from remote
locations "like a conference and home"; "a **few clients** need to connect to a VNet".

**Site-to-Site VPN** _(p206)_ — "enables an **entire on-premises network** to access VMS on Azure
virtual network over the Internet. It allows the users/organizations to access Azure VMS **using the
RDP/SSH protocol instead of direct RDP/SSH access over the Internet**."

### Site-to-Site VPN — the three security benefits stated _(Mod 12 p207)_

| # | Benefit | Printed |
|---|---|---|
| 1 | **Secure Connectivity** | "provides secure connection for **all traffic that flows across it by encrypting it**. This helps to protect the traffic against **data modification and eavesdropping**." |
| 2 | **Simplified Network Architecture** | "simplifies the network architecture by **eliminating the need of converting internal IP addresses to external IP addresses**. Devices used inside an organization usually use internal IP addresses which are converted to external IP addresses to make them accessible from the Internet." |
| 3 | **Access Control** | "The administrator can **define access control rules in a simpler and secure way** … because **S2S VPN users are internal users** so traffic entering the VPN can be **blocked or denied** from accessing the resources." |

### ExpressRoute _(Mod 12 p207)_

- "ExpressRoute **works like Site-to-Site VPN**. Use a **dedicated WAN link** to get its
  functionality. This dedicated WAN link **does not go through the internet** and they are **stable
  and perform better than Site-to-Site VPN**."
- "Azure provides Express route service to let customers **exchange data between their on-premises or
  co-locating (shared) infrastructure and Azure data centers by creating private connections**."
- "It offers **faster speed, lower latency, and higher reliability** … as it does not use the
  Internet to connect to Azure data centers."
- "Organization can get **cost benefits** by using Express Route connections for transferring data
  between Azure and on-premises infrastructure."

## Cards

What the courseware says you must do to secure inbound internet communications to an Azure VM, and the four application-level steps
?
Implement SSL encryption to secure data transfer — get an SSL certificate, modify the service definition and configuration files, upload the certificate, then connect to the role instance via HTTPS

What an endpoint ACL in Azure is used for, and what the two tool options are
?
To restrict access on public endpoint IP addresses and restrict traffic to specific IP address sources — created and managed with PowerShell or through the Azure Management Portal (which can add, modify or remove an ACL on an endpoint)

The two-step risk the courseware gives for exposing RDP/SSH to the internet
?
An attacker using brute-force techniques over RDP/SSH over the internet can gain access to an Azure VM; once in, that VM becomes a launch point to compromise other VMs on the virtual network or attack network devices outside the Azure cloud

The three alternatives the courseware offers instead of direct RDP/SSH over the internet
?
Point-to-Site VPN, Site-to-Site VPN, and ExpressRoute — the protocols printed for Point-to-Site are SSTP, Open VPN and IKEv2

The three security benefits the courseware states for Site-to-Site VPN
?
Secure Connectivity — all traffic encrypted, protected against data modification and eavesdropping · Simplified Network Architecture — no internal-to-external IP address conversion · Access Control — rules defined simply because S2S VPN users are internal users

ExpressRoute versus Site-to-Site VPN as the courseware describes it
?
It works like Site-to-Site VPN but over a dedicated WAN link that does not go through the internet, so it is stable, faster, lower latency and more reliable, and it creates private connections between on-premises/co-located infrastructure and Azure data centers