---
type: question
module: "ext"
tags: [exam]
topic: "CND study deck - 239 cards verified against the 20 module PDFs"
exam_weight: unknown
status: done
unresolved: []
---
# CND - Verified Study Deck

> [!info] What this is
> **239 cards, every one matched to the 20 module PDFs.** Each carries its source as
> `_(Mod NN pNN)_`, so you can always check it against the courseware.
> Full provenance, including every card that failed, is in
> [[External-Flashcards-Verification]].
> Your original Quizlet export had 264: the 19 that did not fully verify are under
> *Revision* at the end, and 6 were dropped (2 with no basis in the courseware,
> 4 redundant repeats of another card).

> [!warning] Read before drilling
> Source was your own Quizlet export (set `617277655`), **not** official courseware, so
> it lives here and not in `20-Notes/`. Do not memorise anything from *Revision* yet.
> One fix was applied to the export: card 9's answer said "Pretty Good Service" where
> the courseware says "Pretty Good **Privacy**".
>
> Card 1 is the one oddity: the export stored an MCQ as the answer with the question as
> the term, and the answer text is just the four options. The useful fact is on
> `Mod 03 p113`: a low-interaction honeypot fakes the services the attacker most
> often asks for.

## Deck

Q:: Low-interaction Honeypot
A:: From the following, identify the type of honeypot which generally fakes those services that are frequently asked by the attacker. They are essentially a single machine with multiple virtual machines. Low-interaction Honeypot Pure Honeypot High-interaction Honeypot Production Honeypot  _(Mod 03 p113)_
#flashcard

Q:: Public key infrastructure
A:: is treated as the most effective method for providing verification during electronic transactions  _(Mod 03 p82)_
#flashcard

Q:: Secure Hashing Algorithm (SHA)
A:: generate a cryptographically one-way hash and is published by NIST as a Federal Information Standard  _(Mod 03 p94)_
#flashcard

Q:: Digital Signature Algorithm
A:: It is a Federal Information Processing Standard (FIPS) for digital signatures.  _(Mod 03 p90)_
#flashcard

Q:: AES
A:: is a National Institute of Standards and Technology (NIST) specification for the encryption of electronic data and is being used by U.S. government agencies to secure sensitive but unclassified material  _(Mod 03 p87)_
#flashcard

Q:: SSL
A:: Secure Sockets Layer (SSL) works at the transport layer.  _(Mod 03 p139)_
#flashcard

Q:: IPSec
A:: Internet Protocol Security (IPSec) works at the network layer  _(Mod 03 p139)_
#flashcard

Q:: PGP
A:: Pretty Good Privacy (PGP) protocol works at the application layer.  _(Mod 03 p139)_
#flashcard

Q:: S/MIME
A:: Secure/Multi-Purpose Internet mail Extension (S/MIME) works at the application layer  _(Mod 03 p139)_
#flashcard

Q:: Network Address Translation (NAT)
A:: firewall technology helps hide the internal network's configuration and thereby reduces the success of attacks on the network or system. It can act as a firewall filtering technique where it allows only those connections that originate inside a network and can block the connections that originate outside the network.  _(Mod 04 p23)_
#flashcard

Q:: Application-level gateway
A:: is a firewall that controls input, output, and/or access across an application or service. It monitors and possibly blocks the input, output, or system service calls, which do not meet the policy of the firewall.  _(Mod 04 p17)_
#flashcard

Q:: Application proxy
A:: An application-level proxy works as a proxy server. It correlates with the gateway server and separates the enterprise network from the Internet.  _(Mod 04 p20)_
#flashcard

Q:: Stateful multi-layer inspection
A:: These firewalls filter packets at the network layer, determine whether session packets are legitimate, and evaluate the contents of packets at the application layer.  _(Mod 04 p19)_
#flashcard

Q:: Firewalk
A:: is used for reconnaissance purpose where it discovers firewall rules using an IP TTL expiration technique.  _(Mod 04 p62)_
#flashcard

Q:: Security Reference Monitor (SRM)
A:: enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.  _(Mod 05 p17)_
#flashcard

Q:: Local Security Authority Subsystem (LSASS)
A:: implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.  _(Mod 05 p19)_
#flashcard

Q:: Security Accounts Manager (SAM)
A:: is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.  _(Mod 05 p21)_
#flashcard

Q:: Windows Integrity Control (WIC)
A:: is an access control mechanism for controlling the interactions between objects based on their integrity or level of trustworthiness.  _(Mod 05 p41)_
#flashcard

Q:: User Account Control (UAC)
A:: is a key access control enforcement feature in Windows that improves the security of the OS by limiting application software to standard user privileges until an administrator authorizes an elevation  _(Mod 05 p98)_
#flashcard

Q:: Network logon service (NetLogon)
A:: a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.  _(Mod 05 p30)_
#flashcard

Q:: Windows logon application (WinLogon)
A:: used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background  _(Mod 05 p27)_
#flashcard

Q:: Just Enough administration (JEA)
A:: a security technology used to limit the number of cmdlets or administration privileges of administrator, user, or service accounts.  _(Mod 05 p106)_
#flashcard

Q:: SID
A:: To troubleshoot user or object access issues across the domain system, the administrator needs to view the SID of users or group.  _(Mod 05 p39)_
#flashcard

Q:: RID
A:: Every SID contains a relative identifier (RID) at the end, and attackers try to access the list of SIDs to try and replace the RID with an administrative account's details so that they can get access to administrative privileges.  _(Mod 05 p100)_
#flashcard

Q:: Microsoft Windows Defender Credential Guard (WDCG)
A:: protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.  _(Mod 05 p81)_
#flashcard

Q:: CPs
A:: a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.  _(Mod 05 p29)_
#flashcard

Q:: Network Level Authentication (NLA)
A:: s implemented to send the user credentials securely from the client side using a security service provider of the client and make the user to authenticate before the session gets started.  _(Mod 05 p219)_
#flashcard

Q:: Enabling Remote Credential Guard
A:: If Remote Credential Guard is enabled, the connection to the other systems using single sign-on will be active only when the host supports it.  _(Mod 05 p221)_
#flashcard

Q:: sudo apt autoclean
A:: clean partial packages  _(Mod 06 p24)_
#flashcard

Q:: sudo apt-get clean
A:: This command cleans the apt cache  _(Mod 06 p24)_
#flashcard

Q:: sudo apt autoremove application-name
A:: uninstalls or removes unnecessary packages  _(Mod 06 p24)_
#flashcard

Q:: NIS-Server
A:: The NIS-Server tends to distribute system configuration files. Also, it is an insecure system that has been vulnerable to DoS attacks, buffer overflows and poor authentication for querying NIS maps.  _(Mod 06 p22)_
#flashcard

Q:: Telnet-Server
A:: It comprises the telnetd daemon, which allows connections from users from other systems through the telnet protocol. The insecure and unencrypted telnet protocol could allow access to sniff network traffic, which can steal the credentials.  _(Mod 06 p22)_
#flashcard

Q:: RSH-Server
A:: The Berkeley rsh-server (rsh, rlogin, rcp) package comprises legacy services that exchange credentials in clear-text. This service comprises many security exposures that can be exploited.  _(Mod 06 p22)_
#flashcard

Q:: TFTP-Server
A:: The file transfer protocol 'Trivial File Transfer Protocol (TFTP)' is used to transfer configuration or boot machines from a boot server automatically. It does not support authentication and ensure the confidentiality of data integrity.  _(Mod 06 p22)_
#flashcard

Q:: rwxrwxrwx
A:: no restrictions on anything. Anybody can do anything  _(Mod 06 p75)_
#flashcard

Q:: rw-rw-rw
A:: All users can read and write the file  _(Mod 06 p75)_
#flashcard

Q:: rw-r--r--
A:: The owner can read and write a file, while others may only read the file. A very common setting where everybody may read but only the owner can make changes.  _(Mod 06 p75)_
#flashcard

Q:: rw-------
A:: Owner can read and write a file. Others have no rights. A common setting for files that the owner wants to keep private.  _(Mod 06 p75)_
#flashcard

Q:: rwx------
A:: The file owner may read, write, and execute the file. Nobody else has any rights. This setting is useful for programs that only user may use and are kept private from others.  _(Mod 06 p75)_
#flashcard

Q:: rwxr-xr-x
A:: The file owner may read, write, and execute the file. Others can read and execute the file. This setting is useful for all programs that are used by all users.  _(Mod 06 p75)_
#flashcard

Q:: iptables -A INPUT -p icmp -i eth0 -j DROP
A:: blocks incoming ping requests  _(Mod 06 p94)_
#flashcard

Q:: iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP
A:: This command will block XMAS scan attack  _(Mod 06 p91)_
#flashcard

Q:: ptables -A INPUT -i eth0 -s xxx.xxx.xxx.xxx -j DROP
A:: block connection on network interface  _(Mod 06 p91)_
#flashcard

Q:: Lynis
A:: Lynis can perform an extensive health scan of systems to support system hardening and compliance testing.  _(Mod 06 p114)_
#flashcard

Q:: AppArmor
A:: Linux security module that allows a system administrator to restrict programs' capabilities with per-program profiles. It is utilized by the system administrator to restrict programs to a limited set of resources.  _(Mod 06 p115)_
#flashcard

Q:: SELinux
A:: It is a mandatory access control (MAC) module that resides in the kernel level of Linux systems. It decides which process can access which files, directories and ports and provides an additional layer of system security.  _(Mod 06 p116)_
#flashcard

Q:: CYOD policy
A:: The CYOD policy allows employees to choose devices (laptops, smartphones, and tablets) from a preapproved set of devices to access company data as per the organization's access privileges.  _(Mod 07 p11)_
#flashcard

Q:: BYOD policy
A:: The BYOD policy allows employees to use the devices that they are comfortable with and best fits their preferences and work purposes.  _(Mod 07 p6)_
#flashcard

Q:: COBO policy
A:: The COBO policy allows employees to use and manage devices purchased by the organization but restricts the use of the device for business use only.  _(Mod 07 p19)_
#flashcard

Q:: COPE policy
A:: The COPE policy allows employees to use and manage devices purchased by the organizations. Larger enterprises are more likely to employ the COPE model. COPE reduces the risks associated with BYOD by implementing stringent policies and protecting devices.  _(Mod 07 p15)_
#flashcard

Q:: MEM
A:: An MEM solution ensures the security of the corporate email infrastructure and data on mobile devices.  _(Mod 07 p45)_
#flashcard

Q:: MDM
A:: An MDM solution is used to deploy, secure, monitor, and manage company-owned and employee-owned devices.  _(Mod 07 p30)_
#flashcard

Q:: UEM
A:: An UEM solution helps in managing and controlling internet-enabled mobile devices, desktops, applications, and content across the organization from a single interface.  _(Mod 07 p51)_
#flashcard

Q:: MAM
A:: An MAM solution enables an organization to secure, manage, and distribute enterprise applications on user mobile devices, without interfering with personal apps and data.  _(Mod 07 p38)_
#flashcard

Q:: Data leaks identification
A:: MTD solutions can be used by admins to identify data leaks to block access to the risky content.  _(Mod 07 p43)_
#flashcard

Q:: Location-based content delivery
A:: MCM solutions are used by admins for location-based content delivery.  _(Mod 07 p40)_
#flashcard

Q:: App wrapping
A:: MAM solutions are used by admins for app wrapping.  _(Mod 07 p39)_
#flashcard

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

Q:: IoT Device Layer
A:: The device or the Thing layer of IoT includes the hardware that constitutes IoT devices.  _(Mod 08 p14)_
#flashcard

Q:: IoT Process Layer
A:: The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.  _(Mod 08 p15)_
#flashcard

Q:: Installing an IoT firewall
A:: will mitigate malicious scripts attack  _(Mod 08 p67)_
#flashcard

Q:: Implementing a strong IoT encryption scheme
A:: prevents attacks like cryptanalysis attacks  _(Mod 08 p67)_
#flashcard

Q:: implementing high data privacy and privilege levels for IoT
A:: prevents social engineering attacks.  _(Mod 08 p40)_
#flashcard

Q:: Device-to-Device model
A:: In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.  _(Mod 08 p16)_
#flashcard

Q:: Device-to-Cloud model
A:: In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.  _(Mod 08 p17)_
#flashcard

Q:: Cloud-to-Cloud model
A:: his type of communication model extends the device-to-cloud communication type in which the data from IoT devices can be accessed by authorized third parties. Here, devices upload their data onto the cloud, and the data is accessed or analyzed later by third parties.  _(Mod 08 p18)_
#flashcard

Q:: Device-to-Gateway model
A:: In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.  _(Mod 08 p17)_
#flashcard

Q:: Monitoring bandwidth consumption of IoT devices
A:: Monitoring bandwidth consumption helps to know how much data is used or sent by IoT device, and to know the download and upload bandwidth consumption of devices in the IoT network.  _(Mod 08 p108)_
#flashcard

Q:: Implementing end-to-end (E2E) security and identity management
A:: It will provide security and privacy in the IoT device and to maintain trust.  _(Mod 08 p90)_
#flashcard

Q:: Constructing virtual LAN pipe
A:: Virtual LAN pipe should be constructed on the fly with each new IoT device connection that would allow IP-based communication to only one endpoint - the publicly facing internet  _(Mod 08 p78)_
#flashcard

Q:: Monitoring the behaviour of IoT device
A:: Monitoring the behaviour of the IoT device provides full visibility and insights of the IoT assets, so that the organization can quickly react to mitigate the risks and resolve an issue before it impact the business.  _(Mod 08 p75)_
#flashcard

Q:: Domotz
A:: It is an IoT monitoring and management tool.  _(Mod 08 p75)_
#flashcard

Q:: SeaCat.io
A:: It is a security-first SaaS technology to operate IoT products in a reliable, scalable and secure manner.  _(Mod 08 p115)_
#flashcard

Q:: DigiCert IoT Security Solutions
A:: It protect private data and home networks while preventing unauthorized access using PKI-based security solutions for consumer IoT devices.  _(Mod 08 p116)_
#flashcard

Q:: beSTORM
A:: It is an IoT vulnerability scanning tool  _(Mod 08 p85)_
#flashcard

Q:: GSMA
A:: GSMA developed IoT Security Guidelines and IoT Security Assessment that help create a secure IoT market with trusted, reliable services that can scale as the market grows.  _(Mod 08 p132)_
#flashcard

Q:: AT&T
A:: AT&T developed The CEO's Guide to Securing the Internet of Things  _(Mod 08 p135)_
#flashcard

Q:: U.S Department of Homeland Security
A:: U.S DHS developed Strategic Principles for Securing the Internet of Things.  _(Mod 08 p128)_
#flashcard

Q:: ENISA
A:: ENISA developed 'Baseline Security Recommendations for Internet of Things  _(Mod 08 p135)_
#flashcard

Q:: dm-crypt
A:: dm-crypt is a transparent disk encryption subsystem in Linux kernel versions 2.6 and later. This command is used for disk encryption in Linux.  _(Mod 10 p37)_
#flashcard

Q:: JTAG
A:: It is a standard interface to test and debug chips with debugging software to know how a chip respond to multiple commands.  _(Mod 08 p31)_
#flashcard

Q:: Application Whitelisting
A:: The approach of application whitelisting is trust centric. By default, applications that are not in the whitelist are prevented from being executed.  _(Mod 09 p10)_
#flashcard

Q:: Application Blacklisting
A:: Application blacklisting is threat centric. By default, it allows all applications that are not in the blacklist to be executed.  _(Mod 09 p13)_
#flashcard

Q:: Application Sandboxing
A:: Application sandboxing is the process of running applications in a sealed container (sandbox) so that the applications cannot access critical system resources and other programs.  _(Mod 09 p47)_
#flashcard

Q:: Application Patch Management
A:: Application patch management is the process of ensuring the security of applications on hosts by regularly deploying new or missing patches.  _(Mod 09 p68)_
#flashcard

Q:: AppLocker
A:: When AppLocker rules are enforced, apps excluded from the list of allowed apps are prevented from running.  _(Mod 09 p24)_
#flashcard

Q:: Group Policy Settings
A:: Group Policy Settings can enable blocking software installation.  _(Mod 09 p36)_
#flashcard

Q:: Registry Editor
A:: Network defenders can block the execution of an application on a system by disabling the application using the Windows Registry Editor.  _(Mod 09 p39)_
#flashcard

Q:: Windows Defender Application Guard
A:: Windows Defender Application Guard (WDAG) isolates Microsoft Edge and blocks websites from accessing the local storage, memory, installed apps, and corporate network endpoints.  _(Mod 09 p61)_
#flashcard

Q:: Sandbox for FireFox
A:: Content Process Sandbox Level  _(Mod 09 p52)_
#flashcard

Q:: Sandbox for Chrome
A:: Strict-Origin-Isolation  _(Mod 09 p50)_
#flashcard

Q:: Toggling feature controls of Sandbox Protections
A:: Used for Acrobat Reader  _(Mod 09 p53)_
#flashcard

Q:: Microsoft URLScan
A:: is a WAF tool that analyzes and filters all Hypertext Transfer Protocol (HTTP) requests received by the Internet Information Service (IIS) web service and protects web applications against Structured Query Language (SQL) injection or cross-site scripting (XSS) attacks.  _(Mod 09 p81)_
#flashcard

Q:: # setfacl -x u:guest test
A:: remove all access ACL rules of test file for the guest user.  _(Mod 10 p18)_
#flashcard

Q:: # setfacl -b u:guest test
A:: remove all ACL of test file for the guest user  _(Mod 10 p18)_
#flashcard

Q:: # setfacl -m u:user1:rwx test
A:: set read and write permission in the ACL of test file for the guest.  _(Mod 10 p18)_
#flashcard

Q:: # setfacl -m d:o:rx /Testdir
A:: This command is used to set default ACL for test directory.  _(Mod 10 p18)_
#flashcard

Q:: RAID 1
A:: RAID level 1 provides data reliability since failure of one disk can still provide access to the same data mirrored on the other disks. In a RAID 1 hardware implementation, a minimum of two disks is required. RAID Level 1 undergoes duplexing, which is the need for twice the amount of disk space for storage.  _(Mod 10 p162)_
#flashcard

Q:: RAID 50
A:: RAID level 50 includes mirroring and striping across multiple RAID levels. This level is a combination of the block level striping of level 0 and the distributed parity of level 5. The configuration of RAID level 50 requires a minimum of six drives. This level undergoes a hot swapping process when a disk fails.  _(Mod 10 p167)_
#flashcard

Q:: SMB
A:: Server message block store virtual machine files such as configuration, Virtual Hard Disk (VHD) files, and snapshots in file shares.  _(Mod 11 p49)_
#flashcard

Q:: IPAM
A:: IP Address Management drivers exist in Docker that provides default subnets or IP addresses to the network and the endpoints.  _(Mod 11 p97)_
#flashcard

Q:: NFV
A:: Network Function Virtualization (NFV) is a network virtualization approach, which separates the network functions (NFs) such as firewalls, traffic control, virtual routing, etc., from physical devices and runs them as software in virtual resources.  _(Mod 11 p79)_
#flashcard

Q:: IUM
A:: The Isolated User Mode (IUM) feature was introduced particularly for Windows 10 Enterprise version and Windows Server 2016. It is a virtualization-based security feature that utilizes the secure kernels and separates business data and processes from the operating system.  _(Mod 11 p48)_
#flashcard

Q:: -mds-clear-on-vm-entry
A:: command in the VirtualBox, the affected buffer will be cleared on every VM entry.  _(Mod 11 p56)_
#flashcard

Q:: BPDU Guard
A:: avoids accidental connection of switch ports with PortFast-enabled and prevents Layer 2 loops or topology changes.  _(Mod 11 p61)_
#flashcard

Q:: BPDU Filter
A:: It will disable STP on selected ports by stopping the port from sending/receiving BPDUs  _(Mod 11 p61)_
#flashcard

Q:: Root Guard
A:: It prevents the switches that are configured as access ports from becoming the root switch.  _(Mod 11 p61)_
#flashcard

Q:: Loopguard and UDLD
A:: Prevents bridging loops occurred due to unidirectional links.  _(Mod 11 p61)_
#flashcard

Q:: --l1d-flush-on-vm-entry
A:: This command flushes the level 1 data cache from every VM entry.  _(Mod 11 p56)_
#flashcard

Q:: Application Plane
A:: This SDN component support different applications: Routing, load balancers, monitoring, security, etc.  _(Mod 11 p64)_
#flashcard

Q:: Control Plane
A:: This SDN component provide abstract view of the network (the network model).  _(Mod 11 p64)_
#flashcard

Q:: Data Plane
A:: This SDN component perform packet forwarding according to instruction stored in flow tables.  _(Mod 11 p64)_
#flashcard

Q:: Open flow
A:: This SDN component is a communication protocol to manage the Southbound interface of the SDN.  _(Mod 11 p71)_
#flashcard

Q:: implementing role-based source authentication
A:: This countermeasure mitigates misconfiguration attacks  _(Mod 11 p76)_
#flashcard

Q:: implementing software attestation to authenticate each application
A:: This countermeasure mitigates malicious application attacks  _(Mod 11 p76)_
#flashcard

Q:: implementing rate limiting and packet dropping techniques at the controller plane
A:: This countermeasure mitigates DDoS attacks.  _(Mod 11 p76)_
#flashcard

Q:: Orchestrator
A:: It controls orchestration, manages software resources, and NFV infrastructure.  _(Mod 11 p80)_
#flashcard

Q:: VNF Manager(s)
A:: Manages the life cycle of VNF such as updates, query, installation, termination, scale-up/down.  _(Mod 11 p80)_
#flashcard

Q:: Element Management System (EMS)
A:: It handles the management function of VNF such as Accounting, Configuration, Performance and Security Management, etc.  _(Mod 11 p80)_
#flashcard

Q:: Virtualized Infrastructure Manager(s)
A:: The function of VIM is to control and manage the communication between VNF with computing, storage, and network resources along with virtualization.  _(Mod 11 p80)_
#flashcard

Q:: etcd
A:: It is a backing store for Kubernetes Cluster data  _(Mod 11 p137)_
#flashcard

Q:: Kube-scheduler
A:: It monitors the newly created pods, which are not having any assigned nodes.  _(Mod 11 p99)_
#flashcard

Q:: Kube-controller-manager
A:: It runs the controller processes.  _(Mod 11 p99)_
#flashcard

Q:: Cloud-controller-manager
A:: It runs the controller that communicates with the cloud providers.  _(Mod 11 p99)_
#flashcard

Q:: cloud broker
A:: entity that manages cloud services regarding the usage, performance, and delivery, and maintains the relationship between the CSPs and cloud consumers.  _(Mod 12 p19)_
#flashcard

Q:: cloud auditor
A:: It is a party that independently examines the cloud service controls to express a corresponding opinion.  _(Mod 12 p18)_
#flashcard

Q:: cloud carrier
A:: It acts as an intermediary that provides connectivity and transport services between the CSPs and cloud consumers  _(Mod 12 p18)_
#flashcard

Q:: cloud provider
A:: It manages the computing infrastructure intended for providing services (directly or via a cloud broker) to the interested parties via network access.  _(Mod 12 p18)_
#flashcard

Q:: Azure Key Vault
A:: It is a secure storage for the keys used to encrypt the data at rest in Azure services.  _(Mod 12 p194)_
#flashcard

Q:: Azure Disk Encryption
A:: It can be performed through the Azure Key Vault to control and manage the encrypted keys.  _(Mod 12 p194)_
#flashcard

Q:: Azure Transparent Data Encryption (TDE)
A:: It is an SQL Azure feature to encrypt data at both the database and server levels.  _(Mod 12 p197)_
#flashcard

Q:: Azure Storage Service Encryption (SSE)
A:: It automatically encrypts the data during storage and decrypts the data at the time of retrieval. It is applied to the entire storage system of Microsoft Azure, and users can enable or disable this feature.  _(Mod 12 p196)_
#flashcard

Q:: Google Cloud Armor
A:: It is to defend DDoS attacks.  _(Mod 12 p282)_
#flashcard

Q:: Google VPS
A:: It helps in regulating the communication of VM-based applications by setting firewall rules.  _(Mod 12 p283)_
#flashcard

Q:: Google Stackdriver
A:: It is to monitor, diagnose, and fix applications across the GCP.  _(Mod 12 p283)_
#flashcard

Q:: Google Cloud NAT
A:: It allows private VMs or private GKE clusters to connect to the internet. It minimizes the access paths and public IPs.  _(Mod 12 p283)_
#flashcard

Q:: Google Cloud Shared VPC
A:: It can configure and centrally manage one or more virtual networks across multiple projects in an organization for secured and efficient communication by utilizing internal IPs.  _(Mod 12 p285)_
#flashcard

Q:: Google Cloud Routes
A:: These are the paths taken by the network traffic from a VM instance to reach another destination.  _(Mod 12 p289)_
#flashcard

Q:: Google Cloud VPC
A:: It is network is a virtual representation of the physical network, which connects VM instances, GKE clusters, App Engine, and other resources of a project.  _(Mod 12 p284)_
#flashcard

Q:: 802.11i
A:: It is used as a standard for WLANs and provides improved encryption for networks. 802.11i requires new protocols such as TKIP, AES.  _(Mod 13 p12)_
#flashcard

Q:: 802.16
A:: It is also known as Wi-Max. This standard is a specification for fixed broadband wireless metropolitan access networks (MANs) that use a point-to-multi-point architecture.  _(Mod 13 p13)_
#flashcard

Q:: 802.11e
A:: It defines the Quality of Service (QoS) for wireless applications. The standard maintains the quality of video and audio streaming, real time online applications, VoIP, etc.  _(Mod 13 p11)_
#flashcard

Q:: Content-based signature
A:: Content-based signatures are detected by analyzing the data in the payload and matching a text string to a specific set of characters. If undetected, these signatures can open backdoors in a system, providing administrative controls to an outsider.  _(Mod 14 p21)_
#flashcard

Q:: Atomic signature
A:: To detect an atomic signature, administrators need to analyze a single packet to determine if the signature includes malicious patterns.  _(Mod 14 p21)_
#flashcard

Q:: Composite signature
A:: Administrators need to analyze a series of packets over a long period of time to detect attack signatures.  _(Mod 14 p21)_
#flashcard

Q:: tcp.dstport==7
A:: detect TCP ping sweep attempts  _(Mod 14 p43)_
#flashcard

Q:: udp.dstport==7
A:: detect UDP ping sweep attempts.  _(Mod 14 p43)_
#flashcard

Q:: TCP null scan attempt
A:: can penetrate through a router and a firewall that filter incoming packets with particular flags set because null scan does not contain any set flag and it is not supported by Windows.  _(Mod 14 p48)_
#flashcard

Q:: icmp.type==3 and icmp.code==3
A:: detect UDP scan attempts using Wireshark  _(Mod 14 p50)_
#flashcard

Q:: Centralized Logging
A:: records changes to firewall policy collects and aggregates logs in one central location works in four parts: log collection, transport, storage, and analysis  _(Mod 15 p13)_
#flashcard

Q:: Local Logging
A:: used by the systems that have a limited number of hosts  _(Mod 15 p12)_
#flashcard

Q:: Push-based mechanism
A:: In a push-based mechanism, the system or application either saves records on the local disk or sends them over the network.  _(Mod 15 p6)_
#flashcard

Q:: Pull-based mechanism
A:: In a pull-based mechanism, a system or an application pulls the log records from a log source. It works based on the client-server model. The system or device that follows this mechanism usually stores their log data in a proprietary format.  _(Mod 15 p6)_
#flashcard

Q:: Mac Security logs
A:: contains information about login/logout activities and helps in determining attempted and successful unauthorized activities.  _(Mod 15 p50)_
#flashcard

Q:: Mac Firewall logs
A:: It is a built-in firewall that can log a large amount of data using a program called appfwloggerd.  _(Mod 15 p50)_
#flashcard

Q:: User-specific logs
A:: User's home directory contains OS component and third-party applications' log information.  _(Mod 15 p50)_
#flashcard

Q:: Command line logs
A:: Look at the command line history for each user to check command line information.  _(Mod 15 p51)_
#flashcard

Q:: Mac Daily.out log
A:: These log files are generated based on the daily activities performed overnight when your system is running but not logged in. It stores network interface history.  _(Mod 15 p53)_
#flashcard

Q:: W3C Extended log file
A:: It is a customizable ASCII format with different properties, separated with spaces. This format enables removal of unwanted property fields to limit the log size.  _(Mod 15 p101)_
#flashcard

Q:: IIS log file format
A:: This format includes BASIC items such as client IP address, user information, date and time, service and instance, service status code, server name, and IP address, request type, number of bytes received, number of bytes sent, the target of operation, etc.  _(Mod 15 p103)_
#flashcard

Q:: NCSA Common log file format
A:: It records items related to user requests such as remote hostname, username, date, time, request type, HTTP status code, and the number of bytes sent by the server.  _(Mod 15 p104)_
#flashcard

Q:: Apache common log format
A:: In this log format, basic weblog parameters are included. It only displays information that is needed to determine the host and the request. Additionally, information about the agent, cookie string, domain name, referrer, time to serve, etc., is excluded in this format.  _(Mod 15 p109)_
#flashcard

Q:: Log generator
A:: This tier consists of the host that produces the log messages  _(Mod 15 p120)_
#flashcard

Q:: Log monitoring:
A:: he third tier consists of consoles that monitor and review the log data as well as the outputs of log analysis. These consoles are used to produce reports.  _(Mod 15 p120)_
#flashcard

Q:: Log collection
A:: Log collection is the process of collecting log messages from various sources to the database in a central location.  _(Mod 15 p121)_
#flashcard

Q:: Log transmission
A:: To store the logs in a centralized location, they are transmitted through different transport mechanisms such as syslog UDP, syslog TCP, encrypted syslog, etc.  _(Mod 15 p122)_
#flashcard

Q:: Log storage
A:: All the log files collected from various devices are stored in central repository/databases. Stored databases can be retrieved in structured way when needed.  _(Mod 15 p122)_
#flashcard

Q:: Log normalization
A:: Log normalization is the process of accepting logs from heterogeneous sources with different formats and converting them into a common format.  _(Mod 15 p122)_
#flashcard

Q:: Log correlation
A:: Log correlation is the process of matching a series of normalized log data to determine a set of related events based on a certain set of rules.  _(Mod 15 p122)_
#flashcard

Q:: Log analysis
A:: Log analysis is the process of identifying the patterns and anomalies in the correlated log data that signifies any intrusion attempt or policy violation activity.  _(Mod 15 p122)_
#flashcard

Q:: Alerting and reporting
A:: An alerting system generates alerts and sends a report to the user if any suspicious event is observed in the logs or calculated matrices.  _(Mod 15 p122)_
#flashcard

Q:: Evidence Examiner/Investigator:
A:: Evidence Examiner/Investigator examines the evidence acquired and sorts of useful evidence. Examines and sorts the evidence according to its relevance for the case. By maintaining an evidence hierarchy, the evidence examiner appropriately prioritizes the evidence.  _(Mod 16 p125)_
#flashcard

Q:: First responder
A:: he first responder is responsible for protecting, integrating, and preserving any evidence obtained from the crime scene.  _(Mod 16 p11)_
#flashcard

Q:: Evidence Manager
A:: The Evidence Manager manages the evidence so that it is admissible in a court of law.  _(Mod 16 p125)_
#flashcard

Q:: IR Manager
A:: The IR manager is a technical expert who understands security and incident management. They are responsible for the actions performed by the incident analysts and report the information to the incident officer.  _(Mod 16 p8)_
#flashcard

Q:: Forensic Investigation and Incident Containment
A:: Both are conducted simultaneously. IR helps organizations contain security events, but a computer forensic investigation enables investigators to find the root cause of the security issue.  _(Mod 16 p123)_
#flashcard

Q:: Evidence Investigator
A:: These examine the evidence acquired and sort useful evidence.  _(Mod 16 p124)_
#flashcard

Q:: Business Recovery
A:: An advance plan, arrangement, procedure to recover the business processes such as workspace, personnel, equipment, and facilities is called Business Recovery.  _(Mod 17 p7)_
#flashcard

Q:: Contingency Planning
A:: Contingency plans ensure continuous on-time product and service delivery, on-site and off-site business operations, and customer satisfaction.  _(Mod 17 p7)_
#flashcard

Q:: Emergency Management
A:: Emergency Management is the procedures and actions that are taken instantly after a crisis in order to safeguard people from harm.  _(Mod 17 p8)_
#flashcard

Q:: BCP
A:: Business continuity planning (BCP) is a document that is developed to ensure resilience from potential threats and allow business operations to continue under adversity.  _(Mod 17 p20)_
#flashcard

Q:: BCM
A:: Business continuity management is a process that ensures that business operations are not affected due to disruptive incidents.  _(Mod 17 p7)_
#flashcard

Q:: DRP
A:: A disaster recovery plan is documented instructions for responding to an unexpected disruptive event (recover from disaster).  _(Mod 17 p22)_
#flashcard

Q:: BIA
A:: BIA is a systematic process that determines and evaluates the potential effects of an interruption to critical business operations as a result of a disaster, an accident, or an emergency.  _(Mod 17 p10)_
#flashcard

Q:: ISO 22301:2019
A:: ISO 22301:2019 describes requirements to implement, maintain, and improve the management system to protect against, reduce the likelihood of the occurrence of, prepare for, respond to and recover from disruptions when they arise  _(Mod 17 p28)_
#flashcard

Q:: ISO 22313:2012
A:: ISO 22313:2012 guides ISO 22301 for setting up and managing effective business continuity and management system (BCMS).  _(Mod 17 p29)_
#flashcard

Q:: ISO/IEC 27031:2011
A:: ISO/IEC 27031:2011 describes the concepts and principles of information and communication technology (ICT) readiness for business continuity, provides a framework of methods and processes to identify and specify all aspects (such as performance criteria, design, and implementation) for improving an organization's ICT readiness to ensure business continuity  _(Mod 17 p30)_
#flashcard

Q:: Chief Information Officer
A:: The CIO is responsible for executing the policies and plans required for supporting the information technology and computer systems of an organization. The main responsibility of a CIO is to train employees and other executive management regarding the possible risks in IT and its impact on the business.  _(Mod 18 p8)_
#flashcard

Q:: IT Security Program Managers and Computer Security Officer
A:: ISSO provides the required support to information system owners with a selection of security controls needed for protecting a system. They also play an important role in the selection and amendment of security controls in an organization.  _(Mod 18 p9)_
#flashcard

Q:: Risk assessment
A:: Risk assessment determines the kind of risks present, the likelihood and severity of risk, priorities and plans for risk control. Risk assessment determines the types of risks that exist, likelihood and severity of risks, and priorities and plans for risk control. Decisions made in the risk treatment phase are based on the results of a risk assessment.  _(Mod 18 p15)_
#flashcard

Q:: Risk identification
A:: It is a process to list the risks and their characteristics before they cause harm to the organization. The techniques used for risk identification include checklists, flow charts, and systems analysis.  _(Mod 18 p14)_
#flashcard

Q:: Risk treatment
A:: t is the process of selecting and implementing appropriate controls on the identified risks in order to modify them.  _(Mod 18 p19)_
#flashcard

Q:: Risk tracking
A:: Risk tracking identifies the chance of a new risk and includes monitoring the probability, impact, status, and exposure of risk. helps a network defender identify the chances of a new risk occurring  _(Mod 18 p24)_
#flashcard

Q:: Risk review
A:: It enables the organization to keep the risk management objectives, and context up-to-date and accurate.  _(Mod 18 p24)_
#flashcard

Q:: Eliminate the risk
A:: It involves eliminating the risk by applying controls to reduce the threat of exploiting the vulnerability to zero.  _(Mod 18 p21)_
#flashcard

Q:: Reduce the risk
A:: It involves finding ways to reduce the likelihood rate of risk to an acceptable level  _(Mod 18 p21)_
#flashcard

Q:: Risk avoidance
A:: It involves avoiding the factor that enhances the risk factor of any process in the business or finding an alternative that goes well with business needs. For instance, not allowing the use of laptops in the organization to avoid the risks associated with the use of laptops.  _(Mod 18 p21)_
#flashcard

Q:: Mitigate the risk
A:: It involves reducing the risks associated with a threat or vulnerability by implementing direct or competing controls.  _(Mod 18 p21)_
#flashcard

Q:: Discovery
A:: This phase involves identification, consideration, and evaluation of network assets. It provides a hacker's view of the network.  _(Mod 18 p47)_
#flashcard

Q:: Assessment
A:: This phase involves scanning and evaluating a system for vulnerabilities  _(Mod 18 p46)_
#flashcard

Q:: Mitigation
A:: It is an action taken to prevent vulnerabilities from exploitation. It involves reducing the risk by taking other actions instead of correcting a discovered vulnerability.  _(Mod 18 p53)_
#flashcard

Q:: Verification
A:: This phase involves monitoring network continuously to check for new vulnerabilities.  _(Mod 18 p46)_
#flashcard

Q:: Internal vulnerability assessment
A:: An internal vulnerability assessment evaluates a network for the presence of internal vulnerabilities.  _(Mod 18 p61)_
#flashcard

Q:: External vulnerability assessment
A:: An external vulnerability assessment evaluates the security profile of an organization from the perimeter of the network.  _(Mod 18 p59)_
#flashcard

Q:: Web vulnerability assessment
A:: It involves crawling the website in order to discover potential vulnerabilities, and then report these results.  _(Mod 18 p63)_
#flashcard

Q:: Attack Surface Visualization
A:: This step involves mapping out all devices, paths, and networks.  _(Mod 19 p9)_
#flashcard

Q:: IoEs' Identification
A:: In this step, potential risk exposures that attackers can use to breach the security of an organization are identified.  _(Mod 19 p9)_
#flashcard

Q:: Attack Simulation
A:: This step involves recognizing how the identified IoE could turn to exploit.  _(Mod 19 p9)_
#flashcard

Q:: Attack Surface Reduction
A:: This step involves implementing appropriate security controls and countermeasures to reduce the attack surface of a system.  _(Mod 19 p9)_
#flashcard

Q:: Conduct Attack Simulation
A:: It helps a network defender validate and manage the security controls across the organization. It enables a network defender to assess the security flaws before any attack takes place.  _(Mod 19 p34)_
#flashcard

Q:: Cloud to User
A:: This refers to the attacks that a Cloud service faces from a user's point of view. This attack surfaces in cloud computing is difficult to define  _(Mod 19 p52)_
#flashcard

Q:: User to Cloud
A:: This pertains to the different types of attack vectors that target a user. It has its origins in the Cloud system. For example, phishing-like attempts that present users a fake usage bill of the Cloud provider.  _(Mod 19 p52)_
#flashcard

Q:: Cloud to Service
A:: It is related to exposing Cloud resources/interfaces to service instances. For example, resource exhaustion, triggering the Cloud provider to provide more resources or end up in a Denial-of-Service (DoS), and attacks on the Cloud system hypervisor. it slightly tricky to separate the service and cloud  _(Mod 19 p51)_
#flashcard

Q:: Service to Cloud
A:: It is related to exposing the service instance to the Cloud provider. Examples include availability reductions, privacy attacks, malicious interference, data integrity attack, data confidentiality attack, etc.  _(Mod 19 p51)_
#flashcard

Q:: IoT Applications and Software Vulnerabilities
A:: Attacks can exploit vulnerabilities in application interfaces and the software of IoT devices. These can compromise systems, steal sensitive or personal data (credentials), or insert malicious firmware updates.  _(Mod 19 p54)_
#flashcard

Q:: IoT Device Vulnerabilities
A:: The parts of a device from which vulnerabilities emerge are physical interfaces (USB ports), failures in memory, firmware, web interface, admin interfaces, and network services.  _(Mod 19 p54)_
#flashcard

Q:: IoT Communication Channel Vulnerabilities
A:: Attacks can occur due to the ways in which IoT components connect with each other. For example, protocols used in IoT systems, Bluetooth, and Wi-Fi can be exposed to vulnerabilities.  _(Mod 19 p54)_
#flashcard

Q:: IoT Cloud Interface Vulnerabilities
A:: Attacks are triggered by inadequate passwords, default credentials, and insecure transport encryption in using Cloud interfaces for IoT.  _(Mod 19 p54)_
#flashcard

Q:: IoT Device Memory Vulnerabilities
A:: It has the possibility of possessing clear-text credentials stored in memory and the monitoring of cipher keys.  _(Mod 19 p55)_
#flashcard

Q:: IoT Device Web Interface
A:: It comprises the web application vulnerabilities of the IoT device web interface and credential management.  _(Mod 19 p55)_
#flashcard

Q:: IoT Device Firmware
A:: It has the possibility of vulnerabilities in the device firmware that provides the features and functions for a solution.  _(Mod 19 p56)_
#flashcard

Q:: IoT Device Physical Interface
A:: It comprises the vulnerabilities in unsecured elements, which are used to compromise IoT devices.  _(Mod 19 p55)_
#flashcard

Q:: Strategic Threat Intelligence collection sources
A:: This intelligence is collected from sources such as open-source intelligence (OSINT), CTI vendors, and Information Sharing and Analysis Organizations (ISAOs) / Information Sharing and Analysis Centers (ISACs).  _(Mod 20 p11)_
#flashcard

Q:: Tactical Threat Intelligence collection sources
A:: The collection sources for tactical threat intelligence include campaign reports, malware, incident reports, attack group reports, human intelligence, etc. This intelligence is generally obtained by reading white/technical papers, communicating with other organizations, or purchasing intelligence from third parties.  _(Mod 20 p12)_
#flashcard

Q:: Operational Threat Intelligence collection sources
A:: Operational threat intelligence is generally collected from sources such as humans, social media, and chat rooms, and also from real-world activities and events that result in cyber-attacks.  _(Mod 20 p13)_
#flashcard

Q:: Indicators of Exposure (IoE)
A:: It shows potentially exploitable vectors before an incident takes place and helps in understanding the security posture of the organization and making more informed decisions to prevent the breaches in advance.  _(Mod 19 p19)_
#flashcard

Q:: Indicators of Attacks (IoAs)
A:: It reveals an active attack before IoCs become visible  _(Mod 20 p21)_
#flashcard

Q:: Indicators of Compromise (IoCs)
A:: IoCs are the technical indicators of threat and are discovered through the investigation after the occurrence of an incident or through the alerts if the network is monitored?  _(Mod 20 p16)_
#flashcard

Q:: Key Risk Indicators (KRIs)
A:: KRIs are the most important indicators of an organization's overall health, it helps in reducing loss and prevents risk exposure.  _(Mod 18 p10)_
#flashcard

Q:: OpenIOC
A:: It is a format of IoC with its XML-based framework to describe the complex semantics of the malware behavior.  _(Mod 20 p17)_
#flashcard

Q:: CybOX
A:: CybOX (Cyber Observable Expression) provides a standard for defining indicator details (observables) regarding measurable events and stateful properties and mainly aims at automating the sharing of security information by providing more than 70 defined objects.  _(Mod 20 p17)_
#flashcard

Q:: MAEC
A:: MAEC (Malware Attribute Enumeration and Characterization) is a standardized language to describe CTI.  _(Mod 20 p18)_
#flashcard

Q:: TAXII
A:: TAXII (Trusted Automated eXchange of Indicator Information) is a set of specifications for exchanging cyber threat information over HTTPS. TAXII uses XML and HTTP for message content and transport. It is specially created to support the exchange of CIT represented in STIX.  _(Mod 20 p18)_
#flashcard

## Revision - not for drilling

> [!failure] 19 cards that did not fully verify
> These are **not** tagged `#flashcard`, so they stay out of your review sessions.
> The reason names the specific claim the courseware does not back, so you can judge
> each one yourself instead of taking my word for it.

**Card 4** - Message Digest Algorithm 5

Q:: Message Digest Algorithm 5
A:: Hash functions calculate a unique fixed-size bit string representation, called a message digest, of any arbitrary block of information. It is also one-way hash but is not published by NIST.  _(Mod 03 p92)_

- Gap: Card adds *not published by NIST*. The courseware says nothing about publication.

**Card 15** - Firewall Analyzer

Q:: Firewall Analyzer
A:: automates the end point security monitoring, network bandwidth monitoring, security, and compliance auditing.  _(Mod 04 p64)_

- Gap: Courseware credits *automates threat remediation*; the bandwidth and compliance framing is not there.

**Card 17** - SonicWALL firewall

Q:: SonicWALL firewall
A:: is a tool that supports network security, secured remote access, and data protection. It applies Unified Threat Management (UTM) against an array of attacks, combining intrusion prevention, anti-virus and antispyware with application-level control of SonicWALL Application Firewall. It provides services for network firewalls, UTMs (Unified network management), VPNs (Virtual Private Network), backup and recovery, and anti-spam for email.  _(Mod 04 p36)_

- Gap: SonicWall is named only as an example vendor. The UTM / VPN / anti-spam list is not in the courseware.

**Card 29** - Windows User Account Control (UAC)

Q:: Windows User Account Control (UAC)
A:: can restrict access to system files and system-wide settings by implementing a sandbox.  _(Mod 05 p98)_

- Gap: UAC is confirmed. The *sandbox mechanism* framing is not part of its definition.

**Card 55** - OpenSCAP

Q:: OpenSCAP
A:: It is a standard security specification maintained by the NIST which can handle multiple security issues on the host machine by supporting various activities for host safety, such as patch checking, vulnerability checking, technical control and compliance activities, and security measurement.  _(Mod 06 p119)_

- Gap: Courseware says **SCAP**, the standard. The tool **OpenSCAP** is never named.

**Card 66** - Application delivery

Q:: Application delivery
A:: MAM solutions are used by admins for application delivery to mobile devices.  _(Mod 07 p38)_

- Gap: MAM is confirmed as *secure, manage, distribute* of enterprise apps. The *application delivery* list is not.

**Card 79** - validating parsers using Document Type Definitions (DTD) and XML Schemas in IoT

Q:: validating parsers using Document Type Definitions (DTD) and XML Schemas in IoT
A:: This will mitigate Xmpp bomb attacks  _(Mod 08 p47)_

- Gap: DTD and XML-schema parser validation is confirmed. The link to the XMPP Bomb attack is not stated.

**Card 95** - NIST

Q:: NIST
A:: NIST developed Systems Security Engineering 800.160, IoT.  _(Mod 08 p121)_

- Gap: The NIST IoT topic is real, but the courseware never mentions **800.160**.

**Card 107** - Sandbox feature for Microsoft Edge

Q:: Sandbox feature for Microsoft Edge
A:: Protection Mode  _(Mod 09 p53)_

- Gap: Protected Mode / UAC / low integrity level is confirmed. Attributing it to Edge specifically is loose.

**Card 132** - changing default password and using strong password

Q:: changing default password and using strong password
A:: This countermeasure mitigates password guessing brute force attacks.  _(Mod 05 p76)_

- Gap: Strong-password guidance is confirmed. That it *prevents* brute force is not stated.

**Card 162** - 802.15

Q:: 802.15
A:: It defines the standards for a wireless personal area network (WPAN). It describes the specification for wireless connectivity with fixed or portable devices.  _(Mod 13 p11)_

- Gap: 802.15 is confirmed as the WPAN standard. *Fixed or portable devices* is not in the table.

**Card 163** - Context-based signature

Q:: Context-based signature
A:: Packets are usually altered using the header information. Suspicious signatures in the header can include malicious data. This type of signature CANNOT open backdoors in a system if not detected.  _(Mod 14 p21)_

- Gap: Context-based signatures are confirmed. *Cannot open backdoors* applies to undetected signatures, not this type.

**Card 167** - tcp.flags==0x00

Q:: tcp.flags==0x00
A:: detect TCP-based OS fingerprinting attempts.  _(Mod 14 p10)_

- Gap: The OS-fingerprint filter lost its text to OCR; no literal `tcp.flags==0x00` survives in the courseware.

**Card 169** - tcp.flags==0x012

Q:: tcp.flags==0x012
A:: This filter is used to detect full TCP scan attempts.  _(Mod 14 p45)_

- Gap: The full-connect scan is confirmed. The filter value `tcp.flags==0x012` is not in the courseware.

**Card 187** - Log analysis

Q:: Log analysis
A:: This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server  _(Mod 15 p119)_

- Gap: The courseware has **one** tier, *Log analysis and storage*. The card splits it.

**Card 188** - Log storage

Q:: Log storage
A:: This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server.  _(Mod 15 p119)_

- Gap: Same: *Log analysis* and *Log storage* are a single tier, not two.

**Card 197** - 1st rule of the First Responder

Q:: 1st rule of the First Responder
A:: Prevent attempts to retrieve data by unqualified individuals  _(Mod 16 p12)_

- Gap: Courseware calls it the *First Response Rule* and says attempts are *avoided*, not *prevented*.

**Card 207** - Disaster Recovery

Q:: Disaster Recovery
A:: DR is a plan to restore important support systems such as hardware, IT assets, and communications. The goal of disaster recovery is to reduce business downtime and to restore technical operations in a short stint of time.  _(Mod 17 p8)_

- Gap: Confirmed, but the courseware wording is *reduce business downtime and accelerate the restoration*.

**Card 215** - ISO 22313:2020

Q:: ISO 22313:2020
A:: ISO 22313: 2020 provides guidance and recommendations for applying BCMS requirements that are given in ISO 22301.  _(Mod 17 p27)_

- Gap: **The courseware says ISO 22313:2012.** The card's `:2020` is wrong.

---

Dropped, no basis in the courseware: card 16 WinGate Proxy Server, card 256 Dynamic Threat Intelligence

Dropped, redundant repeat of another card already in the deck:
- card 42 rwx------ - card 47 is kept instead (same or fuller text)
- card 44 rwxr-xr-x - card 48 is kept instead (same or fuller text)
- card 232 Risk assessment - card 218 is kept instead (same or fuller text)
- card 240 IoEs' Identification - card 236 is kept instead (same or fuller text)
