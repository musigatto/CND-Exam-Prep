---
type: note
module: "07"
lo: "05"
tags: [concept, tool, protocol, bestpractice, mod/07]
topic: "Android Device Administration API and Security"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# Android Security Guidelines and Device Administration API (§7.5)

Android devices have built-in security features that should be enabled/configured properly.

## Android Device Administration API
- Introduced in **Android 2.2**; provides device-administration features **at the system level**
- Allows developers to create **security-aware applications** for enterprise settings (IT needs rich control over employee devices)
- A device administration ("admin") API is used to write device-admin apps installed by users; they **enforce the desired policies**
- Example app types: email clients · security apps that perform remote wipe · device-management services/apps

### Policies supported by the Device Administration API
| Policy | Description |
|---|---|
| Password enabled | Requires PIN or passwords |
| Minimum password length | Number of characters (e.g., ≥ 6) |
| Alphanumeric password required | Letters + numbers (+ optional symbols) |
| Complex password required | ≥ letter + digit + special symbol (**Android 3.0**) |
| Minimum letters/lowercase/non-letter/numerical/symbols/uppercase required | Counts in the password (**Android 3.0**) |
| Password expiration timeout | Delta in **milliseconds** from when admin sets it (**Android 3.0**) |
| Password history restriction | Prevents reuse of last **n** unique passwords; used with `setPasswordExpirationTimeout()` (**Android 3.0**) |
| Maximum failed password attempts | Device **wipes its data** after N wrong attempts; admin can remotely reset to factory defaults (**secures lost/stolen data**) |
| Maximum inactivity time lock | Screen lock after time since last touch/button; value 1–60 min |
| Require storage encryption | Whether device supports storage encryption (**Android 3.0**) |
| Disable camera | Camera enabled/disabled dynamically by context/time (**Android 4.0**) |

Additional API capabilities: **prompt user to set a new password · lock device immediately · wipe device data (factory reset)**

## Securing Android Devices — Countermeasures
- **Enable screen locks**
- **Never root** an Android device
- Download apps **only from the official Android market**
- Keep device updated with **Google Android antivirus**
- Do **not directly download APKs**
- Update the OS regularly
- **Android Protector** app: passwords for accessing text messages + email accounts
- Customize lock screen with user information
- Enable **encryption**
- **AppLock** to lock apps with private information
- Before installing from Google Play: read required permissions (must match functionality) + browse ratings/reviews
- **Multiple accounts** if device shared between users (privacy)
- Enable **GPS** to track a lost/stolen device
- Remote-erase apps: **Lookout Mobile Security · 3cX Mobile Device Manager · SeekDroid AntiTheft**
- Turn off: **visible passwords** (don't display on screen) · **use secure credentials** (apps accessing secure certs/credentials) · **Wi-Fi** (prevent accidental wireless connection) — found at **Settings → Connections** or **Settings → More → Security**

## Cards
Q:: Android Device Administration API origin + purpose?
<!--SR:!2026-09-30,1,230-->
A:: Introduced in Android 2.2; system-level device administration for security-aware enterprise apps; device-admin apps enforce policies (email clients, remote-wipe security apps, device management).
#flashcard
Q:: Key Android Device Admin policies?
A:: Password enabled · min password length · alphanumeric/complex password (Android 3.0) · password expiration/history · max failed attempts (wipe) · inactivity lock (1–60 min) · storage encryption (3.0) · disable camera (4.0).
#flashcard
Q:: Which policy wipes the device?
A:: Maximum failed password attempts — device wipes its data after the allowed number of wrong entries; remotely resettable to factory defaults.
#flashcard
Q:: Android hardening top countermeasures?
A:: Screen locks · never root · official market only · Google Android AV · no direct APK downloads · OS updates · encryption · AppLock · GPS on · remote-erase apps (Lookout, 3cX, SeekDroid) · per-app permissions review.
#flashcard
Q:: Settings path for disabling visible passwords/secure credentials?
A:: Settings → Connections or Settings → More → Security (most Android devices).
#flashcard