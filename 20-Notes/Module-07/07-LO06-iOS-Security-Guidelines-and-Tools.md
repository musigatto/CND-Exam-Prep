---

type: note
module: "07"
lo: "06"
tags: [bestpractice, tool, policy, mod/07, flashcard/07]
topic: "iOS Security Guidelines and Tools"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# iOS Security Guidelines and Tools (§7.6)

iOS devices have built-in security features that should be enabled/configured appropriately.

## Guidelines for Securing iOS Devices
- **Passcode Lock:** Settings → Touch ID and Passcode → Turn Passcode On; set separate passcodes for apps with sensitive data
- **Disable JavaScript and add-ons** from the web browser
- Download applications from the **Apple App Store** only
- **Auto-Lock Timeout:** Settings → General → Auto-Lock (enter passcode after set time)
- Use iOS devices on a **secured + protected Wi-Fi** network
- Do not store sensitive data on the **client-side database**
- Do not access web services on a **compromised network**
- Do not open links/attachments from **unknown sources**
- Deploy only **trusted third-party applications**
- **Change the default iPhone root password from Alpine**
- Do **not jailbreak or root** in enterprise environments
- Configure **Find My iPhone** + wipe lost/stolen devices
- Enable **jailbreak detection**; protect access to **iTunes, Apple ID, Google accounts** with sensitive data
- **Disable iCloud services** so sensitive enterprise data is not backed up to the cloud (cloud can back up documents, account info, settings, messages)
- **Ask to Join Networks:** Settings → Wi-Fi → Ask to Join (prevents random network connection)
- **Regular OS updates with Apple security patches:** connect to iTunes; iOS 5+ → Settings → General → Software Updates
- **Erase Data:** Settings → Touch ID and Passcode → Erase Data — erases all data/settings after failed attempts (e.g., 10)
- Turn **Voice Dial OFF** (Settings → Touch ID and Passcode) — dialing without passcode
- **Delete Keyboard Cache:** General → Reset → Reset Keyboard Dictionary (removes recorded keystrokes)
- **Disable Geotagging** (location-based data stored in images)
- **Safari Privacy + Security:** Settings → Safari — block pop-ups · disable passwords/AutoFill · fraudulent-website warnings · block cookies · clear history/website data
- **Do Not Track:** Settings → Safari → enable (keep web browsing info private)
- Disable **Bluetooth** (Settings → Bluetooth → OFF) and **Wi-Fi** (Settings → Wi-Fi → OFF) when not in use

## iOS Device Tracking Tools
- **Find My** (support.apple.com): use another iOS device signed in with the lost device's **Apple ID** to locate on map, **remotely lock**, play a sound, display a message, **erase all data**
  - **Lost Mode** (iOS 6+): locks device with passcode + custom message (e.g., contact number); tracks whereabouts → recent location history viewable
  - Setup: Settings → [your name] → iCloud → Find My iPhone → turn ON **Find My iPhone** + **Send Last Location** (iOS 10.2-: Settings → iCloud)
  - **Find My network:** locate device even offline, in power-reserve mode, after power-off
  - **Send Last Location:** auto-sends location to Apple when battery is critically low
- Others: **mSpy** (mspy.com) · **SpyBubble** · **Scannero.io / Scenario** · **iLocalis** (ilocalis.com) · **GPS Tracker by FollowMee** (followmee.com) · **iHound** (apps.apple.com)

## iOS Device Security Tools
- **Avira Mobile Security** (avira.com): web protection + identity safeguarding · identifies phishing websites targeting you · secures emails · tracks device · identifies suspicious activities · organizes device memory · **backs up contacts**
- Others: **Norton Mobile Security** · **LastPass Password Manager** · **McAfee Total Protection** · **SplashID Safe Password Manager** · **Webroot SecureWeb Browser** · **Wickr Me — Private Messenger** · **1Password** · **GadgetTrak** · **iLocalis** · **GPS Tracker by FollowMee**

## Cards
iOS passcode/erase configuration paths?
?
Settings → Touch ID and Passcode (Turn Passcode On, Erase Data, Voice Dial OFF); Auto-Lock: Settings → General → Auto-Lock.

Default iPhone root password and the fix?
?
Default root password is "Alpine" — must be changed. Never jailbreak/root in enterprise environments.

Find My iPhone Lost Mode?
?
iOS 6+ feature: locks the device with a passcode + custom message (e.g., contact number); tracks whereabouts and recent location history.

Find My iPhone setup path?
?
Settings → [your name] → iCloud → Find My iPhone → turn on Find My iPhone + Send Last Location (iOS 10.2-: Settings → iCloud).

Key iOS hardening items?
?
App Store only · no sensitive data on client-side DB or iCloud · no jailbreak · trusted third-party apps · ask-to-join Wi-Fi · Safari privacy settings + Do Not Track · disable BT/Wi-Fi when idle · regular Apple patches.
