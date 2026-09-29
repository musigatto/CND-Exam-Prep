---
type: note
module: "09"
lo: "02"
tags: [concept, process, bestpractice, mod/09]
topic: "Application Sandboxing — Approaches, Examples, Browser Isolation"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Application Sandboxing (§9.2a)

## Sandboxing Concept
- **Sandboxing** = running apps in a **sealed container** so they cannot access critical system resources / other programs; extra security layer protecting apps + system from malicious apps
- Purpose: execute **untrusted or untested programs/code from untrusted or unverified third parties** without risking host/OS
- **Limitation:** sandbox protection is **not robust against advanced malware that targets the OS kernel**
- Sandboxed app → dedicated directory with unlimited read/write **inside**, no read/write **outside** unless authorized

## Two Approaches
| Type | Mechanism |
|---|---|
| **Isolation-based sandbox** | program isolated from system resources + outside programs |
| **Rule-based sandbox** | applications share resources **based on set rules/policies** |

## Sandbox Examples
| Example | Behavior |
|---|---|
| **Web browsers** | run low-permission sandboxed; page JS runs but cannot access local system files; plug-in access restricted |
| **PDFs / Office docs** | Adobe Reader PDF in restricted sandbox; Office docs sandboxed to stop unsafe macros |
| **Mobile apps** | each app sandbox-isolated from another; requests user permission for resources (location, camera) |
| **Windows UAC** | sandbox restricting access to system files/settings; Edge Protected Mode runs at **low** integrity (standard user = medium; elevated admin = high) |

## Chrome: Strict-Origin-Isolation (Site Isolation)
- Loads each site in a **dedicated process**, limited access between sites; blocks sensitive docs from other sites
- Two enable methods: `chrome://flags` → Strict-Origin-Isolation → **Enabled** (or goto `chrome://flags/#enable-site-per-process`) + restart; or shortcut Target + `--site-per-process`

## Firefox: Sandbox Level Checks
- Location 1: `about:support` → scroll to **Sandbox** listing → Content Process Sandbox Level
- Location 2: `about:config` → preference **`security.sandbox.content.level`** (integer) → change as required

## Acrobat Reader Sandbox Configuration
- Edit → Preferences → **Security (Enhanced) → Sandbox protections**: Enable Protected Mode at startup · Create Protected Mode log file · **Run in AppContainer** · Protected View (Off / Files from potentially unsafe locations / All files)

## Cards
Q:: Sandboxing definition / goal?
A:: Run untrusted or untested third-party programs in a sealed container that blocks access to critical system resources; extra layer over host/OS.
#flashcard
Q:: Sandbox limitation (important)?
A:: Not robust against advanced malware targeting the OS kernel.
#flashcard
Q:: Two sandbox approaches?
A:: Isolation-based (program isolated from system). Rule-based (shares resources per policies).
#flashcard
Q:: Windows UAC integrity levels vs sandbox?
A:: Edge Protected Mode runs low integrity; standard user = medium; elevated admin = high.
#flashcard
Q:: Chrome site-isolation flag methods?
A:: chrome://flags Strict-Origin-Isolation Enabled, or Chrome shortcut Target --site-per-process.
#flashcard
Q:: Firefox sandbox preference?
A:: about:support (Sandbox listing) or about:config security.sandbox.content.level.
#flashcard
Q:: Acrobat Protected Mode?
A:: Security (Enhanced) → Sandbox protections: Protected Mode at startup, AppContainer, Protected View modes.
#flashcard