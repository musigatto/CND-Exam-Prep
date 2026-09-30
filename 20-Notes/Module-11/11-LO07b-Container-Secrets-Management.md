---
type: note
module: "11"
lo: "07"
tags: [bestpractice, mod/11, flashcard/11]
topic: "Container Secrets Management"
exam_weight: unknown
status: done
unresolved:
  - "The slice names no specific credential-management or secret-store product for this block (contrast the third-party tool catalogue in [[11-LO08b-Docker-Security-Tools]]); none is asserted here."
  - "Slide wording 'Encrypt secrets and latter decrypt using container private key' (typo 'latter' as printed) vs prose 'encrypted and decrypted by the containers private key'. Both kept, not reconciled."
  - "The key-management, storage backend and rotation interval are never specified in the slice - no algorithm, TTL or vault product given."
---

[[MOC-Module-11]]
# Container Secrets Management (§11.07)

Secrets = **passwords, access tokens, API keys**. Must be secured to prevent access by unauthorized users with malicious intent. _(Mod 11 p114)_

## Best practices to protect container secrets _(Mod 11 p114)_

| # | Slide | Prose |
|---|---|---|
| 1 | Do **not** use **environment variables** to store secrets | — |
| 2 | Container **images should not contain secrets** | "The container image should not contain a secret" |
| 3 | **Log all secret operations** | "Ensure that all secret operations are logged" |
| 4 | Transfer secrets using a **secure channel** | "The secret should be transferred through a secure channel" |
| 5 | **Encrypt** secrets, decrypt using the **container private key** | "encrypted and decrypted by the containers private key" |
| 6 | Use **third-party tools** for creating and managing **secret stores** for storing sensitive information | "Credential management tools or secret storage must be adopted while using third party vendor products" |
| 7 | **Rotate secrets periodically** | "rotated on a regular basis" |
| 8 | **Revoke immediately** if a secret is **exposed** | "Exposed secrets must be revoked" |

Prose-only item with no slide counterpart: **each application must assume responsibility for authentication and authorization**. _(Mod 11 p114)_

Runtime angle: the container must know *which* authn/authz secrets are required and *where* they are needed, and how they are configured, stored and managed. → [[11-LO07a-Container-Security-Measures]] _(Mod 11 p116)_
Image angle: keep secrets out of the image build, and out of the container/Dockerfile. → [[11-LO08c-Docker-Security-Best-Practices]] _(Mod 11 p113, p128)_

## Cards

Which three container secrets does the courseware name as needing protection?
?
Passwords, access tokens, and API keys - they must be secured to prevent them from being accessed by unauthorized users with malicious intent. _(Mod 11 p114)_

Container secrets: give the full handling chain from transfer to revocation.
?
Transfer through a secure channel, encrypt and decrypt with the container's private key, store in a secret store created and managed with third-party credential-management tools, rotate on a regular basis, revoke immediately if exposed - and log all secret operations. _(Mod 11 p114)_

Two placement rules for secrets: where must they never live?
?
Not in environment variables, and not inside the container image (nor in the container file / Dockerfile). _(Mod 11 p114)_

One secrets-management responsibility the courseware assigns to the application itself.
?
Each application must assume responsibility for authentication and authorization. _(Mod 11 p114)_
