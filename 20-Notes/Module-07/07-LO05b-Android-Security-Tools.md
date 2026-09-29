---
type: note
module: "07"
lo: "05"
tags: [tool, command, mod/07]
topic: "Android Security Tools (Find, AV, Scanner, Tracker)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# Android Security Tools (§7.5)

## Find My Device (Android)
- Locates a lost Android device and protects/erases stored information
- With **Google Sync** on a supported device **+ Google Apps Device Policy app** → use the **Google Apps control panel** to remotely find, lock, or erase
- Erase = all data wiped + **factory reset** (email, calendar, contacts, photos, music, personal files; SD card if applicable)

### Requirements to use Find My Device
Be turned on · signed in to a **Google account** · connected to **mobile data or Wi-Fi** · visible on **Google Play** · location enabled · Find My Device turned on

### Steps (find/lock/erase)
1. Go to `https://www.google.com/android/find` + sign in
2. Select the lost device (top of screen) — device gets a notification
3. Check location on map (approximate; last-known location available)
4. Pick action (Enable lock and erase first if needed):
   - **Play sound:** rings at full volume for **5 min** even on silent/vibrate
   - **Lock:** locks with PIN/pattern/password; can set one + add message/phone number to lock screen
   - **Erase:** permanently deletes data (may not delete SD card); Find My Device will **not work after erase**

## Antivirus / Security Apps (Android)
- **Kaspersky: VPN & Antivirus** (my.kaspersky.com) — anti-theft + virus protection; features: antivirus protection · background check (virus/spyware/trojan scan) · **app lock** (secret code for messages/photos) · **find my phone** · anti-theft · anti-phishing (secure shopping/banking) · **call blocker** · **web filter** · Android 8 support · **data leak checker** (accounts leaking personal data on the web/dark web) · smart home monitor
- Others: **Avira Antivirus Security** · **Avast Antivirus** · **McAfee Security: Antivirus VPN** · **McAfee Total Protection** · **Sophos Mobile Security** · **Malwarebytes for Android** · **AVG AntiVirus** · **Safe Security** · **Trend Micro Mobile Security and Antivirus** · **BullGuard Mobile Security and Antivirus**

## Vulnerability Scanners (Android)
- **X-Ray** (labs.duo.com): scans for **unpatched vulnerabilities from the mobile carrier**; lists CVEs + presence check per vulnerability; auto-updated for newly disclosed vulnerabilities (e.g., CVE-2015-1528, CVE-2015-3825, CVE-2015-3636, CVE-2014-4943, CVE-2014-3153, CVE-2013-6282)
- Others: **Threat Scan** (free.kaspersky.com) · **Astra** (getastra.com) · **Shellshock Scanner — Zimperium** · **Quixxi** · **BlueBorne Vulnerability Scanner by Armis** · **EternalBlue Vulnerability Scanner** (ebvscanner.firebaseapp.com)

## Device Tracking Tools (Android)
- **Google Find My Device** (play.google.com): anti-theft recovery app — send a text message → replies with current address + **Google Maps link**; rings at max volume (even silent); shows remaining battery; **notifies on SIM change**; remote erase
- **Where's My Droid** (wheresmydroid.com): track via text-message **attention word** or online control center **Commander** — ring/vibrate find · GPS location · **GPS Flare** (location alert on low battery) · passcode protection · SIM/phone-number change notification · **stealth mode** (hides incoming texts with attention word)
- Others: **Prey** (preyproject.com) · **iHound** (ihoundgps.com) · **Hoverwatch** · **Life360** · **GadgetTrak** · **Find My Device + Location Tracker — TrackView** (trackview.net) · **Lost Android** (androidlost.com)

## Cards
Q:: Find My Device prerequisites?
A:: On · signed into Google account · mobile-data/Wi-Fi connected · visible on Google Play · location enabled · Find My Device on.
<!--SR:!2026-09-30,1,230-->
#flashcard
Q:: Find My Device actions?
A:: Play sound (full volume 5 min) · Lock (PIN/pattern/password + message/phone number) · Erase (permanent; SD card may survive; service stops working).
#flashcard
Q:: X-Ray function?
A:: Scans Android device for unpatched (carrier-level) vulnerabilities; lists CVEs with per-vulnerability check; auto-updates for new disclosures.
#flashcard
Q:: Where's My Droid tracking methods?
A:: Text-message attention word or the online control center "Commander"; features GPS, GPS Flare, SIM-change notification, stealth mode.
#flashcard
Q:: Kaspersky VPN & Antivirus feature set?
A:: Anti-virus cleaner · background check · app lock · find my phone · anti-theft · anti-phishing · call blocker · web filter · data leak checker · smart home monitor.
#flashcard