---
type: note
module: "11"
lo: "09"
tags: [policy, bestpractice, mod/11, flashcard/11]
topic: "Kubernetes Audit Policy"
exam_weight: unknown
status: done
unresolved:
  - "p.139 slide bullet reads only 'Audit logs periodically' with no object after it - appears truncated, so no rotation/retention practice is asserted."
  - "p.140 Figure 11.36 is an image; the YAML was recovered from the identical block printed on p.139 (same tokens, same order). No audit-log rotation/retention flags, no request/response level names and no webhook backend appear anywhere in pp.139-140."
---

[[MOC-Module-11]]
# Kubernetes Audit Policy (§11.09)

## What audit logging does _(Mod 11 p139)_

- Audit logs contain a **record of the activities of users, administrators, or system components that have affected the system**. _(Mod 11 p139)_
- **Audit logging features customize API logging at both the metadata level and the payload** (for example, request and response). **These log levels can be set per the policy of the organization.** _(Mod 11 p139)_

| Request type | What the audit log stores |
|---|---|
| **Read** — `get`, `list`, `watch` | The **request object** is exported to the audit logs |
| **Sensitive data** — `Secret`, `ConfigMap` | Only the **metadata** is saved in the audit logs |
| **All remaining requests** | The **requests** are exported to the audit logs |

## Questions the logs must answer _(Mod 11 p139)_

Mnemonic, in printed order — **W W W W W W W**: **What** happened · **When** did it happen · **Who** initiated it · **What** did it happen on · **Where** was it observed · **Where** was it initiated · **Where** was it going. _(Mod 11 p139)_

## Minimal audit policy file _(Mod 11 p139–p140)_

**Log all requests at the Metadata level.** Figure 11.36 "Minimal Audit Policy File" _(Mod 11 p140)_:

```yaml
# Log all requests at the Metadata level.
apiVersion: audit.k8s.io/v1
kind: Policy
rules:
- level: Metadata
```

- `audit.k8s.io/v1` API group, `kind: Policy`, a single `rules` entry with `level: Metadata` — the **minimal** policy that still records every request. _(Mod 11 p140)_
- The slice gives **no** further levels, rotation/retention flags or output backends for the audit subsystem — see `unresolved`.

## Cards

Kubernetes audit logs: what do they record?
?
A record of the activities of users, administrators, or system components that have affected the system. Audit logging customizes API logging at the metadata level and at the payload (request and response), set per organizational policy. _(Mod 11 p139)_

What is stored in the audit logs for read requests (get, list, watch) versus for Secret and ConfigMap requests?
?
Read requests: the request object is exported. Secret and ConfigMap: only the metadata is saved. All remaining requests are exported. _(Mod 11 p139)_

List the seven questions Kubernetes audit logs must let cluster administrators answer.
?
What happened · When did it happen · Who initiated it · What did it happen on · Where was it observed · Where was it initiated · Where was it going. _(Mod 11 p139)_

Minimal audit policy file: what are the apiVersion, kind and rule level?
?
apiVersion audit.k8s.io/v1, kind Policy, rules with a single entry - level: Metadata (Figure 11.36) - logs all requests at the Metadata level. _(Mod 11 p140)_

Which of these is NOT stated in the Kubernetes audit-policy guidance of Module 11?
?
Audit-log rotation, retention and backends - the slice only gives the minimal Metadata-level policy file. See unresolved. _(Mod 11 p139)_

Audit logging in Kubernetes customizes API logging at which two levels?
?
At the metadata level and at the payload (for example, request and response); the levels can be set as per the policy of the organization. _(Mod 11 p139)_
