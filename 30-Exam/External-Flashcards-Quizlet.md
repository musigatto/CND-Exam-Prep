---
type: question
module: "ext"
tags: [exam]
topic: "External Flashcards - Quizlet set 617277655 (third-party)"
exam_weight: unknown
status: draft
unresolved:
  - "Source is a third-party Quizlet set, NOT the 20 module PDFs. Kept out of 20-Notes/ per AGENTS.md traceability rule."
  - "Cards whose definition is an inline MCQ have no stated answer; see ## MCQ cards without a stated answer."
---
# External Flashcards - Quizlet

> [!warning] Provenance
> Harvested by the user from Quizlet set `617277655` ("CND Study for Practice Test"), 264 cards.
> Not derived from the courseware PDFs, so this file is **separate** from the PDF-built note tree.
> Verbatim: typos in the source are preserved (e.g. "Pretty Good Service (PGP)" at card 9).
> One export corruption repaired: card 45 term was `rw-r<U+2014>r--` (em-dash for the 3 hyphens), restored to `rw-r--r--` per that card's own definition.

Cards: 264.  Source: https://quizlet.com/617277655/

Q:: Low-interaction Honeypot
A:: From the following, identify the type of honeypot which generally fakes those services that are frequently asked by the attacker. They are essentially a single machine with multiple virtual machines. Low-interaction Honeypot Pure Honeypot High-interaction Honeypot Production Honeypot

Q:: Public key infrastructure
A:: is treated as the most effective method for providing verification during electronic transactions

Q:: Secure Hashing Algorithm (SHA)
A:: generate a cryptographically one-way hash and is published by NIST as a Federal Information Standard

Q:: Message Digest Algorithm 5
A:: Hash functions calculate a unique fixed-size bit string representation, called a message digest, of any arbitrary block of information. It is also one-way hash but is not published by NIST.

Q:: Digital Signature Algorithm
A:: It is a Federal Information Processing Standard (FIPS) for digital signatures.

Q:: AES
A:: is a National Institute of Standards and Technology (NIST) specification for the encryption of electronic data and is being used by U.S. government agencies to secure sensitive but unclassified material

Q:: SSL
A:: Secure Sockets Layer (SSL) works at the transport layer.

Q:: IPSec
A:: Internet Protocol Security (IPSec) works at the network layer

Q:: PGP
A:: Pretty Good Service (PGP) protocol works at the application layer.

Q:: S/MIME
A:: Secure/Multi-Purpose Internet mail Extension (S/MIME) works at the application layer

Q:: Network Address Translation (NAT)
A:: firewall technology helps hide the internal network's configuration and thereby reduces the success of attacks on the network or system. It can act as a firewall filtering technique where it allows only those connections that originate inside a network and can block the connections that originate outside the network.

Q:: Application-level gateway
A:: is a firewall that controls input, output, and/or access across an application or service. It monitors and possibly blocks the input, output, or system service calls, which do not meet the policy of the firewall.

Q:: Application proxy
A:: An application-level proxy works as a proxy server. It correlates with the gateway server and separates the enterprise network from the Internet.

Q:: Stateful multi-layer inspection
A:: These firewalls filter packets at the network layer, determine whether session packets are legitimate, and evaluate the contents of packets at the application layer.

Q:: Firewall Analyzer
A:: automates the end point security monitoring, network bandwidth monitoring, security, and compliance auditing.

Q:: WinGate Proxy Server
A:: sophisticated integrated Internet gateway and a communications server designed to meet the control, security, and communication needs for businesses.

Q:: SonicWALL firewall
A:: is a tool that supports network security, secured remote access, and data protection. It applies Unified Threat Management (UTM) against an array of attacks, combining intrusion prevention, anti-virus and antispyware with application-level control of SonicWALL Application Firewall. It provides services for network firewalls, UTMs (Unified network management), VPNs (Virtual Private Network), backup and recovery, and anti-spam for email.

Q:: Firewalk
A:: is used for reconnaissance purpose where it discovers firewall rules using an IP TTL expiration technique.

Q:: Security Reference Monitor (SRM)
A:: enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.

Q:: Local Security Authority Subsystem (LSASS)
A:: implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.

Q:: Security Accounts Manager (SAM)
A:: is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.

Q:: Windows Integrity Control (WIC)
A:: is an access control mechanism for controlling the interactions between objects based on their integrity or level of trustworthiness.

Q:: User Account Control (UAC)
A:: is a key access control enforcement feature in Windows that improves the security of the OS by limiting application software to standard user privileges until an administrator authorizes an elevation

Q:: Network logon service (NetLogon)
A:: a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.

Q:: Windows logon application (WinLogon)
A:: used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background

Q:: Just Enough administration (JEA)
A:: a security technology used to limit the number of cmdlets or administration privileges of administrator, user, or service accounts.

Q:: SID
A:: To troubleshoot user or object access issues across the domain system, the administrator needs to view the SID of users or group.

Q:: RID
A:: Every SID contains a relative identifier (RID) at the end, and attackers try to access the list of SIDs to try and replace the RID with an administrative account's details so that they can get access to administrative privileges.

Q:: Windows User Account Control (UAC)
A:: can restrict access to system files and system-wide settings by implementing a sandbox.

Q:: Microsoft Windows Defender Credential Guard (WDCG)
A:: protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.

Q:: CPs
A:: a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.

Q:: Network Level Authentication (NLA)
A:: s implemented to send the user credentials securely from the client side using a security service provider of the client and make the user to authenticate before the session gets started.

Q:: Enabling Remote Credential Guard
A:: If Remote Credential Guard is enabled, the connection to the other systems using single sign-on will be active only when the host supports it.

Q:: sudo apt autoclean
A:: clean partial packages

Q:: sudo apt-get clean
A:: This command cleans the apt cache

Q:: sudo apt autoremove application-name
A:: uninstalls or removes unnecessary packages

Q:: NIS-Server
A:: The NIS-Server tends to distribute system configuration files. Also, it is an insecure system that has been vulnerable to DoS attacks, buffer overflows and poor authentication for querying NIS maps.

Q:: Telnet-Server
A:: It comprises the telnetd daemon, which allows connections from users from other systems through the telnet protocol. The insecure and unencrypted telnet protocol could allow access to sniff network traffic, which can steal the credentials.

Q:: RSH-Server
A:: The Berkeley rsh-server (rsh, rlogin, rcp) package comprises legacy services that exchange credentials in clear-text. This service comprises many security exposures that can be exploited.

Q:: TFTP-Server
A:: The file transfer protocol 'Trivial File Transfer Protocol (TFTP)' is used to transfer configuration or boot machines from a boot server automatically. It does not support authentication and ensure the confidentiality of data integrity.

Q:: rwxrwxrwx
A:: no restrictions on anything. Anybody can do anything

Q:: rwx------
A:: The file owner may read, write, and execute the file. Nobody else has any rights.

Q:: rw-rw-rw
A:: All users can read and write the file

Q:: rwxr-xr-x
A:: The file owner may read, write, and execute the file. Others can read and execute the file. This setting is useful for all programs that are used by all users.

Q:: rw-r--r--
A:: The owner can read and write a file, while others may only read the file. A very common setting where everybody may read but only the owner can make changes.

Q:: rw-------
A:: Owner can read and write a file. Others have no rights. A common setting for files that the owner wants to keep private.

Q:: rwx------
A:: The file owner may read, write, and execute the file. Nobody else has any rights. This setting is useful for programs that only user may use and are kept private from others.

Q:: rwxr-xr-x
A:: The file owner may read, write, and execute the file. Others can read and execute the file. This setting is useful for all programs that are used by all users.

Q:: iptables -A INPUT -p icmp -i eth0 -j DROP
A:: blocks incoming ping requests

Q:: iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP
A:: This command will block XMAS scan attack

Q:: ptables -A INPUT -i eth0 -s xxx.xxx.xxx.xxx -j DROP
A:: block connection on network interface

Q:: Lynis
A:: Lynis can perform an extensive health scan of systems to support system hardening and compliance testing.

Q:: AppArmor
A:: Linux security module that allows a system administrator to restrict programs' capabilities with per-program profiles. It is utilized by the system administrator to restrict programs to a limited set of resources.

Q:: SELinux
A:: It is a mandatory access control (MAC) module that resides in the kernel level of Linux systems. It decides which process can access which files, directories and ports and provides an additional layer of system security.

Q:: OpenSCAP
A:: It is a standard security specification maintained by the NIST which can handle multiple security issues on the host machine by supporting various activities for host safety, such as patch checking, vulnerability checking, technical control and compliance activities, and security measurement.

Q:: CYOD policy
A:: The CYOD policy allows employees to choose devices (laptops, smartphones, and tablets) from a preapproved set of devices to access company data as per the organization's access privileges.

Q:: BYOD policy
A:: The BYOD policy allows employees to use the devices that they are comfortable with and best fits their preferences and work purposes.

Q:: COBO policy
A:: The COBO policy allows employees to use and manage devices purchased by the organization but restricts the use of the device for business use only.

Q:: COPE policy
A:: The COPE policy allows employees to use and manage devices purchased by the organizations. Larger enterprises are more likely to employ the COPE model. COPE reduces the risks associated with BYOD by implementing stringent policies and protecting devices.

Q:: MEM
A:: An MEM solution ensures the security of the corporate email infrastructure and data on mobile devices.

Q:: MDM
A:: An MDM solution is used to deploy, secure, monitor, and manage company-owned and employee-owned devices.

Q:: UEM
A:: An UEM solution helps in managing and controlling internet-enabled mobile devices, desktops, applications, and content across the organization from a single interface.

Q:: MAM
A:: An MAM solution enables an organization to secure, manage, and distribute enterprise applications on user mobile devices, without interfering with personal apps and data.

Q:: Data leaks identification
A:: MTD solutions can be used by admins to identify data leaks to block access to the risky content.

Q:: Location-based content delivery
A:: MCM solutions are used by admins for location-based content delivery.

Q:: Application delivery
A:: MAM solutions are used by admins for application delivery to mobile devices.

Q:: App wrapping
A:: MAM solutions are used by admins for app wrapping.

Q:: IoT User applications
A:: These applications help change the behavior of the application controls.

Q:: IoT Control applications
A:: Control applications send automatic commands and alerts to actuators and helps in investigating problematic cases and enhancing security by identifying security breaches.

Q:: IoT Gateways
A:: Gateways are devices through which data are transmitted from things to the cloud and vice versa.

Q:: IoT Streaming data processors
A:: These processors ensure that no data can be lost or corrupted

Q:: IoT Cloud layer
A:: his layer consists of servers hosted in the cloud that accept, store, and process the sensor data received from IoT gateways.

Q:: IoT Communication layer
A:: The communication layer includes the components of communication protocols and networks used for connectivity and edge computing.

Q:: IoT Device Layer
A:: The device or the Thing layer of IoT includes the hardware that constitutes IoT devices.

Q:: IoT Process Layer
A:: The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.

Q:: Installing an IoT firewall
A:: will mitigate malicious scripts attack

Q:: Implementing a strong IoT encryption scheme
A:: prevents attacks like cryptanalysis attacks

Q:: implementing high data privacy and privilege levels for IoT
A:: prevents social engineering attacks.

Q:: validating parsers using Document Type Definitions (DTD) and XML Schemas in IoT
A:: This will mitigate Xmpp bomb attacks

Q:: Device-to-Device model
A:: In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.

Q:: Device-to-Cloud model
A:: In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.

Q:: Cloud-to-Cloud model
A:: his type of communication model extends the device-to-cloud communication type in which the data from IoT devices can be accessed by authorized third parties. Here, devices upload their data onto the cloud, and the data is accessed or analyzed later by third parties.

Q:: Device-to-Gateway model
A:: In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.

Q:: Monitoring bandwidth consumption of IoT devices
A:: Monitoring bandwidth consumption helps to know how much data is used or sent by IoT device, and to know the download and upload bandwidth consumption of devices in the IoT network.

Q:: Implementing end-to-end (E2E) security and identity management
A:: It will provide security and privacy in the IoT device and to maintain trust.

Q:: Constructing virtual LAN pipe
A:: Virtual LAN pipe should be constructed on the fly with each new IoT device connection that would allow IP-based communication to only one endpoint - the publicly facing internet

Q:: Monitoring the behaviour of IoT device
A:: Monitoring the behaviour of the IoT device provides full visibility and insights of the IoT assets, so that the organization can quickly react to mitigate the risks and resolve an issue before it impact the business.

Q:: Domotz
A:: It is an IoT monitoring and management tool.

Q:: SeaCat.io
A:: It is a security-first SaaS technology to operate IoT products in a reliable, scalable and secure manner.

Q:: DigiCert IoT Security Solutions
A:: It protect private data and home networks while preventing unauthorized access using PKI-based security solutions for consumer IoT devices.

Q:: beSTORM
A:: It is an IoT vulnerability scanning tool

Q:: GSMA
A:: GSMA developed IoT Security Guidelines and IoT Security Assessment that help create a secure IoT market with trusted, reliable services that can scale as the market grows.

Q:: AT&T
A:: AT&T developed The CEO's Guide to Securing the Internet of Things

Q:: U.S Department of Homeland Security
A:: U.S DHS developed Strategic Principles for Securing the Internet of Things.

Q:: NIST
A:: NIST developed Systems Security Engineering 800.160, IoT.

Q:: ENISA
A:: ENISA developed 'Baseline Security Recommendations for Internet of Things

Q:: dm-crypt
A:: dm-crypt is a transparent disk encryption subsystem in Linux kernel versions 2.6 and later. This command is used for disk encryption in Linux.

Q:: JTAG
A:: It is a standard interface to test and debug chips with debugging software to know how a chip respond to multiple commands.

Q:: Application Whitelisting
A:: The approach of application whitelisting is trust centric. By default, applications that are not in the whitelist are prevented from being executed.

Q:: Application Blacklisting
A:: Application blacklisting is threat centric. By default, it allows all applications that are not in the blacklist to be executed.

Q:: Application Sandboxing
A:: Application sandboxing is the process of running applications in a sealed container (sandbox) so that the applications cannot access critical system resources and other programs.

Q:: Application Patch Management
A:: Application patch management is the process of ensuring the security of applications on hosts by regularly deploying new or missing patches.

Q:: AppLocker
A:: When AppLocker rules are enforced, apps excluded from the list of allowed apps are prevented from running.

Q:: Group Policy Settings
A:: Group Policy Settings can enable blocking software installation.

Q:: Registry Editor
A:: Network defenders can block the execution of an application on a system by disabling the application using the Windows Registry Editor.

Q:: Windows Defender Application Guard
A:: Windows Defender Application Guard (WDAG) isolates Microsoft Edge and blocks websites from accessing the local storage, memory, installed apps, and corporate network endpoints.

Q:: Sandbox feature for Microsoft Edge
A:: Protection Mode

Q:: Sandbox for FireFox
A:: Content Process Sandbox Level

Q:: Sandbox for Chrome
A:: Strict-Origin-Isolation

Q:: Toggling feature controls of Sandbox Protections
A:: Used for Acrobat Reader

Q:: Microsoft URLScan
A:: is a WAF tool that analyzes and filters all Hypertext Transfer Protocol (HTTP) requests received by the Internet Information Service (IIS) web service and protects web applications against Structured Query Language (SQL) injection or cross-site scripting (XSS) attacks.

Q:: # setfacl -x u:guest test
A:: remove all access ACL rules of test file for the guest user.

Q:: # setfacl -b u:guest test
A:: remove all ACL of test file for the guest user

Q:: # setfacl -m u:user1:rwx test
A:: set read and write permission in the ACL of test file for the guest.

Q:: # setfacl -m d:o:rx /Testdir
A:: This command is used to set default ACL for test directory.

Q:: RAID 1
A:: RAID level 1 provides data reliability since failure of one disk can still provide access to the same data mirrored on the other disks. In a RAID 1 hardware implementation, a minimum of two disks is required. RAID Level 1 undergoes duplexing, which is the need for twice the amount of disk space for storage.

Q:: RAID 50
A:: RAID level 50 includes mirroring and striping across multiple RAID levels. This level is a combination of the block level striping of level 0 and the distributed parity of level 5. The configuration of RAID level 50 requires a minimum of six drives. This level undergoes a hot swapping process when a disk fails.

Q:: SMB
A:: Server message block store virtual machine files such as configuration, Virtual Hard Disk (VHD) files, and snapshots in file shares.

Q:: IPAM
A:: IP Address Management drivers exist in Docker that provides default subnets or IP addresses to the network and the endpoints.

Q:: NFV
A:: Network Function Virtualization (NFV) is a network virtualization approach, which separates the network functions (NFs) such as firewalls, traffic control, virtual routing, etc., from physical devices and runs them as software in virtual resources.

Q:: IUM
A:: The Isolated User Mode (IUM) feature was introduced particularly for Windows 10 Enterprise version and Windows Server 2016. It is a virtualization-based security feature that utilizes the secure kernels and separates business data and processes from the operating system.

Q:: -mds-clear-on-vm-entry
A:: command in the VirtualBox, the affected buffer will be cleared on every VM entry.

Q:: BPDU Guard
A:: avoids accidental connection of switch ports with PortFast-enabled and prevents Layer 2 loops or topology changes.

Q:: BPDU Filter
A:: It will disable STP on selected ports by stopping the port from sending/receiving BPDUs

Q:: Root Guard
A:: It prevents the switches that are configured as access ports from becoming the root switch.

Q:: Loopguard and UDLD
A:: Prevents bridging loops occurred due to unidirectional links.

Q:: --l1d-flush-on-vm-entry
A:: This command flushes the level 1 data cache from every VM entry.

Q:: Application Plane
A:: This SDN component support different applications: Routing, load balancers, monitoring, security, etc.

Q:: Control Plane
A:: This SDN component provide abstract view of the network (the network model).

Q:: Data Plane
A:: This SDN component perform packet forwarding according to instruction stored in flow tables.

Q:: Open flow
A:: This SDN component is a communication protocol to manage the Southbound interface of the SDN.

Q:: changing default password and using strong password
A:: This countermeasure mitigates password guessing brute force attacks.

Q:: implementing role-based source authentication
A:: This countermeasure mitigates misconfiguration attacks

Q:: implementing software attestation to authenticate each application
A:: This countermeasure mitigates malicious application attacks

Q:: implementing rate limiting and packet dropping techniques at the controller plane
A:: This countermeasure mitigates DDoS attacks.

Q:: Orchestrator
A:: It controls orchestration, manages software resources, and NFV infrastructure.

Q:: VNF Manager(s)
A:: Manages the life cycle of VNF such as updates, query, installation, termination, scale-up/down.

Q:: Element Management System (EMS)
A:: It handles the management function of VNF such as Accounting, Configuration, Performance and Security Management, etc.

Q:: Virtualized Infrastructure Manager(s)
A:: The function of VIM is to control and manage the communication between VNF with computing, storage, and network resources along with virtualization.

Q:: etcd
A:: It is a backing store for Kubernetes Cluster data

Q:: Kube-scheduler
A:: It monitors the newly created pods, which are not having any assigned nodes.

Q:: Kube-controller-manager
A:: It runs the controller processes.

Q:: Cloud-controller-manager
A:: It runs the controller that communicates with the cloud providers.

Q:: cloud broker
A:: entity that manages cloud services regarding the usage, performance, and delivery, and maintains the relationship between the CSPs and cloud consumers.

Q:: cloud auditor
A:: It is a party that independently examines the cloud service controls to express a corresponding opinion.

Q:: cloud carrier
A:: It acts as an intermediary that provides connectivity and transport services between the CSPs and cloud consumers

Q:: cloud provider
A:: It manages the computing infrastructure intended for providing services (directly or via a cloud broker) to the interested parties via network access.

Q:: Azure Key Vault
A:: It is a secure storage for the keys used to encrypt the data at rest in Azure services.

Q:: Azure Disk Encryption
A:: It can be performed through the Azure Key Vault to control and manage the encrypted keys.

Q:: Azure Transparent Data Encryption (TDE)
A:: It is an SQL Azure feature to encrypt data at both the database and server levels.

Q:: Azure Storage Service Encryption (SSE)
A:: It automatically encrypts the data during storage and decrypts the data at the time of retrieval. It is applied to the entire storage system of Microsoft Azure, and users can enable or disable this feature.

Q:: Google Cloud Armor
A:: It is to defend DDoS attacks.

Q:: Google VPS
A:: It helps in regulating the communication of VM-based applications by setting firewall rules.

Q:: Google Stackdriver
A:: It is to monitor, diagnose, and fix applications across the GCP.

Q:: Google Cloud NAT
A:: It allows private VMs or private GKE clusters to connect to the internet. It minimizes the access paths and public IPs.

Q:: Google Cloud Shared VPC
A:: It can configure and centrally manage one or more virtual networks across multiple projects in an organization for secured and efficient communication by utilizing internal IPs.

Q:: Google Cloud Routes
A:: These are the paths taken by the network traffic from a VM instance to reach another destination.

Q:: Google Cloud VPC
A:: It is network is a virtual representation of the physical network, which connects VM instances, GKE clusters, App Engine, and other resources of a project.

Q:: 802.11i
A:: It is used as a standard for WLANs and provides improved encryption for networks. 802.11i requires new protocols such as TKIP, AES.

Q:: 802.16
A:: It is also known as Wi-Max. This standard is a specification for fixed broadband wireless metropolitan access networks (MANs) that use a point-to-multi-point architecture.

Q:: 802.11e
A:: It defines the Quality of Service (QoS) for wireless applications. The standard maintains the quality of video and audio streaming, real time online applications, VoIP, etc.

Q:: 802.15
A:: It defines the standards for a wireless personal area network (WPAN). It describes the specification for wireless connectivity with fixed or portable devices.

Q:: Context-based signature
A:: Packets are usually altered using the header information. Suspicious signatures in the header can include malicious data. This type of signature CANNOT open backdoors in a system if not detected.

Q:: Content-based signature
A:: Content-based signatures are detected by analyzing the data in the payload and matching a text string to a specific set of characters. If undetected, these signatures can open backdoors in a system, providing administrative controls to an outsider.

Q:: Atomic signature
A:: To detect an atomic signature, administrators need to analyze a single packet to determine if the signature includes malicious patterns.

Q:: Composite signature
A:: Administrators need to analyze a series of packets over a long period of time to detect attack signatures.

Q:: tcp.flags==0x00
A:: detect TCP-based OS fingerprinting attempts.

Q:: tcp.dstport==7
A:: detect TCP ping sweep attempts

Q:: tcp.flags==0x012
A:: This filter is used to detect full TCP scan attempts.

Q:: udp.dstport==7
A:: detect UDP ping sweep attempts.

Q:: TCP null scan attempt
A:: can penetrate through a router and a firewall that filter incoming packets with particular flags set because null scan does not contain any set flag and it is not supported by Windows.

Q:: icmp.type==3 and icmp.code==3
A:: detect UDP scan attempts using Wireshark

Q:: Centralized Logging
A:: records changes to firewall policy collects and aggregates logs in one central location works in four parts: log collection, transport, storage, and analysis

Q:: Local Logging
A:: used by the systems that have a limited number of hosts

Q:: Push-based mechanism
A:: In a push-based mechanism, the system or application either saves records on the local disk or sends them over the network.

Q:: Pull-based mechanism
A:: In a pull-based mechanism, a system or an application pulls the log records from a log source. It works based on the client-server model. The system or device that follows this mechanism usually stores their log data in a proprietary format.

Q:: Mac Security logs
A:: contains information about login/logout activities and helps in determining attempted and successful unauthorized activities.

Q:: Mac Firewall logs
A:: It is a built-in firewall that can log a large amount of data using a program called appfwloggerd.

Q:: User-specific logs
A:: User's home directory contains OS component and third-party applications' log information.

Q:: Command line logs
A:: Look at the command line history for each user to check command line information.

Q:: Mac Daily.out log
A:: These log files are generated based on the daily activities performed overnight when your system is running but not logged in. It stores network interface history.

Q:: W3C Extended log file
A:: It is a customizable ASCII format with different properties, separated with spaces. This format enables removal of unwanted property fields to limit the log size.

Q:: IIS log file format
A:: This format includes BASIC items such as client IP address, user information, date and time, service and instance, service status code, server name, and IP address, request type, number of bytes received, number of bytes sent, the target of operation, etc.

Q:: NCSA Common log file format
A:: It records items related to user requests such as remote hostname, username, date, time, request type, HTTP status code, and the number of bytes sent by the server.

Q:: Apache common log format
A:: In this log format, basic weblog parameters are included. It only displays information that is needed to determine the host and the request. Additionally, information about the agent, cookie string, domain name, referrer, time to serve, etc., is excluded in this format.

Q:: Log generator
A:: This tier consists of the host that produces the log messages

Q:: Log analysis
A:: This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server

Q:: Log storage
A:: This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server.

Q:: Log monitoring:
A:: he third tier consists of consoles that monitor and review the log data as well as the outputs of log analysis. These consoles are used to produce reports.

Q:: Log collection
A:: Log collection is the process of collecting log messages from various sources to the database in a central location.

Q:: Log transmission
A:: To store the logs in a centralized location, they are transmitted through different transport mechanisms such as syslog UDP, syslog TCP, encrypted syslog, etc.

Q:: Log storage
A:: All the log files collected from various devices are stored in central repository/databases. Stored databases can be retrieved in structured way when needed.

Q:: Log normalization
A:: Log normalization is the process of accepting logs from heterogeneous sources with different formats and converting them into a common format.

Q:: Log correlation
A:: Log correlation is the process of matching a series of normalized log data to determine a set of related events based on a certain set of rules.

Q:: Log analysis
A:: Log analysis is the process of identifying the patterns and anomalies in the correlated log data that signifies any intrusion attempt or policy violation activity.

Q:: Alerting and reporting
A:: An alerting system generates alerts and sends a report to the user if any suspicious event is observed in the logs or calculated matrices.

Q:: 1st rule of the First Responder
A:: Prevent attempts to retrieve data by unqualified individuals

Q:: Evidence Examiner/Investigator:
A:: Evidence Examiner/Investigator examines the evidence acquired and sorts of useful evidence. Examines and sorts the evidence according to its relevance for the case. By maintaining an evidence hierarchy, the evidence examiner appropriately prioritizes the evidence.

Q:: First responder
A:: he first responder is responsible for protecting, integrating, and preserving any evidence obtained from the crime scene.

Q:: Evidence Manager
A:: The Evidence Manager manages the evidence so that it is admissible in a court of law.

Q:: IR Manager
A:: The IR manager is a technical expert who understands security and incident management. They are responsible for the actions performed by the incident analysts and report the information to the incident officer.

Q:: Forensic Investigation and Incident Containment
A:: Both are conducted simultaneously. IR helps organizations contain security events, but a computer forensic investigation enables investigators to find the root cause of the security issue.

Q:: Evidence Investigator
A:: These examine the evidence acquired and sort useful evidence.

Q:: Business Recovery
A:: An advance plan, arrangement, procedure to recover the business processes such as workspace, personnel, equipment, and facilities is called Business Recovery.

Q:: Contingency Planning
A:: Contingency plans ensure continuous on-time product and service delivery, on-site and off-site business operations, and customer satisfaction.

Q:: Emergency Management
A:: Emergency Management is the procedures and actions that are taken instantly after a crisis in order to safeguard people from harm.

Q:: Disaster Recovery
A:: DR is a plan to restore important support systems such as hardware, IT assets, and communications. The goal of disaster recovery is to reduce business downtime and to restore technical operations in a short stint of time.

Q:: BCP
A:: Business continuity planning (BCP) is a document that is developed to ensure resilience from potential threats and allow business operations to continue under adversity.

Q:: BCM
A:: Business continuity management is a process that ensures that business operations are not affected due to disruptive incidents.

Q:: DRP
A:: A disaster recovery plan is documented instructions for responding to an unexpected disruptive event (recover from disaster).

Q:: BIA
A:: BIA is a systematic process that determines and evaluates the potential effects of an interruption to critical business operations as a result of a disaster, an accident, or an emergency.

Q:: ISO 22301:2019
A:: ISO 22301:2019 describes requirements to implement, maintain, and improve the management system to protect against, reduce the likelihood of the occurrence of, prepare for, respond to and recover from disruptions when they arise

Q:: ISO 22313:2012
A:: ISO 22313:2012 guides ISO 22301 for setting up and managing effective business continuity and management system (BCMS).

Q:: ISO/IEC 27031:2011
A:: ISO/IEC 27031:2011 describes the concepts and principles of information and communication technology (ICT) readiness for business continuity, provides a framework of methods and processes to identify and specify all aspects (such as performance criteria, design, and implementation) for improving an organization's ICT readiness to ensure business continuity

Q:: ISO 22313:2020
A:: ISO 22313: 2020 provides guidance and recommendations for applying BCMS requirements that are given in ISO 22301.

Q:: Chief Information Officer
A:: The CIO is responsible for executing the policies and plans required for supporting the information technology and computer systems of an organization. The main responsibility of a CIO is to train employees and other executive management regarding the possible risks in IT and its impact on the business.

Q:: IT Security Program Managers and Computer Security Officer
A:: ISSO provides the required support to information system owners with a selection of security controls needed for protecting a system. They also play an important role in the selection and amendment of security controls in an organization.

Q:: Risk assessment
A:: Risk assessment determines the kind of risks present, the likelihood and severity of risk, priorities and plans for risk control. Risk assessment determines the types of risks that exist, likelihood and severity of risks, and priorities and plans for risk control. Decisions made in the risk treatment phase are based on the results of a risk assessment.

Q:: Risk identification
A:: It is a process to list the risks and their characteristics before they cause harm to the organization. The techniques used for risk identification include checklists, flow charts, and systems analysis.

Q:: Risk treatment
A:: t is the process of selecting and implementing appropriate controls on the identified risks in order to modify them.

Q:: Risk tracking
A:: Risk tracking identifies the chance of a new risk and includes monitoring the probability, impact, status, and exposure of risk. helps a network defender identify the chances of a new risk occurring

Q:: Risk review
A:: It enables the organization to keep the risk management objectives, and context up-to-date and accurate.

Q:: Eliminate the risk
A:: It involves eliminating the risk by applying controls to reduce the threat of exploiting the vulnerability to zero.

Q:: Reduce the risk
A:: It involves finding ways to reduce the likelihood rate of risk to an acceptable level

Q:: Risk avoidance
A:: It involves avoiding the factor that enhances the risk factor of any process in the business or finding an alternative that goes well with business needs. For instance, not allowing the use of laptops in the organization to avoid the risks associated with the use of laptops.

Q:: Mitigate the risk
A:: It involves reducing the risks associated with a threat or vulnerability by implementing direct or competing controls.

Q:: Discovery
A:: This phase involves identification, consideration, and evaluation of network assets. It provides a hacker's view of the network.

Q:: Assessment
A:: This phase involves scanning and evaluating a system for vulnerabilities

Q:: Mitigation
A:: It is an action taken to prevent vulnerabilities from exploitation. It involves reducing the risk by taking other actions instead of correcting a discovered vulnerability.

Q:: Verification
A:: This phase involves monitoring network continuously to check for new vulnerabilities.

Q:: Internal vulnerability assessment
A:: An internal vulnerability assessment evaluates a network for the presence of internal vulnerabilities.

Q:: Risk assessment
A:: Risk assessment determines the kind of risks present, the likelihood and severity of risk, priorities and plans for risk control.

Q:: External vulnerability assessment
A:: An external vulnerability assessment evaluates the security profile of an organization from the perimeter of the network.

Q:: Web vulnerability assessment
A:: It involves crawling the website in order to discover potential vulnerabilities, and then report these results.

Q:: Attack Surface Visualization
A:: This step involves mapping out all devices, paths, and networks.

Q:: IoEs' Identification
A:: In this step, potential risk exposures that attackers can use to breach the security of an organization are identified.

Q:: Attack Simulation
A:: This step involves recognizing how the identified IoE could turn to exploit.

Q:: Attack Surface Reduction
A:: This step involves implementing appropriate security controls and countermeasures to reduce the attack surface of a system.

Q:: Conduct Attack Simulation
A:: It helps a network defender validate and manage the security controls across the organization. It enables a network defender to assess the security flaws before any attack takes place.

Q:: IoEs' Identification
A:: n this step, potential risk exposures that attackers can use to breach the security of an organization are identified.

Q:: Cloud to User
A:: This refers to the attacks that a Cloud service faces from a user's point of view. This attack surfaces in cloud computing is difficult to define

Q:: User to Cloud
A:: This pertains to the different types of attack vectors that target a user. It has its origins in the Cloud system. For example, phishing-like attempts that present users a fake usage bill of the Cloud provider.

Q:: Cloud to Service
A:: It is related to exposing Cloud resources/interfaces to service instances. For example, resource exhaustion, triggering the Cloud provider to provide more resources or end up in a Denial-of-Service (DoS), and attacks on the Cloud system hypervisor. it slightly tricky to separate the service and cloud

Q:: Service to Cloud
A:: It is related to exposing the service instance to the Cloud provider. Examples include availability reductions, privacy attacks, malicious interference, data integrity attack, data confidentiality attack, etc.

Q:: IoT Applications and Software Vulnerabilities
A:: Attacks can exploit vulnerabilities in application interfaces and the software of IoT devices. These can compromise systems, steal sensitive or personal data (credentials), or insert malicious firmware updates.

Q:: IoT Device Vulnerabilities
A:: The parts of a device from which vulnerabilities emerge are physical interfaces (USB ports), failures in memory, firmware, web interface, admin interfaces, and network services.

Q:: IoT Communication Channel Vulnerabilities
A:: Attacks can occur due to the ways in which IoT components connect with each other. For example, protocols used in IoT systems, Bluetooth, and Wi-Fi can be exposed to vulnerabilities.

Q:: IoT Cloud Interface Vulnerabilities
A:: Attacks are triggered by inadequate passwords, default credentials, and insecure transport encryption in using Cloud interfaces for IoT.

Q:: IoT Device Memory Vulnerabilities
A:: It has the possibility of possessing clear-text credentials stored in memory and the monitoring of cipher keys.

Q:: IoT Device Web Interface
A:: It comprises the web application vulnerabilities of the IoT device web interface and credential management.

Q:: IoT Device Firmware
A:: It has the possibility of vulnerabilities in the device firmware that provides the features and functions for a solution.

Q:: IoT Device Physical Interface
A:: It comprises the vulnerabilities in unsecured elements, which are used to compromise IoT devices.

Q:: Strategic Threat Intelligence collection sources
A:: This intelligence is collected from sources such as open-source intelligence (OSINT), CTI vendors, and Information Sharing and Analysis Organizations (ISAOs) / Information Sharing and Analysis Centers (ISACs).

Q:: Tactical Threat Intelligence collection sources
A:: The collection sources for tactical threat intelligence include campaign reports, malware, incident reports, attack group reports, human intelligence, etc. This intelligence is generally obtained by reading white/technical papers, communicating with other organizations, or purchasing intelligence from third parties.

Q:: Operational Threat Intelligence collection sources
A:: Operational threat intelligence is generally collected from sources such as humans, social media, and chat rooms, and also from real-world activities and events that result in cyber-attacks.

Q:: Dynamic Threat Intelligence
A:: It is not a type of threat intelligence. FireEye.com - Dynamic Threat Intelligence (DTI) service is a TI feed provider. The FireEye Dynamic Threat Intelligence cloud generates a dynamic and anonymized signature of the attack when a FireEye appliance confirms an attack and warns others by distributing it on the cloud.

Q:: Indicators of Exposure (IoE)
A:: It shows potentially exploitable vectors before an incident takes place and helps in understanding the security posture of the organization and making more informed decisions to prevent the breaches in advance.

Q:: Indicators of Attacks (IoAs)
A:: It reveals an active attack before IoCs become visible

Q:: Indicators of Compromise (IoCs)
A:: IoCs are the technical indicators of threat and are discovered through the investigation after the occurrence of an incident or through the alerts if the network is monitored?

Q:: Key Risk Indicators (KRIs)
A:: KRIs are the most important indicators of an organization's overall health, it helps in reducing loss and prevents risk exposure.

Q:: OpenIOC
A:: It is a format of IoC with its XML-based framework to describe the complex semantics of the malware behavior.

Q:: CybOX
A:: CybOX (Cyber Observable Expression) provides a standard for defining indicator details (observables) regarding measurable events and stateful properties and mainly aims at automating the sharing of security information by providing more than 70 defined objects.

Q:: MAEC
A:: MAEC (Malware Attribute Enumeration and Characterization) is a standardized language to describe CTI.

Q:: TAXII
A:: TAXII (Trusted Automated eXchange of Indicator Information) is a set of specifications for exchanging cyber threat information over HTTPS. TAXII uses XML and HTTP for message content and transport. It is specially created to support the exchange of CIT represented in STIX.

## MCQ cards without a stated answer

These read as multiple-choice items with all options inline, but the source marks no correct answer. Not guessing - decide them yourself against the PDFs:
- Low-interaction Honeypot  <=  From the following, identify the type of honeypot which generally fakes those services that are frequently asked by the attacker. They are essentially a single machine with multiple virtual machines. Low-interaction Honeypot Pure Honeypot High-interaction Honeypot Production Honeypot
