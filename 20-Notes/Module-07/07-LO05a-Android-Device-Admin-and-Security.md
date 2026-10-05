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





