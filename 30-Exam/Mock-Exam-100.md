---
type: exam
module: "mock"
tags: [exam, mod/01]
topic: "CND Mock Exam — 100 shuffled, no answers"
exam_weight: high
status: draft
unresolved:
  - "Mock is a stub: only Module 01 items exist (50 of 100). Remaining 50 require modules 11-20."
  - "No pass mark is applied when self-grading; official cut score is form-dependent (60-85%), see [[Exam-Facts]]."
---
# Mock Exam 100

> [!warning] No answers here.
> 4 hours · 100 single-best-answer · official format is Multiple Choice.
> **There is no fixed pass score** — EC-Council's cut score varies by form (60%–85%).
> Self-grade as a percentage and compare against your own target. See [[Exam-Facts]].
> Grade via [[Answer-Key]].

## Instructions
- Same 100 items as the [[Question-Bank]], shuffled.
- Mark your sheet, grade with [[Answer-Key]].

## Questions (partial — Module 01)

1. According to the courseware, the 11 tactic categories in MITRE ATT&CK for Enterprise are derived from which sources?
2. Which security approach uses methods such as IDS, SIMS, TRS, and IPS to address attacks that the preventive approach failed to avert?
3. An attacker floods a DHCP server with a large number of DHCP requests carrying spoofed MAC addresses, exhausting the available IP address pool. Which type of attack is this, and which tool is commonly used?
4. Which of the following best represents how risk is calculated in network security?
5. A web application uses SSL/TLS only for the login page, and a packet sniffer is used to intercept the session cookie afterwards. Which session hijacking method is used?
6. A security consultant is building an organization's compliance program. Which of the following represents the correct hierarchy as given in the courseware?
7. Which of the following is responsible for determining the purposes and means of processing personal data, while the other handles data on its behalf, under the GDPR?
8. An organization wants to block all Internet services by default and only enable each service that the network defender individually deems safe and necessary, while logging everything. Which Internet access policy type is this?
9. During the first phase of IT asset management, the team discovers and documents all assets and then groups them. Which grouping basis is used?
10. Which access rule applies when a user holds the "Secret" data classification level, according to the courseware?
11. A network defender wants a single security console that provides firewall, IDS, anti-malware, spam filtering, content filtering, DLP, and VPN, while accepting the risk of a single point of failure. Which solution is described?
12. An enterprise deploys honeypots to study attacker behavior in isolation. The network defenders discover exactly how attacks unfold step by step in order to develop new countermeasures. Which honeypot type is this?
13. Which NAC detection check is NOT among those the courseware lists for admission?
14. A technician must centrally administer switches, routers, and firewalls while encrypting the entire client–server communication including the username and password. Which AAA protocol fits?
15. Which IPsec service authenticates the sender but does NOT encrypt the data?
16. A firewall checks each packet's header against a rule set and makes its decision independently at the network level of the OSI model, without tracking session state. Which firewall technology is this?
17. An IDS cannot detect intrusions when they are encapsulated in encrypted traffic because encrypted payloads cannot be matched to signatures. What does the courseware recommend to fix this?
18. In a Software-Defined Perimeter, which component is the authentication point that evaluates the policy, grants access to the client, and determines which gateways the client may communicate with?
19. A network defender wants to allow only a single MAC address per port on an access switch. Which port-security method is this?
20. An IDS sensor is placed outside the perimeter firewall. The team tunes it to the least-sensitive attacks so it logs attack attempts only, without raising alerts. Which deployment location is this?
21. Which Windows access-management approach grants users only the specific cmdlets, scripts, and functions they need, defined through role capability files and session configuration files?
22. A Windows service is installed so that it runs under its own dedicated account with its own SID, and Windows sets the password and changes it periodically. Which Windows security feature is this, and under what name form does it run?
23. According to the courseware, which of the following does DNSSEC guarantee by adding digital signatures to DNS information?
24. A network defender must stop the built-in Guest account from being used for password-less, unauthenticated Internet access on a workstation. Which command disables it?
25. An administrator must configure the Windows Update service to start automatically so automatic updates continue. Which command does the courseware use?
26. Which SELinux mode prints warnings instead of enforcing the security policy?
27. A Linux administrator runs `find / -perm +4000` and receives a long list of binaries such as `chfn`, `gpasswd`, and `sudo`. According to the courseware, what is the purpose of this command?
28. To confine SFTP users inside a chroot jail so they cannot browse other users' directories, which configuration must be appended to `/etc/ssh/sshd_config`?
29. A network defender must drop packets that have the characteristics of an XMAS scan. Which iptables rule does the courseware list for this task?
30. Ubuntu's "minimal installation" option restricts the packages installed during the OS install, keeping only the desktop, web browser, and core system tools. Approximately how many packages does it remove compared with the default install?
31. An organization wants MDM capabilities without maintaining servers on its premises; it accepts monthly/annual fees to negate the up-front cost while still having management and admission. Which MDM delivery method fits this need?
32. An organization lets employees select their own smartphone or tablet from a list of devices approved by the company; the company purchases the selected device. Which mobile usage policy is this?
33. The Android Device Administration API supports a policy by which the device wipes its data if the user enters the wrong password too many times. Which policy is this?
34. According to the general mobile platform security guidelines, "Find My Device" (Android) and "Find My iPhone" or "FindMyPhone" (Apple iOS) are examples of which service?
35. The courseware categorizes enterprise mobile device security challenges. A vulnerability unintentionally introduced by a manufacturer into a mobile keyboard such as SwiftKey belongs to which risk category?
36. In IoT, two connected devices exchange data directly using Bluetooth, Z-Wave, ZigBee, or Wi-Fi, without the cloud being in the flow during the interaction. Which IoT communication model is this?
37. A security tester wants to enumerate and attack ZigBee/IEEE 802.15.4 networks and needs tools such as `zbdump`, `zbconvert`, `zbreplay`, and `zbstumbler`. Which framework provides these?
38. The GSMA IoT Security Assessment scores a device across eight areas. Which of the following is one of those eight areas?
39. A network defender monitors the IoT fleet managed with SeaCat.io. Which port carries the SeaCat mutual-TLS gateway tunnel (alongside Nginx on 443)?
40. An attacker exploits the OBEX Push profile to gain access to data on a nearby phone; a second attacker remotely controls a compromised device to execute AT commands, connect to the Internet, and place calls. Which Bluetooth attacks are described, respectively?
41. Per the courseware, what is the correct sequence of the automated application patch-management process?
42. A network defender wants a Software Restriction Policy rule that keeps applying to an executable no matter where it is moved or renamed on the disk. Which SRP rule type provides this behavior?
43. Which of the following is a documented LIMITATION of a web application firewall (WAF)?
44. Which statement correctly contrasts whitelisting and blacklisting?
45. An endpoint must surf the web in an isolated environment that blocks websites from reaching local storage, memory, other installed applications, and corporate network endpoints, using hardware virtualization with SLAT support. Which technology is described?
46. An application must perform equality comparisons on an encrypted column: the same plaintext value must always yield the same ciphertext. The database engine must never see the encryption keys. Which SQL Server encryption feature and mode fits this requirement?
47. A hard disk must be prepared for a vendor's laboratory-grade forensic attempt to recover data with signal-processing tools. Which destruction technique and documented characteristic is correct?
48. A security analyst must map safeguards to the state of a data asset. According to the courseware, which control pairing corresponds to the two listed data states — data in transit and data in use?
49. An Oracle DBA takes a consistent, closed-database backup so the files can be restored without the archive logs. Which sequence matches the courseware's cold-backup procedure?
50. During an Oracle data-masking project, an Enterprise Manager discovery job locates columns holding 15/16-digit credit-card and 9-digit Social Security numbers, assigning them a sensitive-column type such as CREDITCARDNUMBER. Which step of the courseware's F.A.S.T. data-masking methodology does this correspond to?

- (remaining items to be assembled from finished module banks)