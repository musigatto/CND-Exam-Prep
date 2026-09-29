---
type: exam
module: "ext"
tags: [exam]
topic: "Audit of Quizlet set 617277655 against the 20 module PDFs"
exam_weight: unknown
status: done
unresolved: []
---
# Flashcard Verification Audit

> [!info] Why this file exists
> Provenance only. The study material is [[External-Flashcards-Quizlet]] - 239 cards,
> each carrying its own `_(Mod NN pNN)_` citation, so you never need this file to
> check a fact. This records the 25 cards that did **not** make it into the deck.

> [!warning] Do not drill from this note
> It carries no `flashcard` tag, so the Spaced Repetition plugin skips the file
> entirely. The 19 entries below are shown in full so you can judge them yourself,
> not because they are safe to memorise.

## Result

| | Cards |
|---|---:|
| Verified, in the deck | 239 |
| Partially verified, held back here | 19 |
| No basis in the courseware, dropped | 2 |
| Redundant repeat of another card, dropped | 4 |
| Contradicted by the courseware | 0 |
| **Original export** | **264** |

## The 19 held back

Each is right about most of itself and wrong or unsupported about one specific claim.

**Card 4** - Message Digest Algorithm 5

> Hash functions calculate a unique fixed-size bit string representation, called a message digest, of any arbitrary block of information. It is also one-way hash but is not published by NIST.
>
> _(Mod 03 p92)_

- Gap: Card adds *not published by NIST*. The courseware says nothing about publication.

**Card 15** - Firewall Analyzer

> automates the end point security monitoring, network bandwidth monitoring, security, and compliance auditing.
>
> _(Mod 04 p64)_

- Gap: Courseware credits *automates threat remediation*; the bandwidth and compliance framing is not there.

**Card 17** - SonicWALL firewall

> is a tool that supports network security, secured remote access, and data protection. It applies Unified Threat Management (UTM) against an array of attacks, combining intrusion prevention, anti-virus and antispyware with application-level control of SonicWALL Application Firewall. It provides services for network firewalls, UTMs (Unified network management), VPNs (Virtual Private Network), backup and recovery, and anti-spam for email.
>
> _(Mod 04 p36)_

- Gap: SonicWall is named only as an example vendor. The UTM / VPN / anti-spam list is not in the courseware.

**Card 29** - Windows User Account Control (UAC)

> can restrict access to system files and system-wide settings by implementing a sandbox.
>
> _(Mod 05 p98)_

- Gap: UAC is confirmed. The *sandbox mechanism* framing is not part of its definition.

**Card 55** - OpenSCAP

> It is a standard security specification maintained by the NIST which can handle multiple security issues on the host machine by supporting various activities for host safety, such as patch checking, vulnerability checking, technical control and compliance activities, and security measurement.
>
> _(Mod 06 p119)_

- Gap: Courseware says **SCAP**, the standard. The tool **OpenSCAP** is never named.

**Card 66** - Application delivery

> MAM solutions are used by admins for application delivery to mobile devices.
>
> _(Mod 07 p38)_

- Gap: MAM is confirmed as *secure, manage, distribute* of enterprise apps. The *application delivery* list is not.

**Card 79** - validating parsers using Document Type Definitions (DTD) and XML Schemas in IoT

> This will mitigate Xmpp bomb attacks
>
> _(Mod 08 p47)_

- Gap: DTD and XML-schema parser validation is confirmed. The link to the XMPP Bomb attack is not stated.

**Card 95** - NIST

> NIST developed Systems Security Engineering 800.160, IoT.
>
> _(Mod 08 p121)_

- Gap: The NIST IoT topic is real, but the courseware never mentions **800.160**.

**Card 107** - Sandbox feature for Microsoft Edge

> Protection Mode
>
> _(Mod 09 p53)_

- Gap: Protected Mode / UAC / low integrity level is confirmed. Attributing it to Edge specifically is loose.

**Card 132** - changing default password and using strong password

> This countermeasure mitigates password guessing brute force attacks.
>
> _(Mod 05 p76)_

- Gap: Strong-password guidance is confirmed. That it *prevents* brute force is not stated.

**Card 162** - 802.15

> It defines the standards for a wireless personal area network (WPAN). It describes the specification for wireless connectivity with fixed or portable devices.
>
> _(Mod 13 p11)_

- Gap: 802.15 is confirmed as the WPAN standard. *Fixed or portable devices* is not in the table.

**Card 163** - Context-based signature

> Packets are usually altered using the header information. Suspicious signatures in the header can include malicious data. This type of signature CANNOT open backdoors in a system if not detected.
>
> _(Mod 14 p21)_

- Gap: Context-based signatures are confirmed. *Cannot open backdoors* applies to undetected signatures, not this type.

**Card 167** - tcp.flags==0x00

> detect TCP-based OS fingerprinting attempts.
>
> _(Mod 14 p10)_

- Gap: The OS-fingerprint filter lost its text to OCR; no literal `tcp.flags==0x00` survives in the courseware.

**Card 169** - tcp.flags==0x012

> This filter is used to detect full TCP scan attempts.
>
> _(Mod 14 p45)_

- Gap: The full-connect scan is confirmed. The filter value `tcp.flags==0x012` is not in the courseware.

**Card 187** - Log analysis

> This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server
>
> _(Mod 15 p119)_

- Gap: The courseware has **one** tier, *Log analysis and storage*. The card splits it.

**Card 188** - Log storage

> This tier consists of one or more log servers that collect log data from the hosts. The log data can be sent either in real-time or in batches based on the schedule to the log server.
>
> _(Mod 15 p119)_

- Gap: Same: *Log analysis* and *Log storage* are a single tier, not two.

**Card 197** - 1st rule of the First Responder

> Prevent attempts to retrieve data by unqualified individuals
>
> _(Mod 16 p12)_

- Gap: Courseware calls it the *First Response Rule* and says attempts are *avoided*, not *prevented*.

**Card 207** - Disaster Recovery

> DR is a plan to restore important support systems such as hardware, IT assets, and communications. The goal of disaster recovery is to reduce business downtime and to restore technical operations in a short stint of time.
>
> _(Mod 17 p8)_

- Gap: Confirmed, but the courseware wording is *reduce business downtime and accelerate the restoration*.

**Card 215** - ISO 22313:2020

> ISO 22313: 2020 provides guidance and recommendations for applying BCMS requirements that are given in ISO 22301.
>
> _(Mod 17 p27)_

- Gap: **The courseware says ISO 22313:2012.** The card's `:2020` is wrong.

## No basis in the courseware

| Card | Topic | Why |
|---:|---|---|
| 16 | WinGate Proxy Server | WinGate appears in none of the 20 modules. |
| 256 | Dynamic Threat Intelligence | The FireEye DTI service is not in the courseware. Module 20 p44 lists FireEye iSight, a different product. |

## Redundant repeats

The export had the same fact twice in some cases. The shorter or typo'd copy was
dropped; the fuller one is in the deck. Nothing was lost.

| Card | Topic | Kept instead |
|---:|---|---|
| 42 | rwx------ | 47 |
| 44 | rwxr-xr-x | 48 |
| 232 | Risk assessment | 218 |
| 240 | IoEs' Identification | 236 |

Two more terms repeat but are **kept both times**, because the pairs are genuinely
different facts: `Log analysis` (the tier vs. the process) and `Log storage`
(collection vs. the repository that holds it).

## Coverage gap worth knowing

**The deck covers none of Module 01 (Network Attack and Defense Strategies) or
Module 02 (Administrative Network Security).** Not one of the 264 exported cards
came from either. If you are revising those two modules, this deck will not help you.

## How it was checked

The 20 module PDFs are image-only, so the text was extracted with Windows OCR
(`en-US`) across 2,799 pages, then every card was matched by exact normalized
substring against its module and the page re-derived from the corpus. All 264 page
citations were then checked against the real PDF page counts. The first pass had put
35 cards on pages that do not exist; those were corrected here, and 3 cards
downgraded from *unsupported* to *partial* once re-read.
