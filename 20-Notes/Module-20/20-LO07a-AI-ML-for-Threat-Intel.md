---
type: note
module: "20"
lo: "07"
tags: [process, mod/20]
topic: "AI/ML for threat intel"
exam_weight: unknown
status: done
unresolved:
  - "p75 header OCRs 'LO#OZ' and 'A/ ML'; clean 'LO#07' / 'AI/ML' from p3 prose list and body used"
  - "p76 prints 'police enforcement' and 'adaption'; kept verbatim, not corrected"
  - "p76 'Al' for 'AI' rendered as 'AI' in prose quotation where unambiguous"
  - "p79 Rapid7 Source prints garbled 'https://www.ropid7.com' forms; quoted verbatim; dashboard values not read"
  - "p81 tool entries carried in sibling 20-LO07b note; this note covers pp75-80 (manifest said pp75-81)"
---
[[MOC-Module-20]]

# AI/ML for Threat Intel (§20.07)

> **LO#07: Discuss leveraging AI/ML capabilities for threat intelligence** _(Mod 20 pp75–80)_
> Covers pp75–80. p75 frames the section as IoC enrichment, phishing detection, and applying AI to TI.

## Enhance CTI using AI/ML _(Mod 20 p76)_

- **Automated data collection and analysis**: collect and analyze lots of data from **network logs, security alerts, open-source intelligence**; extract pertinent IOCs (**IP addresses, domain names, hashes**) by **removing unimportant data**; saves time and resources, gives **actionable insights**. _(Mod 20 p76)_
- **Enhanced threat detection and response**: **machine learning and deep learning** techniques that **learn from past and current data and adapt to new and developing threats**; prioritize the most critical dangers; offer **suggestions and instructions on how to neutralize them**. _(Mod 20 p76)_
- **Improved sharing and collaboration**: share with **industry peers, police enforcement (as printed), governmental agencies**; **cross-reference and validate** TI data with other sources and databases; aid **enrichment and validation**. _(Mod 20 p76)_
- **Enhanced skills and knowledge**: training and educational tools (**courses, tutorials, webinars, podcasts**); **feedback and ideas** on improving TI processes; learn from own and others' experiences. _(Mod 20 p76)_

See sibling [[20-LO07b-TI-Tools-Guidelines-and-Summary]] for the AI/ML TI solutions and application guidelines.

## Use cases of AI in TI _(Mod 20 pp77–78)_

| Use case | What the page says |
|---|---|
| Summarization | **NLP models, with LLMs as a notable example**, condense large volumes into summaries; analysts absorb and convert TI into **useful insight** |
| IOC extraction | **Automatically extract IOCs** from **unstructured sources like social media or dark web forums**; speeds identification of possible threats |
| TTP extraction | Extract TTPs from **lengthy documents like threat research studies**; better comprehend and protect against **specific adversary behaviors** |
| Predictive intelligence | Assess **past threat data and forecast future trends**; proactively adjust security posture |
| Alert generation | Exchange of TI can **create automatic warnings** |
| LLM-streamlined exchange | **LLMs automatically create warnings or reports** depending on risks discovered; streamline **exchange and risk communication** |
| Enhanced decision making | AI insights and suggestions help **prioritize and distribute resources** |
| Real-time TI | Analyze different sources, get **real-time TI, respond to emerging threats quickly** |

_(Mod 20 pp77–78)_

## Enrich IoCs with TI _(Mod 20 p79)_

- Use **TI feeds to enrich IOCs** (IP address, domain names, file hashes) with **contextual information**; evaluate risk more accurately; **prioritize by impact on critical resources** to respond efficiently. _(Mod 20 p79)_
- Hunting lets the organization **correlate IOCs** to understand and synchronize **incidents and vulnerabilities**; keeps data **centralized with a clear view of the network**; structure IOCs and **block indicators on the firewall and EDR**. _(Mod 20 p79)_
- Prose Source as printed: `https://www.ropid7.com` forms garbled in OCR; Figure 20.13 Rapid7 IntSights dashboard treated as non-evidence, no values read. _(Mod 20 p79)_

## Phishing detection with TI _(Mod 20 p80)_

- TI identifies **phishing campaigns** via data on **known malicious domains, email addresses, and phishing techniques**; also detects **compromised email accounts**. _(Mod 20 p80)_
- Three approaches: **automated processes** (free team from manual phishing-threat effort); **proactive preventive tools** (TI software, preventive posture); **AI analyses** (detailed AI analyses of phishing threats). _(Mod 20 p80)_






