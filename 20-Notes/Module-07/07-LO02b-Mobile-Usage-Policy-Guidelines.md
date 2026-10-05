---

type: note
module: "07"
lo: "02"
tags: [concept, policy, bestpractice, mod/07]
topic: "Security Guidelines for Mobile Usage Policies"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-07]]

# Security Guidelines for BYOD, CYOD, COPE, and COBO (§7.2)

## For Administrator / Network Defender
- Educate employees about these policies
- Clarify **who owns which apps and data**
- Use an **encrypted channel** for data transfer
- Clarify which apps are **allowed or banned**
- Control access on a **need-to-know basis**
- Do not allow **jailbroken/rooted** devices
- Apply **session authentication + timeout** policy on access gateways
- Secure organizational data centers with multi-layered protection; register devices with a remote locate + wipe facility (if policy permits); update devices with latest OS + patches; use anti-virus + DLP solutions; ensure MDM/MAM solutions match company requirements

## For Employees
- Impose **company WLAN** access when on-site
- Use **complex passcodes**, change them frequently
- Devices must be **registered and authenticated** before accessing the organizational network
- Consider **multi-factor authentication** for remote access to org information systems
- Users must agree + **sign the policies** before accessing org systems
- On leaving: state whether **total device wipe or selective wipe** of certain apps/data is required; keep org + personal data separate
- Encrypt org data stored on devices (**strong algorithms**) + use encrypted channels
- Lost/stolen device → **remotely reset/wipe device passwords** to prevent unauthorized access
- Implement an **SSL-based VPN** for secure remote access
- Keep devices updated with latest OSes/software (avoid/fix vulnerabilities)
- No offline access to sensitive org info — accessible **only via the company network**

## Access Gateway Authentication Methods
Allowed methods (access gateway): **No authentication** · **Domain only** · **SMS authentication** · **RSA SecurID only** · **Domain + RSA SecurID**
- Specify **session timeout** through the access gateway
- Specify whether the **domain password can be cached** on the device or must be re-entered each access



