---
type: note
module: "11"
lo: "08"
tags: [bestpractice, mod/11, flashcard/11]
topic: "Docker Image Security Best Practices"
exam_weight: unknown
status: done
unresolved:
  - "p.127-128 the Dockerfile snippet OCR'd as 'IO -alpine / USER node / node index. j s' - rendered here as FROM node:10-alpine / USER node / node index.js (high confidence: the slice's own Snyk and p.128 tag examples also use node:10 and node:8-alpine). Not literal."
  - "p.127 the Snyk test command OCR'd as '$ snyk test --docker node:10 --file-path /path/to/' - the image name and path are reconstructed from OCR spacing; the flags --docker and --file-path are legible."
  - "p.128 'An image hash to pin the exact content, for example: FROM node:' - the hash after the colon is missing (truncated in the source), so no hash example is given."
  - "p.128 security disclosure file is written 'SECURITY.TXT' in the courseware; reproduced as printed, not corrected to another casing."
  - "p.128 the benign use cases for ADD are never stated - only its risks and the rule 'use COPY unless ADD is specifically required'."
---

[[MOC-Module-11]]
# Docker Image Security Best Practices (§11.08)

Closes LO#08 with the image-layer rules. Engine features and DCT: [[11-LO08a-Docker-Security-Measures]]; vendor scanners/bench: [[11-LO08b-Docker-Security-Tools]]. _(Mod 11 p127–p129)_

## The list _(Mod 11 p127–p128, closing items p129)_

| # | Practice | Content |
|---|---|---|
| 1 | **Favor minimal base images** | Fewer OS libraries and tools → minimize risk and **attack surface**; favor **alpine-based** images over full-blown system OS images. _(p127, p128)_ |
| 2 | **Sign and verify images** | Mitigates **MITM**: pull only images pushed by the publisher and untampered; sign with **notary**; ensure the pulled image is trustworthy and authentic. _(p127, p128)_ |
| 3 | **Implement least privileged policy** | Dedicated user and group created **on the image**, minimal permissions to run the application; **the same user runs the process**. Node.js ships a built-in generic `node` user. _(p127)_ |
| 4 | **Find, fix, monitor OSS vulns** | Scan images for known vulnerabilities **as part of CI**; tool such as **Snyk** for open-source application libraries and Docker images. _(p127, p128)_ |
| 5 | **Use multi-stage builds** | Small, clean images with **minimized attack surface and vulnerabilities**; closing item: reduces the attack surface for **Docker image dependencies**. _(p127, p129)_ |
| 6 | **Use labels for metadata** | Labels/metadata carry **security details**; implement a **security disclosure policy** in a `SECURITY.TXT` file and provide that information in the image label. _(p127, p128)_ |
| 7 | **Use a linter** | Static code analyzer such as the **hadolint** linter to detect/alert on Dockerfile issues and enforce Dockerfile best practices; closing item: resolve concerns related to **Docker files**. _(p127, p129)_ |
| 8 | **Use COPY instead of ADD** | ADD is vulnerable to MITM (arbitrary URLs could be malicious sources), implicitly unpacks local archives → **path traversal / Zip Slip**; use COPY unless ADD is specifically required. _(p127, p128)_ |
| 9 | **Do not leak sensitive information** | Prevent accidental leakage of secrets, tokens and keys while building: **multi-stage builds**; **Docker secrets** feature to mount sensitive files **without caching** (**Docker 18.04+** only); **`.dockerignore`** to avoid a hazardous `COPY` pulling sensitive files from the build context. _(p128)_ |
| 10 | **Use fixed tags for immutability** | Owners can push new versions to the same tag → inconsistent builds and hard-to-track vulnerability fixes. Use a **verbose tag with version + OS** (`node:8-alpine`) and an **image hash** to pin exact content. _(p128)_ |

## Commands / examples as printed _(Mod 11 p127–p128)_

```
# 3 - least privileged policy: the same user runs the process
FROM node:10-alpine
USER node
node index.js

# 4 - scan open-source libraries and images
$ snyk test --docker node:10 --file-path /path/to/
$ snyk monitor --docker node:10
```

`node:8-alpine` = verbose version+OS tag. Hash form: `FROM node:<hash>` — the hash itself is missing in the source. _(Mod 11 p128)_

## Cards

Why favor minimal and alpine base images?
?
Choose images with fewer OS libraries and tools - this decreases risk and reduces the attack surface area of the container. Favor alpine-based images over full-blown system OS images. _(Mod 11 p127–p128)_

COPY versus ADD: what does the courseware say, and how is it worded twice?
?
ADD is vulnerable to MITM attacks because arbitrary URLs specified could be malicious data sources, and it implicitly unpacks local archives, which could result in path traversal or Zip Slip vulnerabilities. Use COPY instead of ADD - use COPY unless ADD is specifically required. _(Mod 11 p127–p128)_

The three measures to stop secrets leaking into images during build, and the version constraint.
?
Use multi-stage builds; use the Docker secrets feature to mount sensitive files without caching them - supported only from Docker 18.04; use a .dockerignore file to avoid a hazardous COPY instruction that may pull sensitive files from the build context. _(Mod 11 p128)_

Fixed tags for immutability: what goes wrong, and what are the two fixes?
?
Image owners can push new versions to the same tags, giving inconsistent images during builds and making it hard to track whether a vulnerability is fixed. Fix with a verbose tag carrying version and OS, for example node:8-alpine, plus an image hash to pin the exact content. _(Mod 11 p128)_

Least privileged policy on an image, and the multi-stage build payoff.
?
Create the dedicated user and group on the image with minimal permissions to run the application, and use the same user to run the process - the Node.js image has a built-in generic node user. Multi-stage builds create small, clean images with minimized attack surface and vulnerabilities. _(Mod 11 p127, p129)_

Which two tools does the courseware name for image scanning and Dockerfile linting, and what is each for?
?
Snyk - scan Docker images and open-source application libraries for vulnerabilities as part of CI, and monitor for newly disclosed ones. hadolint - a static code analyzer linter that detects and alerts on issues in a Dockerfile and enforces Dockerfile best practices. _(Mod 11 p127, p129)_
