---

type: question
module: "ext"
tags: [exam, flashcard]
topic: "CND study deck - 239 cards verified against the 20 module PDFs"
exam_weight: unknown
status: done
unresolved: []
---
# CND - Verified Study Deck

> [!info] What this is
> **239 cards, every one matched to the 20 module PDFs.** Each carries its source as
> `_(Mod NN pNN)_`, so you can always check it against the courseware.
> Your original Quizlet export had 264: the 19 that did not fully verify and the 6
> that were dropped are in [[External-Flashcards-Verification]].

> [!warning] Read before drilling
> Source was your own Quizlet export (set `617277655`), **not** official courseware, so
> it lives here and not in `20-Notes/`. This note is the whole drillable deck - nothing
> unverified is in it.
> One fix was applied to the export: card 9's answer said "Pretty Good Service" where
> the courseware says "Pretty Good **Privacy**".
>
> Card 1 is the one oddity: the export stored an MCQ as the answer with the question as
> the term, and the answer text is just the four options. The useful fact is on
> `Mod 03 p113`: a low-interaction honeypot fakes the services the attacker most
> often asks for.

## Deck

Low-interaction Honeypot
?
From the following, identify the type of honeypot which generally fakes those services that are frequently asked by the attacker. They are essentially a single machine with multiple virtual machines. Low-interaction Honeypot Pure Honeypot High-interaction Honeypot Production Honeypot  _(Mod 03 p113)_

Public key infrastructure
?
is treated as the most effective method for providing verification during electronic transactions  _(Mod 03 p82)_

Secure Hashing Algorithm (SHA)
?
generate a cryptographically one-way hash and is published by NIST as a Federal Information Standard  _(Mod 03 p94)_

Digital Signature Algorithm
?
It is a Federal Information Processing Standard (FIPS) for digital signatures.  _(Mod 03 p90)_

AES
?
is a National Institute of Standards and Technology (NIST) specification for the encryption of electronic data and is being used by U.S. government agencies to secure sensitive but unclassified material  _(Mod 03 p87)_

SSL
?
Secure Sockets Layer (SSL) works at the transport layer.  _(Mod 03 p139)_

IPSec
?
Internet Protocol Security (IPSec) works at the network layer  _(Mod 03 p139)_

PGP
?
Pretty Good Privacy (PGP) protocol works at the application layer.  _(Mod 03 p139)_

S/MIME
?
Secure/Multi-Purpose Internet mail Extension (S/MIME) works at the application layer  _(Mod 03 p139)_

Network Address Translation (NAT)
?
firewall technology helps hide the internal network's configuration and thereby reduces the success of attacks on the network or system. It can act as a firewall filtering technique where it allows only those connections that originate inside a network and can block the connections that originate outside the network.  _(Mod 04 p23)_

Application-level gateway
?
is a firewall that controls input, output, and/or access across an application or service. It monitors and possibly blocks the input, output, or system service calls, which do not meet the policy of the firewall.  _(Mod 04 p17)_

Application proxy
?
An application-level proxy works as a proxy server. It correlates with the gateway server and separates the enterprise network from the Internet.  _(Mod 04 p20)_

Stateful multi-layer inspection
?
These firewalls filter packets at the network layer, determine whether session packets are legitimate, and evaluate the contents of packets at the application layer.  _(Mod 04 p19)_

Firewalk
?
is used for reconnaissance purpose where it discovers firewall rules using an IP TTL expiration technique.  _(Mod 04 p62)_

Security Reference Monitor (SRM)
?
enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.  _(Mod 05 p17)_

Local Security Authority Subsystem (LSASS)
?
implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.  _(Mod 05 p19)_

Security Accounts Manager (SAM)
?
is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.  _(Mod 05 p21)_

Windows Integrity Control (WIC)
?
is an access control mechanism for controlling the interactions between objects based on their integrity or level of trustworthiness.  _(Mod 05 p41)_

User Account Control (UAC)
?
is a key access control enforcement feature in Windows that improves the security of the OS by limiting application software to standard user privileges until an administrator authorizes an elevation  _(Mod 05 p98)_

Network logon service (NetLogon)
?
a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.  _(Mod 05 p30)_

Windows logon application (WinLogon)
?
used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background  _(Mod 05 p27)_

Just Enough administration (JEA)
?
a security technology used to limit the number of cmdlets or administration privileges of administrator, user, or service accounts.  _(Mod 05 p106)_

SID
?
To troubleshoot user or object access issues across the domain system, the administrator needs to view the SID of users or group.  _(Mod 05 p39)_

RID
?
Every SID contains a relative identifier (RID) at the end, and attackers try to access the list of SIDs to try and replace the RID with an administrative account's details so that they can get access to administrative privileges.  _(Mod 05 p100)_

Microsoft Windows Defender Credential Guard (WDCG)
?
protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.  _(Mod 05 p81)_

CPs
?
a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.  _(Mod 05 p29)_

Network Level Authentication (NLA)
?
s implemented to send the user credentials securely from the client side using a security service provider of the client and make the user to authenticate before the session gets started.  _(Mod 05 p219)_

Enabling Remote Credential Guard
?
If Remote Credential Guard is enabled, the connection to the other systems using single sign-on will be active only when the host supports it.  _(Mod 05 p221)_

sudo apt autoclean
?
clean partial packages  _(Mod 06 p24)_

sudo apt-get clean
?
This command cleans the apt cache  _(Mod 06 p24)_

sudo apt autoremove application-name
?
uninstalls or removes unnecessary packages  _(Mod 06 p24)_

NIS-Server
?
The NIS-Server tends to distribute system configuration files. Also, it is an insecure system that has been vulnerable to DoS attacks, buffer overflows and poor authentication for querying NIS maps.  _(Mod 06 p22)_

Telnet-Server
?
It comprises the telnetd daemon, which allows connections from users from other systems through the telnet protocol. The insecure and unencrypted telnet protocol could allow access to sniff network traffic, which can steal the credentials.  _(Mod 06 p22)_

RSH-Server
?
The Berkeley rsh-server (rsh, rlogin, rcp) package comprises legacy services that exchange credentials in clear-text. This service comprises many security exposures that can be exploited.  _(Mod 06 p22)_

TFTP-Server
?
The file transfer protocol 'Trivial File Transfer Protocol (TFTP)' is used to transfer configuration or boot machines from a boot server automatically. It does not support authentication and ensure the confidentiality of data integrity.  _(Mod 06 p22)_

rwxrwxrwx
?
no restrictions on anything. Anybody can do anything  _(Mod 06 p75)_

rw-rw-rw
?
All users can read and write the file  _(Mod 06 p75)_

rw-r--r--
?
The owner can read and write a file, while others may only read the file. A very common setting where everybody may read but only the owner can make changes.  _(Mod 06 p75)_

rw-------
?
Owner can read and write a file. Others have no rights. A common setting for files that the owner wants to keep private.  _(Mod 06 p75)_

rwx------
?
The file owner may read, write, and execute the file. Nobody else has any rights. This setting is useful for programs that only user may use and are kept private from others.  _(Mod 06 p75)_

rwxr-xr-x
?
The file owner may read, write, and execute the file. Others can read and execute the file. This setting is useful for all programs that are used by all users.  _(Mod 06 p75)_

iptables -A INPUT -p icmp -i eth0 -j DROP
?
blocks incoming ping requests  _(Mod 06 p94)_

iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP
?
This command will block XMAS scan attack  _(Mod 06 p91)_

ptables -A INPUT -i eth0 -s xxx.xxx.xxx.xxx -j DROP
?
block connection on network interface  _(Mod 06 p91)_

Lynis
?
Lynis can perform an extensive health scan of systems to support system hardening and compliance testing.  _(Mod 06 p114)_

AppArmor
?
Linux security module that allows a system administrator to restrict programs' capabilities with per-program profiles. It is utilized by the system administrator to restrict programs to a limited set of resources.  _(Mod 06 p115)_

SELinux
?
It is a mandatory access control (MAC) module that resides in the kernel level of Linux systems. It decides which process can access which files, directories and ports and provides an additional layer of system security.  _(Mod 06 p116)_

CYOD policy
?
The CYOD policy allows employees to choose devices (laptops, smartphones, and tablets) from a preapproved set of devices to access company data as per the organization's access privileges.  _(Mod 07 p11)_

BYOD policy
?
The BYOD policy allows employees to use the devices that they are comfortable with and best fits their preferences and work purposes.  _(Mod 07 p6)_

COBO policy
?
The COBO policy allows employees to use and manage devices purchased by the organization but restricts the use of the device for business use only.  _(Mod 07 p19)_

COPE policy
?
The COPE policy allows employees to use and manage devices purchased by the organizations. Larger enterprises are more likely to employ the COPE model. COPE reduces the risks associated with BYOD by implementing stringent policies and protecting devices.  _(Mod 07 p15)_

MEM
?
An MEM solution ensures the security of the corporate email infrastructure and data on mobile devices.  _(Mod 07 p45)_

MDM
?
An MDM solution is used to deploy, secure, monitor, and manage company-owned and employee-owned devices.  _(Mod 07 p30)_

UEM
?
An UEM solution helps in managing and controlling internet-enabled mobile devices, desktops, applications, and content across the organization from a single interface.  _(Mod 07 p51)_

MAM
?
An MAM solution enables an organization to secure, manage, and distribute enterprise applications on user mobile devices, without interfering with personal apps and data.  _(Mod 07 p38)_

Data leaks identification
?
MTD solutions can be used by admins to identify data leaks to block access to the risky content.  _(Mod 07 p43)_

Location-based content delivery
?
MCM solutions are used by admins for location-based content delivery.  _(Mod 07 p40)_

App wrapping
?
MAM solutions are used by admins for app wrapping.  _(Mod 07 p39)_

IoT User applications
?
These applications help change the behavior of the application controls.  _(Mod 08 p13)_

IoT Control applications
?
Control applications send automatic commands and alerts to actuators and helps in investigating problematic cases and enhancing security by identifying security breaches.  _(Mod 08 p12)_

IoT Gateways
?
Gateways are devices through which data are transmitted from things to the cloud and vice versa.  _(Mod 08 p11)_

IoT Streaming data processors
?
These processors ensure that no data can be lost or corrupted  _(Mod 08 p11)_

IoT Cloud layer
?
his layer consists of servers hosted in the cloud that accept, store, and process the sensor data received from IoT gateways.  _(Mod 08 p15)_

IoT Communication layer
?
The communication layer includes the components of communication protocols and networks used for connectivity and edge computing.  _(Mod 08 p14)_

IoT Device Layer
?
The device or the Thing layer of IoT includes the hardware that constitutes IoT devices.  _(Mod 08 p14)_

IoT Process Layer
?
The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.  _(Mod 08 p15)_

Installing an IoT firewall
?
will mitigate malicious scripts attack  _(Mod 08 p67)_

Implementing a strong IoT encryption scheme
?
prevents attacks like cryptanalysis attacks  _(Mod 08 p67)_

implementing high data privacy and privilege levels for IoT
?
prevents social engineering attacks.  _(Mod 08 p40)_

Device-to-Device model
?
In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.  _(Mod 08 p16)_

Device-to-Cloud model
?
In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.  _(Mod 08 p17)_

Cloud-to-Cloud model
?
his type of communication model extends the device-to-cloud communication type in which the data from IoT devices can be accessed by authorized third parties. Here, devices upload their data onto the cloud, and the data is accessed or analyzed later by third parties.  _(Mod 08 p18)_

Device-to-Gateway model
?
In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.  _(Mod 08 p17)_

Monitoring bandwidth consumption of IoT devices
?
Monitoring bandwidth consumption helps to know how much data is used or sent by IoT device, and to know the download and upload bandwidth consumption of devices in the IoT network.  _(Mod 08 p108)_

Implementing end-to-end (E2E) security and identity management
?
It will provide security and privacy in the IoT device and to maintain trust.  _(Mod 08 p90)_

Constructing virtual LAN pipe
?
Virtual LAN pipe should be constructed on the fly with each new IoT device connection that would allow IP-based communication to only one endpoint - the publicly facing internet  _(Mod 08 p78)_

Monitoring the behaviour of IoT device
?
Monitoring the behaviour of the IoT device provides full visibility and insights of the IoT assets, so that the organization can quickly react to mitigate the risks and resolve an issue before it impact the business.  _(Mod 08 p75)_

Domotz
?
It is an IoT monitoring and management tool.  _(Mod 08 p75)_

SeaCat.io
?
It is a security-first SaaS technology to operate IoT products in a reliable, scalable and secure manner.  _(Mod 08 p115)_

DigiCert IoT Security Solutions
?
It protect private data and home networks while preventing unauthorized access using PKI-based security solutions for consumer IoT devices.  _(Mod 08 p116)_

beSTORM
?
It is an IoT vulnerability scanning tool  _(Mod 08 p85)_

GSMA
?
GSMA developed IoT Security Guidelines and IoT Security Assessment that help create a secure IoT market with trusted, reliable services that can scale as the market grows.  _(Mod 08 p132)_

AT&T
?
AT&T developed The CEO's Guide to Securing the Internet of Things  _(Mod 08 p135)_

U.S Department of Homeland Security
?
U.S DHS developed Strategic Principles for Securing the Internet of Things.  _(Mod 08 p128)_

ENISA
?
ENISA developed 'Baseline Security Recommendations for Internet of Things  _(Mod 08 p135)_

dm-crypt
?
dm-crypt is a transparent disk encryption subsystem in Linux kernel versions 2.6 and later. This command is used for disk encryption in Linux.  _(Mod 10 p37)_

JTAG
?
It is a standard interface to test and debug chips with debugging software to know how a chip respond to multiple commands.  _(Mod 08 p31)_

Application Whitelisting
?
The approach of application whitelisting is trust centric. By default, applications that are not in the whitelist are prevented from being executed.  _(Mod 09 p10)_

Application Blacklisting
?
Application blacklisting is threat centric. By default, it allows all applications that are not in the blacklist to be executed.  _(Mod 09 p13)_

Application Sandboxing
?
Application sandboxing is the process of running applications in a sealed container (sandbox) so that the applications cannot access critical system resources and other programs.  _(Mod 09 p47)_

Application Patch Management
?
Application patch management is the process of ensuring the security of applications on hosts by regularly deploying new or missing patches.  _(Mod 09 p68)_

AppLocker
?
When AppLocker rules are enforced, apps excluded from the list of allowed apps are prevented from running.  _(Mod 09 p24)_

Group Policy Settings
?
Group Policy Settings can enable blocking software installation.  _(Mod 09 p36)_

Registry Editor
?
Network defenders can block the execution of an application on a system by disabling the application using the Windows Registry Editor.  _(Mod 09 p39)_

Windows Defender Application Guard
?
Windows Defender Application Guard (WDAG) isolates Microsoft Edge and blocks websites from accessing the local storage, memory, installed apps, and corporate network endpoints.  _(Mod 09 p61)_

Sandbox for FireFox
?
Content Process Sandbox Level  _(Mod 09 p52)_

Sandbox for Chrome
?
Strict-Origin-Isolation  _(Mod 09 p50)_

Toggling feature controls of Sandbox Protections
?
Used for Acrobat Reader  _(Mod 09 p53)_

Microsoft URLScan
?
is a WAF tool that analyzes and filters all Hypertext Transfer Protocol (HTTP) requests received by the Internet Information Service (IIS) web service and protects web applications against Structured Query Language (SQL) injection or cross-site scripting (XSS) attacks.  _(Mod 09 p81)_

# setfacl -x u:guest test
?
remove all access ACL rules of test file for the guest user.  _(Mod 10 p18)_

# setfacl -b u:guest test
?
remove all ACL of test file for the guest user  _(Mod 10 p18)_

# setfacl -m u:user1:rwx test
?
set read and write permission in the ACL of test file for the guest.  _(Mod 10 p18)_

# setfacl -m d:o:rx /Testdir
?
This command is used to set default ACL for test directory.  _(Mod 10 p18)_

RAID 1
?
RAID level 1 provides data reliability since failure of one disk can still provide access to the same data mirrored on the other disks. In a RAID 1 hardware implementation, a minimum of two disks is required. RAID Level 1 undergoes duplexing, which is the need for twice the amount of disk space for storage.  _(Mod 10 p162)_

RAID 50
?
RAID level 50 includes mirroring and striping across multiple RAID levels. This level is a combination of the block level striping of level 0 and the distributed parity of level 5. The configuration of RAID level 50 requires a minimum of six drives. This level undergoes a hot swapping process when a disk fails.  _(Mod 10 p167)_

SMB
?
Server message block store virtual machine files such as configuration, Virtual Hard Disk (VHD) files, and snapshots in file shares.  _(Mod 11 p49)_

IPAM
?
IP Address Management drivers exist in Docker that provides default subnets or IP addresses to the network and the endpoints.  _(Mod 11 p97)_

NFV
?
Network Function Virtualization (NFV) is a network virtualization approach, which separates the network functions (NFs) such as firewalls, traffic control, virtual routing, etc., from physical devices and runs them as software in virtual resources.  _(Mod 11 p79)_

IUM
?
The Isolated User Mode (IUM) feature was introduced particularly for Windows 10 Enterprise version and Windows Server 2016. It is a virtualization-based security feature that utilizes the secure kernels and separates business data and processes from the operating system.  _(Mod 11 p48)_

-mds-clear-on-vm-entry
?
command in the VirtualBox, the affected buffer will be cleared on every VM entry.  _(Mod 11 p56)_

BPDU Guard
?
avoids accidental connection of switch ports with PortFast-enabled and prevents Layer 2 loops or topology changes.  _(Mod 11 p61)_

BPDU Filter
?
It will disable STP on selected ports by stopping the port from sending/receiving BPDUs  _(Mod 11 p61)_

Root Guard
?
It prevents the switches that are configured as access ports from becoming the root switch.  _(Mod 11 p61)_

Loopguard and UDLD
?
Prevents bridging loops occurred due to unidirectional links.  _(Mod 11 p61)_

--l1d-flush-on-vm-entry
?
This command flushes the level 1 data cache from every VM entry.  _(Mod 11 p56)_

Application Plane
?
This SDN component support different applications: Routing, load balancers, monitoring, security, etc.  _(Mod 11 p64)_

Control Plane
?
This SDN component provide abstract view of the network (the network model).  _(Mod 11 p64)_

Data Plane
?
This SDN component perform packet forwarding according to instruction stored in flow tables.  _(Mod 11 p64)_

Open flow
?
This SDN component is a communication protocol to manage the Southbound interface of the SDN.  _(Mod 11 p71)_

implementing role-based source authentication
?
This countermeasure mitigates misconfiguration attacks  _(Mod 11 p76)_

implementing software attestation to authenticate each application
?
This countermeasure mitigates malicious application attacks  _(Mod 11 p76)_

implementing rate limiting and packet dropping techniques at the controller plane
?
This countermeasure mitigates DDoS attacks.  _(Mod 11 p76)_

Orchestrator
?
It controls orchestration, manages software resources, and NFV infrastructure.  _(Mod 11 p80)_

VNF Manager(s)
?
Manages the life cycle of VNF such as updates, query, installation, termination, scale-up/down.  _(Mod 11 p80)_

Element Management System (EMS)
?
It handles the management function of VNF such as Accounting, Configuration, Performance and Security Management, etc.  _(Mod 11 p80)_

Virtualized Infrastructure Manager(s)
?
The function of VIM is to control and manage the communication between VNF with computing, storage, and network resources along with virtualization.  _(Mod 11 p80)_

etcd
?
It is a backing store for Kubernetes Cluster data  _(Mod 11 p137)_

Kube-scheduler
?
It monitors the newly created pods, which are not having any assigned nodes.  _(Mod 11 p99)_

Kube-controller-manager
?
It runs the controller processes.  _(Mod 11 p99)_

Cloud-controller-manager
?
It runs the controller that communicates with the cloud providers.  _(Mod 11 p99)_

cloud broker
?
entity that manages cloud services regarding the usage, performance, and delivery, and maintains the relationship between the CSPs and cloud consumers.  _(Mod 12 p19)_

cloud auditor
?
It is a party that independently examines the cloud service controls to express a corresponding opinion.  _(Mod 12 p18)_

cloud carrier
?
It acts as an intermediary that provides connectivity and transport services between the CSPs and cloud consumers  _(Mod 12 p18)_

cloud provider
?
It manages the computing infrastructure intended for providing services (directly or via a cloud broker) to the interested parties via network access.  _(Mod 12 p18)_

Azure Key Vault
?
It is a secure storage for the keys used to encrypt the data at rest in Azure services.  _(Mod 12 p194)_

Azure Disk Encryption
?
It can be performed through the Azure Key Vault to control and manage the encrypted keys.  _(Mod 12 p194)_

Azure Transparent Data Encryption (TDE)
?
It is an SQL Azure feature to encrypt data at both the database and server levels.  _(Mod 12 p197)_

Azure Storage Service Encryption (SSE)
?
It automatically encrypts the data during storage and decrypts the data at the time of retrieval. It is applied to the entire storage system of Microsoft Azure, and users can enable or disable this feature.  _(Mod 12 p196)_

Google Cloud Armor
?
It is to defend DDoS attacks.  _(Mod 12 p282)_

Google VPS
?
It helps in regulating the communication of VM-based applications by setting firewall rules.  _(Mod 12 p283)_

Google Stackdriver
?
It is to monitor, diagnose, and fix applications across the GCP.  _(Mod 12 p283)_

Google Cloud NAT
?
It allows private VMs or private GKE clusters to connect to the internet. It minimizes the access paths and public IPs.  _(Mod 12 p283)_

Google Cloud Shared VPC
?
It can configure and centrally manage one or more virtual networks across multiple projects in an organization for secured and efficient communication by utilizing internal IPs.  _(Mod 12 p285)_

Google Cloud Routes
?
These are the paths taken by the network traffic from a VM instance to reach another destination.  _(Mod 12 p289)_

Google Cloud VPC
?
It is network is a virtual representation of the physical network, which connects VM instances, GKE clusters, App Engine, and other resources of a project.  _(Mod 12 p284)_

802.11i
?
It is used as a standard for WLANs and provides improved encryption for networks. 802.11i requires new protocols such as TKIP, AES.  _(Mod 13 p12)_

802.16
?
It is also known as Wi-Max. This standard is a specification for fixed broadband wireless metropolitan access networks (MANs) that use a point-to-multi-point architecture.  _(Mod 13 p13)_

802.11e
?
It defines the Quality of Service (QoS) for wireless applications. The standard maintains the quality of video and audio streaming, real time online applications, VoIP, etc.  _(Mod 13 p11)_

Content-based signature
?
Content-based signatures are detected by analyzing the data in the payload and matching a text string to a specific set of characters. If undetected, these signatures can open backdoors in a system, providing administrative controls to an outsider.  _(Mod 14 p21)_

Atomic signature
?
To detect an atomic signature, administrators need to analyze a single packet to determine if the signature includes malicious patterns.  _(Mod 14 p21)_

Composite signature
?
Administrators need to analyze a series of packets over a long period of time to detect attack signatures.  _(Mod 14 p21)_

tcp.dstport==7
?
detect TCP ping sweep attempts  _(Mod 14 p43)_

udp.dstport==7
?
detect UDP ping sweep attempts.  _(Mod 14 p43)_

TCP null scan attempt
?
can penetrate through a router and a firewall that filter incoming packets with particular flags set because null scan does not contain any set flag and it is not supported by Windows.  _(Mod 14 p48)_

icmp.type==3 and icmp.code==3
?
detect UDP scan attempts using Wireshark  _(Mod 14 p50)_

Centralized Logging
?
records changes to firewall policy collects and aggregates logs in one central location works in four parts: log collection, transport, storage, and analysis  _(Mod 15 p13)_

Local Logging
?
used by the systems that have a limited number of hosts  _(Mod 15 p12)_

Push-based mechanism
?
In a push-based mechanism, the system or application either saves records on the local disk or sends them over the network.  _(Mod 15 p6)_

Pull-based mechanism
?
In a pull-based mechanism, a system or an application pulls the log records from a log source. It works based on the client-server model. The system or device that follows this mechanism usually stores their log data in a proprietary format.  _(Mod 15 p6)_

Mac Security logs
?
contains information about login/logout activities and helps in determining attempted and successful unauthorized activities.  _(Mod 15 p50)_

Mac Firewall logs
?
It is a built-in firewall that can log a large amount of data using a program called appfwloggerd.  _(Mod 15 p50)_

User-specific logs
?
User's home directory contains OS component and third-party applications' log information.  _(Mod 15 p50)_

Command line logs
?
Look at the command line history for each user to check command line information.  _(Mod 15 p51)_

Mac Daily.out log
?
These log files are generated based on the daily activities performed overnight when your system is running but not logged in. It stores network interface history.  _(Mod 15 p53)_

W3C Extended log file
?
It is a customizable ASCII format with different properties, separated with spaces. This format enables removal of unwanted property fields to limit the log size.  _(Mod 15 p101)_

IIS log file format
?
This format includes BASIC items such as client IP address, user information, date and time, service and instance, service status code, server name, and IP address, request type, number of bytes received, number of bytes sent, the target of operation, etc.  _(Mod 15 p103)_

NCSA Common log file format
?
It records items related to user requests such as remote hostname, username, date, time, request type, HTTP status code, and the number of bytes sent by the server.  _(Mod 15 p104)_

Apache common log format
?
In this log format, basic weblog parameters are included. It only displays information that is needed to determine the host and the request. Additionally, information about the agent, cookie string, domain name, referrer, time to serve, etc., is excluded in this format.  _(Mod 15 p109)_

Log generator
?
This tier consists of the host that produces the log messages  _(Mod 15 p120)_

Log monitoring:
?
he third tier consists of consoles that monitor and review the log data as well as the outputs of log analysis. These consoles are used to produce reports.  _(Mod 15 p120)_

Log collection
?
Log collection is the process of collecting log messages from various sources to the database in a central location.  _(Mod 15 p121)_

Log transmission
?
To store the logs in a centralized location, they are transmitted through different transport mechanisms such as syslog UDP, syslog TCP, encrypted syslog, etc.  _(Mod 15 p122)_

Log storage
?
All the log files collected from various devices are stored in central repository/databases. Stored databases can be retrieved in structured way when needed.  _(Mod 15 p122)_

Log normalization
?
Log normalization is the process of accepting logs from heterogeneous sources with different formats and converting them into a common format.  _(Mod 15 p122)_

Log correlation
?
Log correlation is the process of matching a series of normalized log data to determine a set of related events based on a certain set of rules.  _(Mod 15 p122)_

Log analysis
?
Log analysis is the process of identifying the patterns and anomalies in the correlated log data that signifies any intrusion attempt or policy violation activity.  _(Mod 15 p122)_

Alerting and reporting
?
An alerting system generates alerts and sends a report to the user if any suspicious event is observed in the logs or calculated matrices.  _(Mod 15 p122)_

Evidence Examiner/Investigator:
?
Evidence Examiner/Investigator examines the evidence acquired and sorts of useful evidence. Examines and sorts the evidence according to its relevance for the case. By maintaining an evidence hierarchy, the evidence examiner appropriately prioritizes the evidence.  _(Mod 16 p125)_

First responder
?
he first responder is responsible for protecting, integrating, and preserving any evidence obtained from the crime scene.  _(Mod 16 p11)_

Evidence Manager
?
The Evidence Manager manages the evidence so that it is admissible in a court of law.  _(Mod 16 p125)_

IR Manager
?
The IR manager is a technical expert who understands security and incident management. They are responsible for the actions performed by the incident analysts and report the information to the incident officer.  _(Mod 16 p8)_

Forensic Investigation and Incident Containment
?
Both are conducted simultaneously. IR helps organizations contain security events, but a computer forensic investigation enables investigators to find the root cause of the security issue.  _(Mod 16 p123)_

Evidence Investigator
?
These examine the evidence acquired and sort useful evidence.  _(Mod 16 p124)_

Business Recovery
?
An advance plan, arrangement, procedure to recover the business processes such as workspace, personnel, equipment, and facilities is called Business Recovery.  _(Mod 17 p7)_

Contingency Planning
?
Contingency plans ensure continuous on-time product and service delivery, on-site and off-site business operations, and customer satisfaction.  _(Mod 17 p7)_

Emergency Management
?
Emergency Management is the procedures and actions that are taken instantly after a crisis in order to safeguard people from harm.  _(Mod 17 p8)_

BCP
?
Business continuity planning (BCP) is a document that is developed to ensure resilience from potential threats and allow business operations to continue under adversity.  _(Mod 17 p20)_

BCM
?
Business continuity management is a process that ensures that business operations are not affected due to disruptive incidents.  _(Mod 17 p7)_

DRP
?
A disaster recovery plan is documented instructions for responding to an unexpected disruptive event (recover from disaster).  _(Mod 17 p22)_

BIA
?
BIA is a systematic process that determines and evaluates the potential effects of an interruption to critical business operations as a result of a disaster, an accident, or an emergency.  _(Mod 17 p10)_

ISO 22301:2019
?
ISO 22301:2019 describes requirements to implement, maintain, and improve the management system to protect against, reduce the likelihood of the occurrence of, prepare for, respond to and recover from disruptions when they arise  _(Mod 17 p28)_

ISO 22313:2012
?
ISO 22313:2012 guides ISO 22301 for setting up and managing effective business continuity and management system (BCMS).  _(Mod 17 p29)_

ISO/IEC 27031:2011
?
ISO/IEC 27031:2011 describes the concepts and principles of information and communication technology (ICT) readiness for business continuity, provides a framework of methods and processes to identify and specify all aspects (such as performance criteria, design, and implementation) for improving an organization's ICT readiness to ensure business continuity  _(Mod 17 p30)_

Chief Information Officer
?
The CIO is responsible for executing the policies and plans required for supporting the information technology and computer systems of an organization. The main responsibility of a CIO is to train employees and other executive management regarding the possible risks in IT and its impact on the business.  _(Mod 18 p8)_

IT Security Program Managers and Computer Security Officer
?
ISSO provides the required support to information system owners with a selection of security controls needed for protecting a system. They also play an important role in the selection and amendment of security controls in an organization.  _(Mod 18 p9)_

Risk assessment
?
Risk assessment determines the kind of risks present, the likelihood and severity of risk, priorities and plans for risk control. Risk assessment determines the types of risks that exist, likelihood and severity of risks, and priorities and plans for risk control. Decisions made in the risk treatment phase are based on the results of a risk assessment.  _(Mod 18 p15)_

Risk identification
?
It is a process to list the risks and their characteristics before they cause harm to the organization. The techniques used for risk identification include checklists, flow charts, and systems analysis.  _(Mod 18 p14)_

Risk treatment
?
t is the process of selecting and implementing appropriate controls on the identified risks in order to modify them.  _(Mod 18 p19)_

Risk tracking
?
Risk tracking identifies the chance of a new risk and includes monitoring the probability, impact, status, and exposure of risk. helps a network defender identify the chances of a new risk occurring  _(Mod 18 p24)_

Risk review
?
It enables the organization to keep the risk management objectives, and context up-to-date and accurate.  _(Mod 18 p24)_

Eliminate the risk
?
It involves eliminating the risk by applying controls to reduce the threat of exploiting the vulnerability to zero.  _(Mod 18 p21)_

Reduce the risk
?
It involves finding ways to reduce the likelihood rate of risk to an acceptable level  _(Mod 18 p21)_

Risk avoidance
?
It involves avoiding the factor that enhances the risk factor of any process in the business or finding an alternative that goes well with business needs. For instance, not allowing the use of laptops in the organization to avoid the risks associated with the use of laptops.  _(Mod 18 p21)_

Mitigate the risk
?
It involves reducing the risks associated with a threat or vulnerability by implementing direct or competing controls.  _(Mod 18 p21)_

Discovery
?
This phase involves identification, consideration, and evaluation of network assets. It provides a hacker's view of the network.  _(Mod 18 p47)_

Assessment
?
This phase involves scanning and evaluating a system for vulnerabilities  _(Mod 18 p46)_

Mitigation
?
It is an action taken to prevent vulnerabilities from exploitation. It involves reducing the risk by taking other actions instead of correcting a discovered vulnerability.  _(Mod 18 p53)_

Verification
?
This phase involves monitoring network continuously to check for new vulnerabilities.  _(Mod 18 p46)_

Internal vulnerability assessment
?
An internal vulnerability assessment evaluates a network for the presence of internal vulnerabilities.  _(Mod 18 p61)_

External vulnerability assessment
?
An external vulnerability assessment evaluates the security profile of an organization from the perimeter of the network.  _(Mod 18 p59)_

Web vulnerability assessment
?
It involves crawling the website in order to discover potential vulnerabilities, and then report these results.  _(Mod 18 p63)_

Attack Surface Visualization
?
This step involves mapping out all devices, paths, and networks.  _(Mod 19 p9)_

IoEs' Identification
?
In this step, potential risk exposures that attackers can use to breach the security of an organization are identified.  _(Mod 19 p9)_

Attack Simulation
?
This step involves recognizing how the identified IoE could turn to exploit.  _(Mod 19 p9)_

Attack Surface Reduction
?
This step involves implementing appropriate security controls and countermeasures to reduce the attack surface of a system.  _(Mod 19 p9)_

Conduct Attack Simulation
?
It helps a network defender validate and manage the security controls across the organization. It enables a network defender to assess the security flaws before any attack takes place.  _(Mod 19 p34)_

Cloud to User
?
This refers to the attacks that a Cloud service faces from a user's point of view. This attack surfaces in cloud computing is difficult to define  _(Mod 19 p52)_

User to Cloud
?
This pertains to the different types of attack vectors that target a user. It has its origins in the Cloud system. For example, phishing-like attempts that present users a fake usage bill of the Cloud provider.  _(Mod 19 p52)_

Cloud to Service
?
It is related to exposing Cloud resources/interfaces to service instances. For example, resource exhaustion, triggering the Cloud provider to provide more resources or end up in a Denial-of-Service (DoS), and attacks on the Cloud system hypervisor. it slightly tricky to separate the service and cloud  _(Mod 19 p51)_

Service to Cloud
?
It is related to exposing the service instance to the Cloud provider. Examples include availability reductions, privacy attacks, malicious interference, data integrity attack, data confidentiality attack, etc.  _(Mod 19 p51)_

IoT Applications and Software Vulnerabilities
?
Attacks can exploit vulnerabilities in application interfaces and the software of IoT devices. These can compromise systems, steal sensitive or personal data (credentials), or insert malicious firmware updates.  _(Mod 19 p54)_

IoT Device Vulnerabilities
?
The parts of a device from which vulnerabilities emerge are physical interfaces (USB ports), failures in memory, firmware, web interface, admin interfaces, and network services.  _(Mod 19 p54)_

IoT Communication Channel Vulnerabilities
?
Attacks can occur due to the ways in which IoT components connect with each other. For example, protocols used in IoT systems, Bluetooth, and Wi-Fi can be exposed to vulnerabilities.  _(Mod 19 p54)_

IoT Cloud Interface Vulnerabilities
?
Attacks are triggered by inadequate passwords, default credentials, and insecure transport encryption in using Cloud interfaces for IoT.  _(Mod 19 p54)_

IoT Device Memory Vulnerabilities
?
It has the possibility of possessing clear-text credentials stored in memory and the monitoring of cipher keys.  _(Mod 19 p55)_

IoT Device Web Interface
?
It comprises the web application vulnerabilities of the IoT device web interface and credential management.  _(Mod 19 p55)_

IoT Device Firmware
?
It has the possibility of vulnerabilities in the device firmware that provides the features and functions for a solution.  _(Mod 19 p56)_

IoT Device Physical Interface
?
It comprises the vulnerabilities in unsecured elements, which are used to compromise IoT devices.  _(Mod 19 p55)_

Strategic Threat Intelligence collection sources
?
This intelligence is collected from sources such as open-source intelligence (OSINT), CTI vendors, and Information Sharing and Analysis Organizations (ISAOs) / Information Sharing and Analysis Centers (ISACs).  _(Mod 20 p11)_

Tactical Threat Intelligence collection sources
?
The collection sources for tactical threat intelligence include campaign reports, malware, incident reports, attack group reports, human intelligence, etc. This intelligence is generally obtained by reading white/technical papers, communicating with other organizations, or purchasing intelligence from third parties.  _(Mod 20 p12)_

Operational Threat Intelligence collection sources
?
Operational threat intelligence is generally collected from sources such as humans, social media, and chat rooms, and also from real-world activities and events that result in cyber-attacks.  _(Mod 20 p13)_

Indicators of Exposure (IoE)
?
It shows potentially exploitable vectors before an incident takes place and helps in understanding the security posture of the organization and making more informed decisions to prevent the breaches in advance.  _(Mod 19 p19)_

Indicators of Attacks (IoAs)
?
It reveals an active attack before IoCs become visible  _(Mod 20 p21)_

Indicators of Compromise (IoCs)
?
IoCs are the technical indicators of threat and are discovered through the investigation after the occurrence of an incident or through the alerts if the network is monitored?  _(Mod 20 p16)_

Key Risk Indicators (KRIs)
?
KRIs are the most important indicators of an organization's overall health, it helps in reducing loss and prevents risk exposure.  _(Mod 18 p10)_

OpenIOC
?
It is a format of IoC with its XML-based framework to describe the complex semantics of the malware behavior.  _(Mod 20 p17)_

CybOX
?
CybOX (Cyber Observable Expression) provides a standard for defining indicator details (observables) regarding measurable events and stateful properties and mainly aims at automating the sharing of security information by providing more than 70 defined objects.  _(Mod 20 p17)_

MAEC
?
MAEC (Malware Attribute Enumeration and Characterization) is a standardized language to describe CTI.  _(Mod 20 p18)_

TAXII
?
TAXII (Trusted Automated eXchange of Indicator Information) is a set of specifications for exchanging cyber threat information over HTTPS. TAXII uses XML and HTTP for message content and transport. It is specially created to support the exchange of CIT represented in STIX.  _(Mod 20 p18)_

---

Provenance, the 19 cards held back for not fully verifying, and the 6 dropped are
all in [[External-Flashcards-Verification]]. That note carries no `flashcard` tag, so
the Spaced Repetition plugin never parses it and none of those cards can reach your
review queue by accident.
