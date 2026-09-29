---

type: note
module: "06"
lo: "04"
tags: [concept, process, tool, command, policy, crypto, mod/06, flashcard/06]
topic: "Linux Password Management and PAM Policies"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Enforce Strong Password Management (§6.4)

Default = simple password rules. Strong policies restrict unauthorized access; set per organizational policy.

## Password Aging Defaults (`/etc/login.defs`)
- View/change: `sudo gedit /etc/login.defs`
- **PASS_MAX_DAYS** — maximum days a password may be used (e.g., 90)
- **PASS_MIN_DAYS** — minimum days between password changes (e.g., 20 / 7)
- **PASS_WARN_AGE** — days of warning before password expires (e.g., 10)
- Settings "applicable for new accounts only"

## PAM (Pluggable Authentication Module)
- Password-policy files: **Red Hat** → `/etc/pam.d/system-auth`; **Debian** → `/etc/pam.d/common-password`
- `minlen=` (min length, e.g., 10), `retry=` (retries before error, e.g., 4)
- **Minimum uppercase** (`ucredit=-2`), **lowercase** (`lcredit=-1`), **digits** (`dcredit=-1`), **other/symbols** (`ocredit=-1`)
  - Main text: "Minimum digits" example `dcredit=-1` (some OCR shows positive in one line — use `-1` = at least 1)
- **Password history / deny re-used passwords**: `remember=N` in `pam_unix.so` (e.g., `remember=5`)

### Account lockout (`pam_tally2.so`)
- **Account lock – retries**: lock after N failed attempts:
  - `auth required pam_tally2.so onerr=fail audit silent deny=5`
  - `account required pam_tally2.so`
- **Account unlock time**: `unlock_time=900` (seconds)

## Setting Secure Password Policy (Debian/Ubuntu)
- Install `pam_pwquality.so` module package
- Edit `/etc/pam.d/common-password` (Debian) or `/etc/pam.d/system-auth` (Red Hat)
- Configure `password requisite pam_pwquality.so retry=3 minlength=8 maxrepeat=3`
  - `retry=3` — prompt user 3 times before error · `minlen=8` — min length 8 · `maxrepeat=3` — max 3 repeating chars
- Reboot: `sudo reboot`

### Password complexity (`pam_pwquality.so`/cracklib style)
- `ucredit=-1` require ≥1 uppercase · `lcredit=-1` ≥1 lowercase · `dcredit=-1` ≥1 digit · `ocredit=-1` ≥1 special

## Restrict User from Using Previous Passwords
- Use `remember=` on `pam_unix.so`; keeps a list of old passwords in `/etc/security/opasswd`; account info in `/etc/passwd`
- Debian step: backup + edit `/etc/pam.d/common-password`, `password [success=1 default=ignore] pam_unix.so obscure use_authtok try_first_pass sha512 remember=13`
- Enable password aging: edit `/etc/login.defs` → `PASS_MIN_DAYS = 7`
- Create opasswd if absent: `# [ ! -f /etc/security/opasswd ] && touch /etc/security/opasswd`

## Ensure No Accounts Have Empty Passwords
- List accounts with empty passwords: `# awk -F: '($2 == "") {print}' /etc/shadow`
- Lock empty-password accounts: `# passwd -l accountName`
- Use `usermod -p` to set null password; **remove `nullok`** from any auth module to disable null-password login
- Disable null password in Debian: edit `/etc/pam.d/common-auth` and `/etc/pam.d/common-password` → remove `nullok`
- Disable null password in Red Hat/Fedora: edit `/etc/pam.d/system-auth` → remove `nullok`

## Disable Unnecessary Accounts
- Attackers gain access via compromised unused/inactive accounts; disable accounts of resigned employees (inside attackers)
- List users not logged in past 90 days (no header, exclude nerver-logged-in): `lastlog -b 90 | tail -n+2 | grep -v 'Never logged in'`
- Disable a user: `usermod -L <username>`

## Cards
/etc/login.defs aging params?
?
PASS_MAX_DAYS (max lifespan), PASS_MIN_DAYS (min interval between changes), PASS_WARN_AGE (days warned before expiry). New accounts only.

PAM password policy files by distro?
?
Red Hat: /etc/pam.d/system-auth. Debian/Ubuntu: /etc/pam.d/common-password. Modules: pam_pwquality.so / pam_cracklib.so / pam_unix.so.

pam_pwquality parameters?
?
`retry=3` (3 prompts), `minlength=8` (min chars), `maxrepeat=3` (max repeats). Complexity: ucredit/lcredit/dcredit/ocredit = -1 → at least 1 of each class.

Prevent password reuse in PAM?
?
pam_unix.so `remember=N` — history stored in /etc/security/opasswd; e.g., remember=13 blocks last 13 passwords.

Find empty-password accounts?
?
`awk -F: '($2==""){print}' /etc/shadow`; lock with `passwd -l <account>`; remove `nullok` from PAM configs.

Audit + disable inactive accounts?
?
`lastlog -b 90 | tail -n+2 | grep -v 'Never logged in'`; disable: `usermod -L <username>`.

Account lockout via PAM?
?
pam_tally2.so: `auth required pam_tally2.so onerr=fail audit silent deny=5` (+ `unlock_time=900`); account line pairs the auth line.
