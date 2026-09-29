---
type: note
module: "10"
lo: "03"
tags: [concept, process, command, crypto, mod/10]
topic: "OS Disk Encryption — FileVault, dm-crypt/LUKS, Android, iOS"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# OS-Level Disk Encryption (§10.3.1–10.3.4)

## macOS FileVault 2
- Full-disk encryption of the **startup disk** (part of macOS)
- System Preferences → Security & Privacy → **FileVault** → Turn On FileVault
- Unlock with login password or **recovery key**

## Linux — dm-crypt
| Plain mode | LUKS |
|---|---|
| No header | Header stores encrypted master key |
| Password used directly | Change password w/o re-encrypting data |
| Resistant to header-based attacks | Multiple keys possible; brute-force protection |
| Password change = re-encrypt (overwrite) | No full-encryption-resistant metadata |
- Sample LUKS ops: `cryptsetup luksFormat /dev/sdb1` (or `open --type plain` for plain)
- Tools: **Cryptmount, CryFs, VeraCrypt, Tomb, EncFSMP, 7-Zip, GPG**

## Android
- dm-crypt; **AES-128-CBC**
- **4 crypto states**: Default · PIN · Password · Pattern
- Requirements: unlock password **≥6 chars incl. ≥1 number**; charged battery / plugged in; set up ≥1 hour
- Enable: Settings → Security → **Encrypt device**
- Hardware AES offload vs software

## iOS
- Every iOS device encrypted by default; passcode/passphrase links encryption to keys
- Face ID & Passcode → **Turn Passcode On**; Passcode Options: custom numeric/alphanumeric

## Cards
Q:: FileVault: how to enable and what unlocks it?
A:: System Preferences → Security & Privacy → FileVault → Turn On; unlock via login password or recovery key.
#flashcard
Q:: What algorithm/state set does Android dm-crypt use?
A:: AES-128-CBC; states Default, PIN, Password, Pattern.
#flashcard
Q:: LUKS over plain dm-crypt: key benefits?
A:: Change password without re-encrypting data; multiple keys; brute-force protection (header + encrypted master key).
#flashcard