---

type: note
module: "10"
lo: "04"
tags: [process, tool, command, mod/10]
topic: "IIS Server SSL Certificates (CSR, bind, pkcs #12 export)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# IIS Secure Server Certificates (§10.4.2)

## Generate a Certificate Request in IIS
1. IIS Manager → server node → **Server Certificates**
2. **Create Certificate Request** (CSR)
3. **Distinguished Name Properties**:
   - Common name = fully-qualified domain (e.g. `www.luxurytreats.com`)
   - Organization = legally registered name (ECC)
   - Organizational unit, City/locality (Lehi, UT), State/province, Country/region
4. **Cryptographic Service Provider** = default **Microsoft RSA SChannel Cryptographic Provider**; bit length (2048)
5. Save `.txt` CSR → submit to CA (internal or public)

## Complete + bind
- **Complete Certificate Request**: point to CA-issued `.cer` + set friendly name
- **Bind** to site: site → Bindings → **https** → port **443** → select cert
- Renewal: export/import .pfx with private key after CSR replacement

## Export/import for load-balanced hosts
- IIS → Server Certificates → **Export** → `.pfx` (private key, password)
- Import on other nodes → bind same cert




