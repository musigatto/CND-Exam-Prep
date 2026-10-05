---

type: note
module: "08"
lo: "05"
tags: [crypto, process, bestpractice, mod/08]
topic: "IoT Security Measures — Crypto, Identity, Hardware (M11–M15)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Measures — Encryption, Identity, Hardware (§8.5, M11–M15)

## M11 — Encrypt End-to-End (E2EE)
- All data (at rest + transit) encrypted across device↔gateway↔cloud↔app
- **TLS v1.2/v1.3**, **IPsec ESP**, **DTLS**, **AES-256**, HSM-backed keys; perfect forward-secrecy ciphers
- Verify: no plaintext protocols (HTTP, Telnet, bare MQTT)

## M12 — Ensure End-to-End Security & Identity Management
- Device identity (*X.509 / SPIFFE-style), mutual TLS (mTLS) between device↔gateway↔cloud
- **PKI/CA**, certificate rotation, private CA for IoT fleet; API keys + OAuth where least privilege
- Integrate with identity providers (Azure AD, Okta)

## M13 — Strong Authentication of IoT Devices & End Users
- Complex unique credentials (no = default), **MFA/2FA**, **smartcards / FIDO2**, biometric
- Prevent dictionary/credential-stuffing attacks; per-device secrets (Zero Trust)

## M14 — Chip-level Security
- Move security into the chip (secure **SoC**, cryptoprocessors, **TPM 2.0**)
- Protect: cryprographic keys in secure element; protected boot, side-channel resistance, **Root of Trust (RoT)** (hardware anchoring)

## M15 — Hardware Security
- **HSM (Hardware Security Module)** — dedicated crypto key mgmt (generation, storage, signing)
- **Secure enclaves / TEE (Intel SGX, ARM TrustZone)** — isolate sensitive workloads
- Tamper-evidence, secure element per device






