---
type: note
module: "16"
lo: "02"
tags: [process, bestpractice, mod/16]
topic: "first responder role, evidence time-gap, pre-response preparation"
exam_weight: unknown
status: done
unresolved:
  - "p11 role list prints `Alerting the incidence teams` and `C0ntaining incident` (zero for o) — quoted in cleaned form, OCR variants recorded here"
  - "p11 prints `should aware` and `forensics investigation u procedure`; p13 heading prints `Things You Should You Know` — grammar/OCR kept as meaning-preserving prose, variants recorded here"
  - "p12 prints first responder must ensure `reliability and liability` of evidence — kept verbatim, not corrected to admissibility"
---

[[MOC-Module-16]]

# First Responder Role and Preparation (§16.02)

> **LO#02: Understand the role of the first responder in incident response** _(Mod 16 pp10–13)_
> Covers pp10–13.

## First responder — definition _(Mod 16 p11)_

- **Individual who arrives first at the crime scene** and brings the incident to others' attention; gains access to the **victim's computer system after the incident report**.
- May be an **end user, network administrator**, anyone in day-to-day network operations, **law enforcement / investigation officer** — someone who spends time in network environments and knows org **assets, traffic, performance/utilization, topology, system locations, security policy**.
- Key value: early **detection, source, impact**, evidence **collection and preservation**.
- IRT works **on the pretext** (as printed) **of the first responder**.

## Roles and responsibilities _(Mod 16 p11)_

- **Reporting** the incident · **alerting** the incident teams · **containing** the incident · **identifying the crime scene** · **collecting complete information** about the incident / crime-scene findings · **preserving temporary and fragile evidence** · **packaging and transporting** the electronic evidence.
- Responsible for **protecting, integrating, and preserving** any evidence from the crime scene (as printed).

## Time-gap and evidence _(Mod 16 p12)_

- **Time gap between occurrence and transference of evidence** is a key aspect; first responder ensures **reliability and liability** of evidence (verbatim).
- Method matters for **preserving evidence and finding attackers**; trained to gather evidence **without modifying any running services** — before it is lost.
- Collects **initial information**, determines **extent and impact**, so others can decide further courses of action.
- Experienced responder applies good **forensic techniques** early; predicts how any change affects further investigation; upholds **availability, integrity, reliability** of evidence.

## First Response Rule _(Mod 16 p12)_

- **Under no circumstances should anyone except forensic analysts** collect or recover data from any computer system / electronic device holding electronic information.
- Everything inside collected devices is **probable evidence** — treat accordingly; unqualified retrieval attempts risk **compromising file integrity** or making files **inadmissible in legal/administrative proceedings**.
- **Secure and protect the workplace/office** to maintain veracity and quality of the crime scene and storage media.

## Things to know before first response _(Mod 16 p13)_

- Review the org IRP, covering: **local IRT names and contact info** · **escalation procedures** · **reporting/handling procedures** for suspected incidents · **containment actions for various incident types**.
- Review the plan and **suggest/implement changes** as required.
- IRT contacts get responders + IRT **on location immediately, minimizing delay**.
- Before escalating, collect and document: **IP address + physical location** of affected systems · **type of data** on the systems · **timeline of activities** the system/user went through · **how detected** · **number of users affected**.
- Containment actions **differ per incident type** — know the per-type actions; prevents further damage.





