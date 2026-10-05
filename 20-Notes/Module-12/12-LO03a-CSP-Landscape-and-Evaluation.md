---
type: note
module: "12"
lo: "03"
tags: [concept, bestpractice, mod/12]
topic: "CSP landscape and CSP security evaluation"
exam_weight: unknown
status: done
unresolved:
  - "p35 Figure 12.2 'Cloud Service Providers' (Worldwide Cloud Infrastructure Services Spend, Q2 2023): only three slice labels carry readable percentages — AWS 30%, Microsoft Azure 26%, Others 35%. The Google Cloud slice label OCR'd as 'oogle Clou' with NO readable percentage, so no Google Cloud share is stated here. (The three printed percentages total 91%, but the residual is not asserted as Google's share.)"
  - "p36: the three provider marketing panels are screenshots; only their banner text OCR'd ('aws Security Platform' / 'Strengthen your security— posture with Azure' / 'Your security transformation: safer with Google technology and expertise' plus the panel titles Amazon Security Capabilities, Azure Security Capabilities, Google Security Capabilities). No panel contents are described."
  - "p36: 'Cloud security maturity models can help in accelerating the implementation of the migration strategy of applications to the cloud.' is printed but the courseware names no specific maturity model in the slice — none is asserted."
---

[[MOC-Module-12]]

# CSP Landscape and Evaluation (§12.03)

> **LO#03 — Evaluate CSPs for security before consuming a cloud service**
> Section scope: how to evaluate CSP providers in terms of security before consuming a cloud
> service; the security features provided by AWS, Azure, and GCP _(Mod 12 p34)_

## Major cloud service providers _(Mod 12 p35)_

**Figure 12.2 — "Worldwide Cloud Infrastructure Services Spend, Q2 2023"** _(Mod 12 p35)_

| Slice label as printed | Share |
|---|---|
| Microsoft Azure | **26%** |
| AWS | **30%** |
| Others | **35%** |
| Google Cloud *(label OCR'd as "oogle Clou")* | **not legible in the source** |

_(Mod 12 p35)_

> The Google Cloud percentage did not survive OCR — see `unresolved:`. Do not fill it in.

## Evaluating the CSPs — gap analysis _(Mod 12 p36)_

**The move:** *before consuming a cloud service*, perform a **gap analysis on the security
capabilities and services provided by the CSPs**. _(Mod 12 p36)_

Benchmark the platform's **maturity, transparency, and compliance** against:

| Benchmark axis | Courseware values |
|---|---|
| **Enterprise security standards** | e.g. **ISO 27001** |
| **Regulatory standards** | **PCI DSS · HIPAA · SOX** |

_(Mod 12 p36)_

- **Cloud security maturity models can help accelerate the implementation of the migration
  strategy of applications to the cloud.** _(Mod 12 p36)_

### Security maturity of the CSP — evaluated on _(Mod 12 p36)_

1. **Disclosure of security policies, compliance, and practices**
2. **Disclosure when mandated**
3. **Security architecture**
4. **Security automation**
5. **Governance and security responsibility**

_(Mod 12 p36)_

> "Do not take the vendor at face value" — the p36 banner panels are pure marketing
> (`Amazon Security Capabilities`, `Azure Security Capabilities`, `Google Security Capabilities`);
> the gap analysis is the actual control. _(Mod 12 p36)_

The courseware then compares the features each CSP publishes — see
[[12-LO03b-CSP-Security-Feature-Comparison]].

Exam cross-refs: [[quiz.html]] · [[Answer-Key]]






