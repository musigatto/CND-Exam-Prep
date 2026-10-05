---
type: note
module: "12"
lo: "04"
tags: [concept, policy, bestpractice, mod/12]
topic: "Amazon VPC security — security groups, NACLs, gateways, subnets, Direct Connect and GovCloud"
exam_weight: unknown
status: done
unresolved:
  - "p131: the security-group worked example says 'for a public web server, select HTTP or HTTPS and specify the value for Source as o.o.o.o/o'. The source CIDR is garbled and is NOT completed to any address here."
  - "p132: in 'Steps to Add Rules to Network ACLs' the sentence 'To use a protocol that is not listed, choose s.' ends in a garbled token. The intended NACL Type-list value is not readable and is not guessed."
  - "pp. 130-141: the courseware never states that security groups are STATEFUL. The only occurrence of the word in this range is 'stateless', applied to network ACLs on p136. The 'stateful vs stateless' contrast is therefore NOT asserted by this note."
  - "p130: the courseware note 'To connect to infrastructures in an EPAM network from AWS, submit a request to helpdesk; you will receive a VPN setup' refers to the courseware author's own employer network, not to AWS guidance. The p130 figure around it OCRs as 'Edit inbound rules / EPAM Cloud VPN / AWS Cloud' and is not used."
  - "p139 Table 12.2 ('Difference among EC2 Classic, EC2 VPC, Regular VPC'): only two value columns OCRed. The EC2-Classic column is missing entirely, and the p138/p139 table headers garble 'VPC' as 'wc'/'VC' and 'EC2-Classic' as 'EC2-CIassic'. Only the row labels and the two readable value sets are transcribed."
  - "p140: 'AWS Region', 'AWS Local zones' and 'AWS GovCloud' appear ONLY as unlabelled bullets on the 'Other AWS Network Security Measures' slide. pp. 140-141 contain no body text describing any of the three, so none is described here."
  - "p133 and p136 figures 12.69/12.70 ('Amazon Virtual Private Cloud Security' / 'Implementation of AWS Security Controls'): the component labels are legible but the addressing OCRs as '10000/16', '10010.0/24', '10.020.9'. No IP prefix from these figures is asserted."
---

[[MOC-Module-12]]

# AWS Network Security: VPC & Network Security Measures (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · VPC implementation (p130) · security
> groups, NACLs and instance security (pp131–132) · Amazon VPC security (pp133–137) · EC2-VPC
> vs EC2-Classic access control (pp138–139) · other network security measures (pp140–141).
> Covers pp. 130–141.

## Amazon VPC — implementation and features _(Mod 12 p130)_

- "**Amazon VPC provisions a logically isolated section of the AWS cloud** where users can
  launch AWS resources in a **virtual network defined by them**."
- "A VPC … can be implemented to define an **isolated network for each workload or
  organizational entity**."
- "It also provides **layer 3 (Network Layer IP routing) isolation from the internet**."

**Implementation objectives** _(Mod 12 p130)_

1. "Implement the VPC **dedicated to your AWS account** to define an **isolated network for
   each workload or organizational entity**."
2. "Use **AWS VPC security groups** and **network access control list (NACL)** features that
   enable **inbound and outbound filtering at the instance and subnet levels**."
3. "Use **Virtual Gateway (VGW)** where the Amazon VPC-based resources require **remote
   network connectivity**."

**VPC features** _(Mod 12 p130)_

1. "Create an Amazon VPC on the AWS scalable infrastructure and **specify its private IP
   address range from any selected range**."
2. "Expand your VPC by adding **secondary IP ranges**."
3. "**Attach one or more Amazon Elastic IP addresses** to any instance in your VPC such that
   it can be reached directly from the internet."
4. "Enable **EC2 instances in the EC2-Classic platform** to communicate with instances in a
   VPC using **private IP addresses**."
5. "**Enable both IPv4 and IPv6** in your VPC."
6. "Use **Amazon VPC traffic mirroring** to capture and mirror network traffic for Amazon EC2
   instances."
7. "**Control inbound and outbound access** to and from **individual subnets** using **network
   access control lists**."
8. "**Associate VPC Security Groups with instances on EC2-Classic.**"

## Security groups and instance security _(Mod 12 p131)_

- "AWS VPC security groups (SGs) enable **inbound and outbound filtering at the instance and
  subnet levels**."
- "**Unlike NACLs, there is no "Deny" rule** in security groups. **A data packet will be
  dropped if there is no rule that explicitly permits it.**" â† *implicit-deny, no explicit deny*
- "Security groups can be used to **restrict access at the protocol and port level**, and
  implement the **rule of least privilege** when designing and implementing user rules … to
  avoid security breaches."
- "The default rule of a security group that filters traffic is defined in **two tables:
  Inbound and Outbound**."
- "**Each rule is comprised of five fields: Type, Protocol, Port Range, Source, and
  Description.** This applies to both Inbound and Outbound rules."

**Walkthrough — create a security group** _(Mod 12 p131)_
1. Open the **Amazon VPC console**.
2. "In the navigation pane, select **Security Groups**, followed by **Create Security
   Group**."
3. "Enter **security group name** (for example, `my-security-group`) and provide a
   description."
4. "Select the **ID of your VPC** from the VPC menu" → select **Yes, Create**.

**Walkthrough — add rules** _(p131, Fig 12.68 "Viewing Security Group Rules")_
1. Open the Amazon VPC console → **Security Groups** in the navigation pane.
2. "Select the **security group to update**."
3. "Select **Actions, Edit inbound rules** or **Actions, Edit outbound rules**."
4. "For **Type**, select the traffic type, and then fill in the required information." (public
   web server example: select **HTTP** or **HTTPS** and specify **Source** — value garbled,
   see `unresolved:`).
5. Inbound-rule example as printed: **Type: All Traffic** · **Source: Enter the ID of the
   security group** → **Save rules**.

## Network ACLs and instance security _(Mod 12 pp131–132, 136)_

- "AWS **network access control list (NACL) acts as a firewall** for controlling inbound and
  outbound traffic."
- "NACLs can be set up with rules, **like a security group**, to add an **additional layer of
  security** to the VPC."
- "Rules can be added or removed from the **default NACL** or additional network ACLs … The
  changes are **automatically applied to the associated subnets**."
- "ACL are considered as **stateless traffic filters** that are implemented on **inbound and
  outbound traffic subnets** in Amazon VPC." _(Mod 12 p136)_
- "They can command orders to **allow and restrict traffic based on the IP protocol, by
  service port, and source/destination IP address**."
- "Network ACLs are **controlled or managed through Amazon VPC APIs** like security groups …
  enable additional security via the **separation of duties**." _(Mod 12 p136)_
- "Application of **per-instance filters with host-based firewalls** like the **Windows
  Firewall** or **iptables** is encouraged by AWS." _(Mod 12 p136)_

**Walkthrough — create a network ACL** _(Mod 12 p132)_
1. Open the Amazon VPC console.
2. "Select **Network ACLs** in the navigation pane" → **Create Network ACL**.
3. "In the **Create Network ACL** dialog box, **name network ACL**, and select the **ID of your
   VPC** from the VPC list." → **Yes, Create**.

**Walkthrough — add rules to a network ACL** _(Mod 12 p132)_
1. Open the console → **Network ACLs** in the navigation pane.
2. "In the details pane, select either the **Inbound Rules** or **Outbound Rules** tab … and
   then choose **Edit**."
3. "In **Rule #**, enter a rule number (for example, **100**)."
4. "Select a rule from the **Type** list" — e.g. **HTTP**; "to allow all TCP traffic, choose
   **All TCP**" (unlisted protocol: value garbled, see `unresolved:`).
5. "In the **Source or Destination** field, enter the **CIDR range** that the rule applies to."
6. "From the **Allow/Deny list**, select **ALLOW** … or **DENY**."
7. **Save**.

**SG vs NACL — what the courseware actually states** _(pp131–132, 136)_

| | **Security group** | **Network ACL** |
|---|---|---|
| Explicit **deny** rule? | **No** — "there is no "Deny" rule" | **Yes** — Allow/Deny list |
| Unmatched packet | "**dropped** if there is no rule that explicitly permits it" | Rules are evaluated by **rule number** (e.g. 100) |
| State | *(not stated in this range)* | "**stateless** traffic filters" |
| Applied to | "**instance and subnet levels**" | "**inbound and outbound traffic subnets**"; changes **automatically applied to associated subnets** |
| Match fields | Type · Protocol · Port Range · **Source** · Description | **IP protocol** · service port · source/destination IP · CIDR |
| Managed via | Amazon VPC APIs | Amazon VPC APIs |
| Extra | "implement the **rule of least privilege**" | "an **additional layer of security**" + separation of duties |

## Amazon VPC security _(Mod 12 pp133–137)_

- "Amazon VPC … create[s] an **isolated portion of the AWS cloud**. It enables customers to
  launch Amazon EC2 instances that have **private addresses in the range of their choice**."
  _(Mod 12 p133)_
- "**Network traffic within every Amazon VPC is completely isolated from all other Amazon
  VPCs**." _(p133, p135)_
- "A **public IP address is randomly assigned** in the Amazon EC2 instance while it is
  launched." _(Mod 12 p133)_
- "Customers can **define subnets** within their VPC by **grouping similar types of instances
  based on the range of IP addresses** and set **routing and security controls** for in and
  out traffic flow of subnet and instance." _(Mod 12 p133)_
- "Customers can select an **IP address range** for their Amazon VPCs **at the time of
  creating it**." _(Mod 12 p135)_
- "The security features in an Amazon VPC are **security groups, routing tables, external
  gateways, and network ACLs**." _(Mod 12 p133)_
- "Customers **should create VPC security groups** for their Amazon VPCs because **Amazon EC2
  security groups would not work inside Amazon VPC**. In addition, Amazon VPC security groups
  contain **additional capabilities** that Amazon EC2 security [groups] do not possess: the
  ability to **change the security groups after the launch of the instance** and the ability
  to **specify any protocol with a standard protocol number**." _(Mod 12 p135)_
- "Amazon EC2 instance in an Amazon VPC **inherits the benefits of the guest's OS and
  prevents packet sniffing**." _(Mod 12 p135)_

### VPC architecture templates — levels of public access _(Mod 12 pp133–134)_

| Template | Courseware description |
|---|---|
| **VPC with only a single public subnet** | "Instances run in an **isolated, private section** of the AWS cloud having **direct access to the internet**. To have **strict control** over inbound and outbound network traffic to the instances, customers can use **security groups and network ACLs**." |
| **VPC with public and private subnets** | "Contains a **public subnet and a private subnet**. Instances in the private subnet **cannot be addressed from the internet** but can use **network address translation (NAT)** to establish **outbound** connection to the internet through a public subnet." |
| **VPC with public and private subnets + hardware VPN access** | "An **IPsec VPN connection** is added between an Amazon VPC and the data center … extends the cloud data centers and establishes **direct access to the internet** for an Amazon VPC in a public subnets instance. Customers can **add a VPN appliance** on their corporate data center side." |
| **VPC with private subnet only + hardware VPN access** | "Instances run in a **private, isolated portion** … **not addressable from the internet**. Customers can connect their corporate data center with the private subnet through an **IPsec tunnel**." |

External connectivity: "Enables customers to establish external connectivity by **creating and
attaching a virtual private gateway, an internet gateway, or both**." _(Mod 12 p133)_

### VPC peering _(Mod 12 p135)_

- "It **connects two VPCs through a private IP address** to establish a **communication
  instance in the same network**."
- "Customers can generate a **VPC peering connection** with each other or other present VPCs
  **from another AWS account of the same region**."

### The AWS VPC security controls _(Mod 12 pp133, 135–137)_

**API access** _(Mod 12 p135)_

- "Calls to **change routing**, to **create and delete Amazon VPCs, security groups, network
  ACL parameters** … are **signed by the Amazon Secret Key**, which **either user or AWS can
  create**."
- "Amazon VPC API are **not allowed to make calls on behalf of customers without access to
  their Secret Access Key**."
- "**SSL** can be used to encrypt API calls to maintain confidentiality. The use of
  **SSL-protected API endpoints is recommended by Amazon**."
- "Customers can further control **what APIs can be called by a newly created user** through
  **AWS IAM**."

**Subnets and route tables** _(Mod 12 p135)_

- "Customers create **one or more subnets** … every instance gets connected to a subnet when
  it is launched."
- "Traditional security attacks of **Layer-2 such as ARP spoofing and MAC spoofing are
  blocked**."
- "Every subnet is connected with a **routing table** that processes network traffic, leaving
  subnets to detect their destination."

**Firewall (security groups)** _(Mod 12 p135)_

- "Amazon VPC offers a **complete firewall solution, like Amazon EC2**, through **egress and
  ingress traffic filtration** from an instance."
- "The **default group** establishes **outbound communication to any destination** and
  **inbound communication from members of the same group**."
- "Traffic can be restricted or controlled by **service port, any protocol, and
  source/destination IP address**."
- "The **guest OS cannot control the firewall** but can **modify it by applying Amazon VPC
  APIs**." → "AWS offers customers **partial access** to the different administrative
  functions on instance and firewall … to implement extra security by **separating duties**."

**Virtual Private Gateway (VPG)** _(Mod 12 p136)_

- "**Private connections** can be established between an Amazon VPC and another network
  through a private connectivity established by the **virtual private gateway**."
- "The **network traffic isolation for every VPG** is established from the network traffic
  within **all other VPGs**."
- "Customers can create **VPN connections from gateway devices at their premises to the
  VPG**."
- "A **pre-shared key** in conjunction with the **customer gateway device's IP address** is
  used to **secure each connection**."

**Internet Gateway** _(Mod 12 p137)_

- "To enable **direct connectivity with the internet, Amazon S3, and other AWS services**, an
  **internet gateway** can be attached to an Amazon VPC."
- "Every instance that wants this access needs to either **associate itself with an Elastic
  IP** or **route traffic through a NAT instance**."
- "AWS also provides **NAT AMI references** that customer can extend to perform **deep packet
  inspection, application-layer filtering, network logging**, or other security controls."
- "**Modification to this access can only be applied by calling Amazon VPC APIs.**"
- "To make instances in a **private subnet connect** to other AWS services and the internet
  but **restrict the internet from initiating a connection** with them, customers can use a
  **NAT gateway**."

**Dedicated Instances** _(Mod 12 p137)_

- "Customers are allowed to launch an Amazon EC2 instance with a **high level of physical
  isolation (which works on single-tenant hardware)** within an Amazon VPC."
- "AWS allows the creation of an Amazon VPC with a **dedicated tenancy** to ensure all
  instances launched in that VPC use this feature."
- "Similarly, customers can create an Amazon VPC with **default tenancy** but specify
  **dedicated instances** for specific instances launched in it."

**Elastic Network Interfaces (ENI)** _(Mod 12 p137)_

- "A **default network interface** is present in each Amazon EC2 instance assigned with a
  private IP address on the Amazon VPC network."
- "Customers are allowed to generate and attach an **elastic network interface** … but
  **only two interfaces can be attached per instance**."
- Use cases: "using **security and network appliances**", "create a **management network**",
  "create **dual-homed instances** with roles/workloads on different subnets".
- "Attributes of a network interface such as the **private IP address, MAC address, and
  elastic IP addresses follow the network interface** because it is attached or detached from
  an EC2 instance and **reattached to another EC2 instance**."

## EC2-VPC vs EC2-Classic access control _(Mod 12 pp138–139)_

- "When the customer creates their AWS account, a **default VPC will be created for the
  customer in every region** … configured already for customers to use. Customers can create
  their own **nondefault VPC** … or launch their instances immediately into their default
  VPC." _(Mod 12 p138)_
- "All instances will be provisioned automatically in a **ready-to-use default VPC** when a
  customer launch instances in a region where there are **no instances** before the launch of
  the new AWS EC2-VPC feature." _(Mod 12 p138)_
- "**Security groups for instances in EC2-VPC are different from the security groups for
  instances in EC2-Classic.**" _(Mod 12 p138)_

**Table 12.2 — difference among EC2 Classic, EC2 VPC and Regular VPC** _(Mod 12 p139; the
EC2-Classic column did not OCR — see `unresolved:`)_

| Characteristic | EC2-VPC (Default VPC) | Regular VPC |
|---|---|---|
| **Private IP address** | "Default IP address until specified by the user otherwise during its launch" · "The instance gets a **static private IP address** from your **default VPC's** address range" | "Unless the user specifies otherwise during its launch" · "The instance gets a **static private IP address** from the **VPC's** address range" |
| **Multiple private IP addresses** | "Users can assign multiple IP addresses to their instances" | "Users can assign multiple IP addresses to their instances" |
| **Elastic IP address** | "When the user stops their instance, the **EIP remains associated** with the instance" | "When the user stops their instance, the **EIP remains associated** with the instance" |
| **DNS hostnames** | "**by default enabled**" | "**by default enabled**" |
| **Security group** | "A security group can reference other security [groups] for the user's **VPC only**" | "A security group can reference other security [groups] for the user's **VPC only**" |
| **Security group association** | "The user **can change the security group of their running instance**" | "The user **can change the security group of their running instance**" |
| **Security group rules** | "The user can add rules for **both inbound traffic and outbound traffic**" | "The user can add rules for **both inbound traffic and outbound traffic**" |
| **Tenancy** | "The user can run the instance on **single-tenant hardware or shared hardware**" | "The user can run the instance on **single-tenant hardware or shared hardware**" |

## Other AWS network security measures _(Mod 12 pp140–141)_

**Slide headings** _(Mod 12 p140)_: AWS Region · AWS Local zones · AWS GovCloud · **Use AWS Direct
Connect to establish a dedicated network connection from your premises to AWS** · **Use DMZs** ·
Isolate resources with subnets, firewalls, and routing tables · Secure DNS configurations ·
Limit in/outbound traffic · Secure accidental exposures.
*(Only the four bolded items receive body treatment on pp. 140–141; see `unresolved:`.)*

### AWS Direct Connect _(Mod 12 p140)_

"Use the cloud service solution AWS Direct Connect to **establish a dedicated network
connection from your premises to AWS**."

| # | Feature and benefit, as printed |
|---|---|
| 1 | "Allows establishing **private connectivity** to your Amazon VPC that provides a **private, high bandwidth** network connection between your network and VPC. **Compatible with all AWS services** such as Amazon S3, Amazon EC2, and Amazon VPC." |
| 2 | "**Reduces bandwidth costs** if you have bandwidth-heavy workloads that you wish to run on AWS." |
| 3 | "**Consistent network performance** that allows to select the data that utilize the dedicated connection as well as the data routing process." |
| 4 | "Provides **1 and 10 Gbps connections**, and enables the **easy provision of multiple connections** if more capacity is required." |
| 5 | "AWS Direct Connect **can be used instead of establishing a VPN connection over the internet** to your Amazon VPCs." |
| 6 | "Provides a **single view in its console** to efficiently manage all your connections and virtual interfaces." |

### DMZ and resource isolation _(Mod 12 p141)_

- **DMZ** — "Use a **demilitarized zone (DMZ)** that exposes the **external services** of an
  organization to an **untrusted network such as the internet**. It can add an **extra layer
  of security** to the **local area network (LAN)** of an organization."
- **Isolate resources with:**
  - **Subnet** — "a main part of VPC, which can be configured as a **VPN-only subnet**. VPC
    can comprise **all public subnets or public/private subnet combinations**. Here, a
    **private subnet does not have a route to the internet gateway**."
  - **Firewalls** — "**protect web-based applications** running on the Amazon cloud and ensure
    traffic filtering by providing **defense against cloud-based exploits**."
  - **Routing tables** — "with rules/routes allow users to **determine the direction of network
    traffic** from a subnet/gateway."
- **Secure DNS configurations** — "Use DNS services such as **Amazon Route 53** … by
  **translating domain names into numeric IP addresses**."
- **Limit inbound/outbound traffic** — "AWS enables the control of inbound/outbound VPC
  network traffic to **differentiate between legitimate and illegitimate requests**."
- **Secure accidental exposures** — "Secure buckets and objects with services such as
  **Amazon S3 Block Public Access** to secure against accidental exposures."

Segmentation theory: [[03-LO06-Network-Segmentation]] · storage side of S3:
[[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]







