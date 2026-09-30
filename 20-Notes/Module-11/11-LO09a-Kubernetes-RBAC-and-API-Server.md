---
type: note
module: "11"
lo: "09"
tags: [policy, bestpractice, mod/11, flashcard/11]
topic: "Kubernetes RBAC and API Server Hardening"
exam_weight: unknown
status: done
unresolved:
  - "p.134 Figure 11.33 (RBAC Example), RoleBinding subject name OCRs as 'sa7' (could be 'sa1'/'sa7') - kept as printed, digit not certain."
  - "p.134 Figure 11.33, Role rule values did not OCR: only the tokens 'apiGroups:', 'resources:', '[\"roles\"]', 'POD', 'list', 'get' and the table row 'POD list get' survived. The values are not reproduced and no rule set is asserted."
  - "p.134 Figure 11.33 caption sits on p.135 ('Role ... Figure 11.33: RBAC Example'); the key/indentation order of 'metadata / name / namespace' was reconstructed from the token order - the figure itself did not OCR with indentation."
  - "p.132 ABAC policy example: the JSON pairs are printed in the figure with key/value order swapped by OCR ('. \"Bob \"user'); pairings restored as user=Bob, namespace=Demo, resource=pods, readonly=true from the sentence above the figure."
  - "p.137 container runtime examples OCR as 'Docker, container, Kubernetes container runtime interface (CRI) implementations, and CRI-O' - the second item is a garbled token, not repaired."
---

[[MOC-Module-11]]
# Kubernetes RBAC and API Server Hardening (§11.09)

LO#09 target: explain the **guidelines, best practices, and recommendations for the security of Kubernetes**; each subsection states one in detail. _(Mod 11 p130)_

Block order in this range: **RBAC/ABAC → TLS → control-plane & node components**; the image / namespace / capability boundaries of the same LO#09 range are kept at the end. Audit policy → [[11-LO09b-Kubernetes-Audit-Policy]]; network policies, PodSecurityPolicy, Secrets → [[11-LO09c-Kubernetes-Pod-Security-Policy]]; tools, CIS, patching → [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]].

## Enable RBAC with least privilege, disable ABAC _(Mod 11 p134)_

- **Implement role-based access control (RBAC)** to separate roles and permissions and **decrease the attack surface**. The RBAC feature of the Kubernetes **authorization module** is used for fine-grained policy management and restricting access to resources such as namespaces. _(Mod 11 p134)_
- The RBAC API **prevents users from escalating privileges by editing roles or role bindings**. Because this is **enforced at the API level**, it applies **even when the RBAC authorizer is not in use**. _(Mod 11 p134, p135)_
- A user can **only create or update a role if they already have all the permissions contained in the role, and at the same scope as the role** — cluster-wide for a `ClusterRole`, within the same namespace for a `Role`. _(Mod 11 p134; p135 restates it as "within the same namespace or cluster-wide for a Role")_
- **Disable attribute-based access control (ABAC) on the API server.** Kubernetes' ABAC is **swapped with RBAC since release 1.6**. _(Mod 11 p135)_

Access-control models in general: [[03-LO01-Access-Control-Models]], [[03-LO02-Zero-Trust-and-Distributed-Access]].

| API server flag | Effect |
|---|---|
| `--authorization-mode=RBAC` | Disable ABAC, use RBAC instead _(Mod 11 p135)_ |
| `--no-enable-legacy-authorization` | The flag given to disable it **in GKE** _(Mod 11 p135)_ |

## RBAC structure — three parts _(Mod 11 p135)_

| Part | What it is | Scope |
|---|---|---|
| **Role / ClusterRole** | The original permission; consists of **rules** → **resources + verbs** (a rule = verbs performed on resources) | Role → namespace · ClusterRole → cluster |
| **Subject** | Entity requiring permissions: **User, Group, or ServiceAccount** | — |
| **RoleBinding / ClusterRoleBinding** | The connection between Role/ClusterRole and the subject | RoleBinding → Role **within a namespace** · ClusterRoleBinding → ClusterRole **cluster-wide** |

Worked procedure as printed _(Mod 11 p134)_:

| Goal | Steps |
|---|---|
| User **Smith** lists pods in namespace `demo` | (Smith already authenticated) create a **Role** `listpods` for namespace `demo` with verb `list` → create a **RoleBinding** binding Smith + `listpods` |
| User **David** lists pods cluster-wide | (David already authenticated) create a **ClusterRole** `democlusterrole` for verbs `get` and `list` → create a **ClusterRoleBinding** binding David + `democlusterrole` |

### Figure 11.33 — RBAC example _(Mod 11 p134)_

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: edit-role-rolebinding
  namespace: default
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: Role
  name: edit-role
subjects:
- kind: ServiceAccount
  name: sa7
  namespace: default
```

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: edit-role
  namespace: default
apiGroups:
resources:
```

→ After `resources:` the printed values did not OCR (only `["roles"]`, `POD`, `list`, `get` survived), so no rule set is reproduced. The figure also prints the table `POD · list · get`, `RoleBinding / ClusterRoleBinding`, `Role / ClusterRole`, `Subject — User · Group · ServiceAccount` and the example names `Pod-reader` / `pod-reader`. See `unresolved`. _(Mod 11 p134)_

## Kubernetes security: TLS _(Mod 11 p136)_

- **Enable TLS for the components that support it** — for **traffic-sniffing prevention, server identity verification, and client identity verification**. _(Mod 11 p136)_
- Kubernetes **expects encryption with TLS by default** for the cluster's API communications; most installation methods create and distribute the necessary certificates. _(Mod 11 p136)_
- **However**, local ports over **HTTP** may sometimes be enabled by some components and installation methods → administrators should **familiarize themselves with the component's settings for the identification of unsecured traffic**. _(Mod 11 p136)_
- Figure 11.35: TLS applied **between every component on the master/control plane** and **between the Kubelet and API server**; master components shown = `Controller Manager`, `etcd (key value DB, SSOT)`, `API server (REST API)`, `Scheduler`; node side = `Kubelet`, `Container Runtime`, `os`. _(Mod 11 p136)_

Certificate lifecycle: [[10-LO04a-Browser-WebServer-TLS-Certificates]], [[10-LO04b-IIS-SSL-Certificate-Lifecycle]].

## Control plane and node components _(Mod 11 p137–p138)_

**Control plane** — makes global decisions, detects and responds to cluster events (e.g. scheduling or starting a new pod if a deployment's `replicas` field is unsatisfied).

- The components **can run on any machine in the cluster**; setup scripts start **all control-plane components on the same machine**, and it is recommended that **user containers are not run on that machine**. _(Mod 11 p137)_
- **API server** — front end of the control plane, binary `kube-apiserver`; **scales by deploying more instances** (horizontal scaling), which **balances traffic between the instances**. _(Mod 11 p137)_
- **etcd** — serves as the cluster data **backing store**; **ensure a backup plan for the cluster data** if etcd is the backing store. _(Mod 11 p137)_
- **Scheduler** — monitors for new pods with no assigned node and assigns one. Influencing factors: **resource requirements** · **hardware, software, and policy constraints** · **affinity and anti-affinity specifications** · **data locality** · **inter-workload interference and deadlines**. _(Mod 11 p137)_
- **Controller manager** — all controller processes are **combined into a single binary and run as a single process** to minimize complexity. _(Mod 11 p137)_

| Controller | Job |
|---|---|
| Node controller | Detects and responds when nodes go down |
| Replication controller | Maintains the correct number of pods for the replication controller object |
| Endpoints controller | Populates the endpoints object (e.g. combines services and pods) |
| Service account + token controllers | Create default accounts and API access tokens for new namespaces |

**Node components** run on all nodes; they **maintain running pods and provision the Kubernetes runtime environment**. _(Mod 11 p137)_

- **Kubelet** — agent running on each cluster node; ensures the running of containers in a pod. _(Mod 11 p138)_
- **Container runtime** — software focused on running containers; examples printed: Docker, *(one token garbled)*, Kubernetes **container runtime interface (CRI)** implementations, and **CRI-O**. _(Mod 11 p138)_

## Same LO#09 range — image, namespace, and capability boundaries _(Mod 11 p131–p133)_

### Know the base image when building containers _(Mod 11 p131)_

Best practice: **be aware of and understand all the component software in the container** → enables building a secure container. Two guidelines:

| Guideline | Detail |
|---|---|
| **Use a small image** | Minimal base image without unnecessary software that can create a bigger attack surface; fewer components **restrict the attack vectors**; **check images for vulnerabilities regularly**; smaller images consume fewer bytes on disk and reduce network traffic. **BusyBox** and **Alpine** given as examples of tools for building small images. Use the **official image** or start from the base image |
| **Do not depend on the `:latest` tag** | The current latest image might not always remain latest; it may cause building container images against a version. **Use the specific version number as the tag** and update the version number |

### Use namespaces to create security boundaries _(Mod 11 p132)_

- A namespace **divides cluster resources into logically named groups**; **resources allocated to one namespace are not visible to other namespaces**. *(OCR prints "kube-pubhc")* _(Mod 11 p132)_
- **Separates sensitive workloads** and **reduces the impact of a compromise**; security controls such as **network policies** apply to workloads in the different namespaces. _(Mod 11 p132)_
- Create a policy with the **Kubernetes authorization plugins** to divide access to a namespace's resources between users. `kubectl get namespace` prints: `default` · `kube-system` · `kube-public` — all `Active`, age `1d`. _(Mod 11 p132)_

ABAC example printed as the way to let Bob read pods in namespace `Demo` — the very model LO#09 tells you to disable: _(Mod 11 p132)_

```json
"abac.authorization.kubernetes.io/v1beta1"
"kind": "Policy",
"spec": {
  "user": "Bob",
  "namespace": "Demo",
  "resource": "pods",
  "readonly": true
}
```

### Restrict Linux capabilities _(Mod 11 p133)_

- **Linux capabilities** limit unrestricted superuser access and give finer-grained permissions — and **attackers can escalate privileges using them**. Restrict them with **PodSecurityPolicy**. _(Mod 11 p133)_
- These PodSecurityPolicy fields take a list of capabilities, **specified as the capability name in ALL CAPS without the `CAP_` prefix**. _(Mod 11 p133)_

| Field | Meaning |
|---|---|
| `AllowedCapabilities` | Whitelist of capabilities that **may be added** to a container |
| `RequiredDropCapabilities` | Capabilities **dropped** from containers — removed from the default set and **must not be added**; must not contain anything in `AllowedCapabilities` or `DefaultAddCapabilities` |
| `DefaultAddCapabilities` | Capabilities **added by default**, in addition to the runtime defaults |

## Cards

Kubernetes RBAC: why is privilege escalation blocked even when the RBAC authorizer is not in use?
?
Because the RBAC API enforces it at the API level - editing roles or role bindings is blocked regardless of the active authorizer. _(Mod 11 p134)_

Condition for creating or updating a role in Kubernetes RBAC.
?
The user must already hold all the permissions contained in the role AND at the same scope - cluster-wide for a ClusterRole, within the same namespace for a Role. _(Mod 11 p134)_

The three parts of Kubernetes RBAC permissions.
?
Role or ClusterRole (rules = resources + verbs; Role = namespace, ClusterRole = cluster) · Subject (User, Group, ServiceAccount) · RoleBinding or ClusterRoleBinding joining them (namespace-scoped vs cluster-wide). _(Mod 11 p135)_

How to disable ABAC on the API server.
?
Kubernetes' ABAC is swapped with RBAC since release 1.6. Use --authorization-mode=RBAC, or in GKE --no-enable-legacy-authorization. _(Mod 11 p135)_

PodSecurityPolicy fields that take a list of Linux capabilities, and the naming rule.
?
AllowedCapabilities, RequiredDropCapabilities, DefaultAddCapabilities - capability name in ALL CAPS without the CAP_ prefix. _(Mod 11 p133)_

Kubernetes container image guidelines for a small image, and the :latest tag.
?
Minimal base image, few components restrict attack vectors, check for vulnerabilities regularly (BusyBox, Alpine given as examples); do not depend on :latest - use the specific version number as the tag and update it. _(Mod 11 p131)_
