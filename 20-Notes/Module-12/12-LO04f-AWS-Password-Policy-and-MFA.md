---
type: note
module: "12"
lo: "04"
tags: [policy, bestpractice, mod/12]
topic: "AWS IAM password policy and MFA for privileged users"
exam_weight: unknown
status: done
unresolved:
  - "p77: the required character set for the 'non-alphanumeric characters' rule prints only as 'at least one of the following non-alphanumeric characters: I ' - the list itself is lost. p78 Figure 12.27 gives the set but it OCRs as '( ! @ g $ % A & - ( ) _ - 001')', i.e. several glyphs are unresolvable (#, ^, *, and the final 3-char group). The rule is asserted; the exact character set is NOT."
  - "p78: Figure 12.27's submit button reads 'Save changes' while step 3 of the printed procedure reads 'Click on Apply Password Policy'. Both are reproduced as printed; the courseware does not reconcile them."
  - "p78: 'IAM default' option subtitle OCRs as 'Defant requirertpnts' and the 'Custom' subtitle as 'use a password pdicy'. Option names are legible and used; the subtitles are not."
  - "p80: the GovCloud TOTP token provider is printed as 'Hypersecu' while p79 names 'Thales' as the TOTP hardware token provider for AWS accounts. Both reproduced as printed - the two provider names are not reconciled and neither is corrected."
  - "p79/p80/p81: the courseware uses 'FIDO security keys' in the MFA-methods list and 'U2F security keys' in the prose and in the p81 step heading. Both terms are used verbatim; neither is normalised to the other."
  - "p82 prints a full 'Steps to Enable SMS MFA for IAM Users' walkthrough, but SMS MFA is NOT in the 'MFA methods that are supported by IAM' list on p79. The walkthrough is recorded as printed, with no claim that IAM supports SMS MFA as a listed method."
  - "p80 Figure 12.28 'Enable Virtual MFA Device' and Figure 12.29 'Scan QR Code for Manual Configuration' are screenshots; their field labels OCR only as fragments ('WA device', 'Select WA device', 'WA to to Authenticator Security Key TOTp', 'Keys'). The option labels Virtual MFA device / Authenticator Security Key / TOTP are legible in the surrounding step text; the figure itself is not transcribed."
  - "p81/p82: the MFA device serial number format is not stated - only 'Type the device serial number (see the back of the device)'. No format is asserted."
  - "p81 Figure 12.30 'Select My Security Credentials Option': the account menu items are legible (My Account / My Organization / My Billing Dashboard / My Security Credentials / Switch Role / Sign Out) but the account alias is OCR'd as 'IAM user Account 123456/89012'; no account id is asserted."
---

[[MOC-Module-12]]

# AWS Password Policy and MFA for Privileged Users (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · area 3 of 6: **configuring password policies
> and enabling MFA for privileged users** _(Mod 12 p40)_
> Covers pp. 77–82: strong password policy (pp77–78) · enable MFA for privileged users
> (pp79–82).

## Strong password policy — the elements the courseware requires _(Mod 12 p77)_

- Purpose printed: "Create a strong password policy and allow IAM users to change their own
  passwords periodically. Users can create a password policy for their AWS accounts on the
  **Account Settings** page of the IAM console."
- Motivation printed on the slide: configure it "to ensure that the user and data are protected
  against **brute-force attacks**". _(Mod 12 p77)_

| # | Required element | Printed value |
|---|---|---|
| 1 | **Minimum length** | "in the range of **6 to 128** characters" |
| 2 | Uppercase | "at least one uppercase character (**A–Z**)" |
| 3 | Lowercase | "at least one lowercase character (**a–z**)" |
| 4 | Numeric | "at least one numeric character (**0–9**)" |
| 5 | Non-alphanumeric | "at least one of the following non-alphanumeric characters" — set unreadable, see `unresolved:` |
| 6 | **Allow users to change their own password** | option |
| 7 | **Enable password expiration** | option |
| 8 | **Prevent password reuse** | option |
| 9 | **Password expiration requires administrator reset** | option |

_(Mod 12 p77)_

## Console path and the policy panel _(Mod 12 p78)_

- Breadcrumb printed above the figure: `IAM > Account Settings > Edit password policy`.
- Two starting options: **IAM default** · **Custom** ("use a password policy"). _(Mod 12 p78)_
- Panel fields (Figure 12.27) _(Mod 12 p78)_:
  - *Password minimum length* — "Enforce a minimum length of **8** characters / needs to be
    between 6 and 128" (8 is the value shown in the figure, not the range minimum).
  - *Password strength* — require at least one uppercase letter from the Latin alphabet (A-Z);
    at least one lowercase letter from the Latin alphabet (a-z); at least one number; at least
    one non-alphanumeric character.
  - *Other requirements* — Turn on password expiration · Password expiration requires
    administrator reset · Allow users to change their own password · Prevent password reuse.
  - Buttons: **Save changes** · **Cancel**.

**Steps to create or change the password policy** _(Mod 12 p78)_ — *rules vs clicks*:

| # | Action |
|---|---|
| 1 | Click on **Account Settings** in the navigation pane of the IAM console |
| 2 | Select the options you want to apply in the **Password Policy** section |
| 3 | Click on **Apply Password Policy** |

- To delete: "click on **Delete Password Policy** in the Password Policy section of
  Account Settings." _(Mod 12 p78)_

## Enable MFA for privileged users — the rule _(Mod 12 p79)_

- "It is recommended to enable **multi-factor authentication (MFA) for privileged users** for
  extra security." _(Mod 12 p79)_
- Slide rationale: "MFA enhances the security for **console and programmatic access**." _(Mod 12 p79)_
- "MFA enables users to use a **device-generated response** for authentication. In such cases,
  **user credentials and the device-generated response** are required to complete the sign-in
  process." _(Mod 12 p79)_
- Why it matters: "With the implementation of MFA, user accounts can be secured **even if the
  credentials or access keys are compromised**." _(Mod 12 p79)_
- Scope: "any method can be used for the privileged IAM users who are **allowed to access
  sensitive resources or API operations**." _(Mod 12 p79)_

**Two response styles** _(Mod 12 p79)_:

| Style | How it works |
|---|---|
| **Virtual and hardware MFA devices** | "generate a code on the app/device, and allow the IAM users to **enter the code on the sign-in screen**" |
| **U2F security keys** | "generate a response when you **tap the device** and allow the IAM users to **finish the sign-in process automatically**" |

## IAM MFA methods — the list as printed _(Mod 12 p79 slide)_

> **IAM MFA Methods:**
> - **FIDO security keys**
> - **Virtual authenticator apps**
> - **TOTP hardware tokens**
> - **TOTP hardware tokens for the AWS GovCloud (US) Regions**

Per-method detail printed _(Mod 12 pp79–80)_:

| Method | Printed description |
|---|---|
| **FIDO Security Keys** | "Third-party providers such as **Yubico** provides FIDO-certified hardware security keys. FIDO is based on **public key cryptography**, which enables strong, **phishing-resistant authentication**. Using a **single security key**, FIDO security keys support **multiple root accounts and IAM users**." |
| **Virtual Authenticator Apps** | "Virtual authenticator apps implements the algorithm **time-based one-time password (TOTP)** and support **multiple tokens on a single device**." |
| **TOTP Hardware Tokens** | "TOTP hardware tokens are provided by **Thales**, a third-party provider. It supports TOTP algorithm and is used **exclusively with AWS accounts**." |
| **TOTP hardware tokens for the AWS GovCloud (US) Regions** | "TOTP hardware tokens are provided by **Hypersecu**, a third-party provider. These tokens are compatible with **AWS GovCloud (US) Regions** and are used **exclusively by IAM users with AWS GovCloud (US) accounts**." |

_(Mod 12 pp79–80)_

Mnemonic: **F**IDO = tap-to-sign-in (phishing-resistant) · **V**irtual app = typed TOTP code ·
**T**hales token = AWS-only hardware TOTP · **H**ypersecu token = GovCloud-only.

## Walkthroughs — click paths only

### Virtual MFA device for IAM users _(Mod 12 p80)_

1. Select **Users** in the navigation pane of the IAM console.
2. Choose the intended MFA user in the **User Name** list.
3. Select the **Security credentials** tab, followed by **Manage** near **Assigned MFA device**.
4. In the **Manage MFA Device** wizard, select **Virtual MFA device**, followed by **Continue**.
5. Open your virtual MFA app. "For a list of apps that you can use for hosting the virtual MFA
   devices, see **Multi-Factor Authentication**."
6. "Decide whether the MFA app supports **QR codes**" and do one of:
   - Select **Show QR code** from the wizard and use the app to scan the QR code; or
   - Select **Show secret key** in the Manage MFA Device wizard and type the secret key in the
     MFA app.
7. In the Manage MFA Device wizard, type the **one-time password (OTP)** that currently appears
   in the virtual MFA device in the **MFA code 1** box.
8. **Wait for 30 seconds** for the device to generate a new OTP, then type the second OTP in the
   **MFA code 2** box.
9. Select **Assign MFA**.

### U2F security key for your own IAM user _(Mod 12 p81)_

1. In the navigation bar on the upper right, select **your username** → **My Security Credentials**.
2. In the **AWS IAM credentials** tab and the **Multi-factor authentication** section, select
   **Manage MFA device**.
3. Select **U2F security key**; then select **Continue** in the Manage MFA device wizard.
4. Insert the U2F security key in the **USB port** of your computer.
5. **Tap** the U2F security key and select **Close** when U2F setup is complete.

### Hardware MFA device for your own IAM user _(Mod 12 pp81–82)_

1. Navigation bar → your username → **My Security Credentials**.
2. AWS IAM credentials tab → **Multi-factor authentication** section → **Manage MFA device**.
3. In the Manage MFA device wizard, select **Hardware MFA device**, followed by **Continue**.
4. Type the **device serial number** (see the back of the device).
5. Type the **six-digit** number displayed by the MFA device in the **MFA code 1** box —
   "Press the button on the front of the device to view the number."
6. **Wait for 30 seconds** while the device refreshes the code, type the next six-digit number
   into the **MFA code 2** box.
7. Press the button on the front of the device again to display the second number and select
   **Assign MFA**.

### SMS MFA for IAM users _(Mod 12 p82)_

1. Select **Users** in the navigation pane.
2. Select the **name (not the checkbox)** of the intended MFA user in the User Name list.
3. Select the **Security credentials** tab.
4. Select **Manage** next to **Assigned MFA device**.
5. Select **An SMS MFA device**, and select **Continue** in the Manage MFA Device wizard.
6. Type the **phone number** to which you want to send MFA codes for this IAM user and select
   **Continue**.
7. Type the **six-digit authentication code** that is immediately sent to the specified phone
   number for verification, then select **Continue**.
8. The wizard ends if AWS successfully verifies the code. Otherwise, click on **Finish** to
   close the wizard.

Upstream: [[12-LO04b-AWS-IAM-Features]] · access levels & least privilege:
[[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] · MFA background:
[[03-LO03-IAM-Authentication-Authorization]]







