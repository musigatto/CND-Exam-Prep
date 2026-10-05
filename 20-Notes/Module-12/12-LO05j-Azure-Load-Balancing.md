---
type: note
module: "12"
lo: "05"
tags: [concept, process, mod/12]
topic: "Azure load balancing — Application Gateway, Traffic Manager, Load Balancer"
exam_weight: unknown
status: done
unresolved:
  - "pp208-212 CONTRADICTION / naming: the courseware says 'external load balancer' and 'internal load balancer' throughout p208 ('create an external and/or internal load balancer'). The word 'public' is never used. Not rewritten."
  - "pp208-212 the courseware NEVER states a Layer 4 / Layer 7 distinction and never uses the words layer, OSI or protocol level for either Application Gateway or Load Balancer. The only protocol-level facts printed are that Application Gateway is an 'HTTP web traffic load balancer' (p208) and that the load balancer handles 'TCP/UDP-based protocols' (Fig 12.141, p212, screenshot). No layer classification is asserted."
  - "pp208-209 the Application Gateway walkthrough STOPS at 'Review + create' — no 'create', no 'Go to resource' step is printed for it, unlike the Load Balancer walkthrough on pp211-212. The completion of the Application Gateway deployment is not documented in this range."
  - "p209 Fig 12.136 prints 'T,er' and 'West US 2' / 'Standard V2'; the tier field label is garbled ('T,er') though the value 'Standard V2' is legible. Whether 'Standard V2' is a tier or a SKU label is not asserted."
  - "p211 Fig 12.139 shows a Load Balancer creation blade with tabs/items 'Frontend IP configuration', 'Inbound rule', 'Outbound rule', 'Backend pool', 'Health probe', 'Load balancing rule' and the label 'Add a backend pool'. None of these is referenced by any printed step in pp209-212; no values are printed for them."
  - "p212 Fig 12.141 resource names print as 'example269' and the deployment as 'Microsoft.LoadBalancer-20231018011208' with resource 'my@68S' / subscription id '62bOUOd.51d4-413-9dOd.ce2U4d5cb5f'. These are screenshot values, garbled in places, and are not defaults."
  - "p208 Azure Traffic Manager is described (DNS/user-location based global load balancing) but NO configuration walkthrough for it is printed anywhere in pp208-212."
---

[[MOC-Module-12]]

# Azure Load Balancing — Optimize Uptime and Performance (§12.05)

> Covers pp. 208–212: the load-balancing rules the courseware states (p208) · Application Gateway
> (pp208–209) · Load Balancer (pp209–212). Related:
> `[[12-LO05i-Azure-Inbound-Access-Control]]`, `[[12-LO04l-AWS-VPC-and-Network-Security]]`.

## Rules the courseware states _(Mod 12 p208, three as printed)_

1. "Use the **Azure Application Gateway** (HTTP web traffic load balancer) to implement
   **end-to-end SSL encryption and SSL termination at the gateway**."
2. "Use the **Azure Traffic Manager** to **load balance connections to the services based on the
   user locations**."
3. "Create an **external load balancer** to provide a **higher level of availability** or an
   **internal load balancer** to **distribute the incoming requests across multiple VMS**."

## Service roles _(Mod 12 p208)_

| Service | Role as printed |
|---|---|
| **Application Gateway** | "an **HTTP web traffic load balancer** … **relieves the web servers from the overhead encryption and decryption**, and ensures **unencrypted traffic flow to the back-end servers**" |
| **Traffic Manager** | "enables load balance connections to the services based on the **user locations**"; "**Global Load Balancing** enhances the performance because connectivity to the **nearest data center** is faster than that to the data center that is situated at a distant place" |
| **Load Balancer** | "The Azure portal can be used to create an **external and/or internal** load balancer, which helps in **distributing the incoming requests across multiple VMS** to provide a **higher level of availability**" |

## Application Gateway — walkthrough _(Mod 12 pp208–209)_

1. "On the Azure **homepage**, click on **Application Gateways**." _(Mod 12 p208)_
2. "Click on **create application gateway**." _(Mod 12 p209)_
3. "Fill in the details and click on **Review + create**." _(Mod 12 p209)_

Blade tabs visible in Fig 12.136 _(Mod 12 p209)_: **Basics · Frontends · Backends · Configuration · Review +
create**; fields *Subscription · Application gateway name · Region (`West US 2`) · Tier (`Standard
V2`) (label garbled)*. Fig 12.135 also shows a **Public / Private** column and
"No application gateways to display". The steps end at Review + create — see `unresolved:`.

## Load Balancer — walkthrough _(Mod 12 pp209–212)_

1. "On the Azure **homepage**, click on **Load balancers**." _(Mod 12 p209)_
2. "Click on **Create load balancer**." _(Mod 12 p210)_
3. "Fill in the details and click on **Review + create**." _(Mod 12 p210)_
4. "After validation, click on **create**." _(Mod 12 p211)_
5. "Click on **Go to resource**." _(Mod 12 p211)_
6. "Thus, a **load balancer is created**." _(Mod 12 p212)_

Blade items visible in the creation/deployment figures _(pp211–212)_: **Frontend IP configuration ·
Inbound rule · Outbound rule · Backend pool · Health probe · Load balancing rule · NAT rules ·
NAT (Public IP address · Inbound) · Overview · Access control (IAM) · Tags · Diagnose and solve
problems · Locks · Template · Diagnostic settings · Properties**. No values are printed for any of
them in the text; the screenshot blurb for Fig 12.141 says it "Balance[s] IPv4 and IPv6 addresses",
handles "TCP/UDP-based protocols … protocols used for voice and messaging", "improves application
uptime … traffic to healthy nodes" and provides network address translation (NAT).





