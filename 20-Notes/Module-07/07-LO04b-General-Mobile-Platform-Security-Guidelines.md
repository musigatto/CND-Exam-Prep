---
type: note
module: "07"
lo: "04"
tags: [bestpractice, policy, tool, threat, mod/07]
topic: "General Mobile Platform Security Guidelines"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# General Mobile Platform Security Guidelines (§7.4)

## General Guidelines
- Do not install too many applications; avoid auto-uploading photos to social networks
- Perform **security assessment** of the application architecture
- Maintain **configuration control and management**
- Install applications from **trusted application stores**
- **Securely wipe/delete data** when disposing of a device
- Do not share info in GPS-enabled apps **unless required**
- Never connect two separate networks (e.g., **Wi-Fi + Bluetooth simultaneously**)
- Disable wireless access (Wi-Fi/Bluetooth) when not in use; Bluetooth **off by default**; disable sharing/tethering when idle

## Use Passcode
- Strong passcode, max possible length · **idle timeout** auto-lock · lockout/wipe after certain attempts · consider **eight-character passcodes** · prevent passcode guessing: set **erase data ON**

## Update OS and Apps
- Install updates when new releases are available · regular software maintenance

## Enable Remote Management
- Enterprise: use **MDM solutions** to secure, monitor, manage, support deployed mobile devices

## Do Not Allow Rooting / Jailbreaking
- MDM solutions must prevent/detect rooting/jailbreak attempts; add clause to mobile security policy

## Use Remote Wipe Services
- **Find My Device** (Android) · **Find My iPhone / FindMyPhone** (Apple iOS) to locate a lost/stolen device
- Report lost/stolen device to IT → disable certificates + other access methods

## Encrypt Storage
- Hardware encryption if supported · encrypt device **and backups** · use device encryption + patch applications

## Periodic Backup and Synchronization
- Secure OTA backup-and-restore tool with background sync
- Backup to Google account (Android) — ensure **sensitive enterprise data NOT backed up to the cloud**
- Control backup location · encrypt backups · keep sensitive data away from shared devices · limit logging data on device · use secure data-transfer utilities (encrypt in transit)

## Filter Email-forwarding Barriers
- Server-side settings of corporate email · **commercial DLP filters** · prevent local caching of emails

## Configure Application Certification Rules
- Install/run **signed applications only** · wireless "ask to join" networks · sandbox apps + data · auto-lock **1 min** · limit location-based services to trusted apps; disable location tracking for apps · disable notifications while locked (avoid sensitive data on lock screen) · AutoFill names/passwords per policy · disable diagnostics + usage data (Settings → General → About)

## Strengthen Browser Permission Rules
- Per company security policies to avoid attacks

## Design and Implement Mobile Device Policies
- Policy defines accepted usage, support levels, information-access permitted per device type
- Control devices/apps · prohibit USB keys · manage OS + application environments · press power button to lock · verify printer location before printing sensitive documents · **Citrix technologies** for data-center storage (privacy of personal devices) · **Follow-Me-Data + ShareFile** as enterprise-managed solution for sensitive data on mobile devices

## Administrator Guidelines
- Publish enterprise policy for consumer-grade devices **and BYOD**; publish **cloud policy**
- Enable antivirus to protect data-center data
- Policies for allowed/prohibited app + data access levels on consumer-grade devices
- Specify **session timeout** through the access gateway
- Specify whether **domain password can be cached** on device
- Access gateway authentication methods: **No authentication · Domain only · SMS authentication · RSA SecurID only · Domain + RSA SecurID**
- Develop/maintain mobile device security policy (resources accessible via mobiles, mobile types, access privileges)
- Develop **system threat models** for mobile devices + accessed resources
- Enable required security settings **before issuing devices**
- Regular maintenance: updated OS/apps · clocks synced to a **common time source** · reconfigure access privileges · identify/document abnormalities
- Monitor policy adherence; evaluate service providers; **test solutions before production** (authentication, app functionality, security, connectivity, performance)

## SMS Phishing Countermeasures
1. Never reply to a suspicious SMS without verifying the source
2. Do **not click links** in the SMS
3. Never reply to an SMS requesting personal/financial information
4. Review your bank's SMS policy
5. Enable **"block texts from the internet"** from your provider
6. Never reply to an SMS urging fast action/response
7. Never call a number included in the SMS
8. Avoid unexpected scams/gifts/offers
9. Avoid messages from non-telephonic numbers (internet text-relay services conceal identity)
10. Check for spelling mistakes, grammatical errors, language inconsistency

## Cards
Q:: Passcode recommendations?
A:: Strong passcode, max length · idle-timeout auto-lock · lockout/wipe after attempts · eight-character passcodes · erase data ON to prevent guessing.
#flashcard
Q:: Remote wipe service examples?
A:: Find My Device (Android) and Find My iPhone / FindMyPhone (iOS); report loss/theft to IT to disable certificates + access methods.
#flashcard
Q:: Access gateway authentication methods?
A:: No authentication · Domain only · SMS authentication · RSA SecurID only · Domain + RSA SecurID.
#flashcard
Q:: SMS phishing countermeasures (top items)?
A:: Don't reply without verifying source · don't click links · don't reply to requests for personal/financial info · review bank's SMS policy · block texts from the internet · never call numbers from SMS · avoid non-telephonic numbers.
#flashcard