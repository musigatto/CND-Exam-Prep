---
type: note
module: "11"
lo: "09"
tags: [policy, bestpractice, mod/11]
topic: "Kubernetes Network Policies, PodSecurityPolicy and Secrets"
exam_weight: unknown
status: done
unresolved:
  - "p.141 default-deny-ingress figure: 'podSelector: {' is printed with an opening brace only - the closing token did not OCR and is not supplied."
  - "p.141 test-network-policy figure: the 'namespace: default' key is printed in the metadata block without indentation in OCR, so it is rendered under metadata; the egress port prints as 5978 while the ingress port of the same figure prints as 6379 - both kept as printed, neither corrected."
  - "p.143 Figure 11.38 (access-nginx): the label pair OCRs as '\"true\" access:' (value before key); restored as access: \"true\" from the sentence stating that only pods with the label access: true can query the service."
  - "p.144 slide callout for the restrict-root policy is too garbled to reproduce (apiVersion printed as 'extensions', 'metadta', 'pr ledged', 'supp'); only the p.146 Figure 11.41 form is reproduced. The activation command 'kubectl create -f restrict-root.yaml' is legible on both."
  - "Figure 11.40 prints runAsUser rule 'MustRunAsNonRoot' while Figure 11.41 prints 'mustRunAsNonRoot' - case kept exactly as printed in each figure; the module does not reconcile them."
  - "p.147 Figure 11.43 (restrict-ports): the hostPorts min and max values did not OCR and are not supplied."
  - "p.148-150 provider table: the Strength and Key length columns did not OCR in column order. Encryption and Other considerations are reproduced; the legible key-length values are 32-byte (secretbox), 32-byte (aesgcm) and 16, 24, or 32-byte (kms). The 'Must be rotated every 200k writes' cell is attributed to aesgcm by its position in the list; the Strength column is not reproduced."
  - "p.149 Figure 11.44: the 'secret:' value of every key1 entry did not OCR (only key2 shows dGhpcyBpcyBwYXNzd29yZA==); the figure also shows both an 'aesgcm' and an 'aescbc' provider block."
  - "p.142 the CLUSTER-IP of service/kubernetes prints as '10.100.e.1' - kept as printed, not repaired."
  - "p.151 the --from-literal= value of 'kubectl create secret generic secret1' did not OCR and is not supplied."
---

[[MOC-Module-11]]
# Kubernetes Network Policies, PodSecurityPolicy and Secrets (§11.09)

Cluster policy recommendations of LO#09 in page order: **network policies → PodSecurityPolicy → secrets at rest**. RBAC and API-server hardening: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]; tools and patching: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]].

## Implement network policies _(Mod 11 p141–p143)_

- A **NetworkPolicy is a specification describing how groups of pods can communicate with each other and with other network endpoints**; it applies **labels to select pods** and defines rules for the traffic allowed among the selected pods. _(Mod 11 p141)_
- **Default state: all pods can talk to all other pods — pods are non-isolated by default.** Therefore create a network policy to restrict pod-to-pod communication. _(Mod 11 p141, p142)_
- If a NetworkPolicy exists in a namespace and it **selects a particular pod**, that pod **rejects any communication not allowed by the policy**. _(Mod 11 p142)_
- **NetworkPolicy resources are additive**: if multiple policies select a pod, the pod is isolated based on the **union** of the policies' rules. _(Mod 11 p141)_
- Pod isolation is the network-segmentation control applied at cluster level: [[03-LO06-Network-Segmentation]].

### Samples printed in the module _(Mod 11 p141)_

Deny all ingress by default — `service/networking/network-policy-default-deny-ingress.yaml`:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-ingress
spec:
  podSelector: {
  policyTypes:
  - Ingress
```

Sample network policy (`test-network-policy`, namespace `default`):

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: test-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      role: db
  policyTypes:
  - Ingress
  - Egress
  ingress:
  - from:
    - ipBlock:
        cidr: 172.17.0.0/16
        except:
        - 172.17.1.0/24
    - namespaceSelector:
        matchLabels:
          project: myproject
    - podSelector:
        matchLabels:
          role: frontend
    ports:
    - protocol: TCP
      port: 6379
  egress:
  - to:
    - ipBlock:
        cidr: 10.0.0.0/24
    ports:
    - protocol: TCP
      port: 5978
```

→ `podSelector: {` in the first block and the `namespace:` placement in the second were not captured with full punctuation/indentation — see `unresolved`.

### Steps to create a policy to restrict communication among pods _(Mod 11 p142–p143)_

| Step | Detail |
|---|---|
| 1 | Configure `kubectl` to talk to the cluster; if there is no cluster, create one with a playground such as **Minikube, Katacoda, or Play with Kubernetes** |
| 2 | Ensure the server version is **higher than v1.8** — `kubectl version` |
| 3 | Ensure a **network provider with network policy support** — **Calico, Cilium, Kube-router, or Romana** |

```bash
kubectl create deployment nginx --image=nginx
# deployment.apps/nginx created
kubectl expose deployment nginx --port=80
# service/nginx exposed
kubectl get svc, pod
```

`kubectl get svc, pod` output: `service/kubernetes` `10.100.e.1` `443/TCP`; `service/nginx` `10.100.0.16` `80/TCP`; `pod/nginx-701339712-e0qfq` `1/1 Running` — both in the **`default` namespace** (Figure 11.37). The `CLUSTER-IP` of `service/kubernetes` prints as `10.100.e.1` and is kept as printed — see `unresolved`. _(Mod 11 p142)_

Test the service from another pod, then limit access _(Mod 11 p142–p143)_:

```bash
kubectl run --generator=run-pod/v1 busybox -- /bin/sh
rm -ti --image=busybox
# then run in the shell:
wget --spider timeout=1 nginx
# Connecting to nginx (10.100.0.16:80) / remote file exists
```

→ the `kubectl run` for busybox is printed split over two lines on the slide and is reproduced in that form. _(Mod 11 p142)_

Restrict the nginx service so that **only pods with the label `access: true` can query it** (Figure 11.38) _(Mod 11 p143)_:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: access-nginx
spec:
  podSelector:
    matchLabels:
      app: nginx
  ingress:
  - from:
    - podSelector:
        matchLabels:
          access: "true"
```

```bash
kubectl apply -f https://k8s.io/examples/service/networking/nginx-policy.yaml
# networkpolicy.networking.k8s.io/access-nginx created
```

**Test the policy** — unlabelled pod: `wget --spider timeout=1 nginx` → `wget: download timed out`; labelled pod → `remote file exists`. _(Mod 11 p143)_

```bash
kubectl run --generator=run-pod/v1 demo --rm -ti --image=demo -- /bin/sh --labels="access=true"
wget --spider timeout=1 nginx
```

## Secure the cluster with PodSecurityPolicy _(Mod 11 p144–p147)_

- **Pod security policies provide central cluster-level configuration and security controls.** A `PodSecurityPolicy` resource **represents the conditions a pod must satisfy to run in the cluster**. _(Mod 11 p144, p145)_
- **Use pod security policies only if they are enabled in the cluster's admission controller** — check with `kubectl get psp`. _(Mod 11 p144)_

| `kubectl get psp` output | Meaning |
|---|---|
| `the server doesn't have a resource type "podSecurityPolicies"` | Server **does not support** pod security policies _(Mod 11 p144)_ |
| `No resources found` | Server **does** support them (Figure 11.39) _(Mod 11 p144)_ |

Enable support on Minikube by starting it with the recommended admission plugins _(Mod 11 p145)_:

```bash
minikube start --extra-config=apiserver.GenericServerRunOptions.AdmissionControl=NamespaceLifecycle,LimitRanger,ServiceAccount,PersistentVolumeLabel,DefaultStorageClass,ResourceQuota,DefaultTolerationSeconds,PodSecurityPolicy
```

On any other platform, check the **cluster vendor's documentation** for whether pod security policy support is enabled by default and how to enable it. **The examples are tested on a Minikube cluster running Kubernetes v1.6.4** and apply to any cluster with pod security policy support. _(Mod 11 p145)_

### Figure 11.40 — pod security policy expressed in YAML _(Mod 11 p145)_

```yaml
apiVersion: extensions/v1beta1
kind: PodSecurityPolicy
metadata:
  name: example
spec:
  privileged: false
  runAsUser:
    rule: MustRunAsNonRoot
  seLinux:
    rule: RunAsAny
  fsGroup:
    rule: RunAsAny
  supplementalGroups:
    rule: RunAsAny
  volumes:
  - nfs
  hostPorts:
  - min: 100
    max: 100
```

Security rules implemented by that policy _(Mod 11 p145)_:

1. Do **not** allow containers running in **privileged mode**.
2. Do **not** allow containers that require **root privileges**.
3. Do **not** allow containers that access volumes **apart from NFS volumes**.
4. Do **not** allow containers that access **host ports apart from port 100**.

### Prevent pods from running with root privileges _(Mod 11 p146)_

Create the policy below and **save it as `restrict-root.yaml`** (Figure 11.41) _(Mod 11 p146)_:

```yaml
apiVersion: extensions/v1beta1
kind: PodSecurityPolicy
metadata:
  name: restrict-root
spec:
  privileged: false
  runAsUser:
    rule: mustRunAsNonRoot
  seLinux:
    rule: RunAsAny
  fsGroup:
    rule: RunAsAny
  supplementalGroups:
    rule: RunAsAny
  volumes:
```

**Activate the policy — this command creates a new policy from the file** _(Mod 11 p146)_:

```bash
kubectl create -f restrict-root.yaml
```

→ `MustRunAsNonRoot` in Fig 11.40 vs `mustRunAsNonRoot` in Fig 11.41: both kept exactly as printed — see `unresolved`.

### Prevent pods from accessing the volume type NFS _(Mod 11 p146)_

**Restrict the available storage choices for containers to reduce costs or avoid accessing information**, by specifying the allowed volume types in the **`volumes` key** of a pod security policy and installing that policy (Figure 11.42) _(Mod 11 p146)_:

```yaml
apiVersion: extensions/v1beta1
kind: PodSecurityPolicy
metadata:
  name: restrict-volumes
spec:
  privileged: false
  runAsUser:
    rule: RunAsAny
  seLinux:
    rule: RunAsAny
  fsGroup:
    rule: RunAsAny
  supplementalGroups:
    rule: RunAsAny
  volumes:
  - nfs
```

### Prevent pods from accessing host ports _(Mod 11 p147)_

Cluster administrators can use pod security policies to restrict the containers' access to **host resources such as host ports or network interfaces** (Figure 11.43) _(Mod 11 p147)_:

```yaml
apiVersion: extensions/v1beta1
kind: PodSecurityPolicy
metadata:
  name: restrict-ports
spec:
  privileged: false
  runAsUser:
    rule: RunAsAny
  seLinux:
    rule: RunAsAny
  fsGroup:
    rule: RunAsAny
  supplementalGroups:
    rule: RunAsAny
  volumes:
  hostPorts:
  - min: `<not legible in the source figure>`
    max: `<not legible in the source figure>`
```

## Use Kubernetes Secrets _(Mod 11 p148–p151)_

- **Do not use a config file for storing secrets — use Kubernetes Secrets.** Secrets enable storing and managing **confidential data such as passwords, tokens, and keys**; this is **safer and more flexible than storing the sensitive data verbatim in a pod specification or a container image**. _(Mod 11 p148)_

### Secret encryption providers _(Mod 11 p148, p150)_

| Provider | Encryption | Other considerations |
|---|---|---|
| `identity` | None | Resources written as-is without encryption. When set as the **first** provider, the resource will be **decrypted as new values are written** |
| `aescbc` | AES-CBC with PKCS#7 padding | **Recommended choice for encryption at rest**, but may be slightly slower than `secretbox` |
| `secretbox` | XSalsa20 and Poly1305 | A **newer standard**; may not be considered acceptable in environments that require **high levels of review** |
| `aesgcm` | AES-GCM with random nonce | **Not recommended** for use except when an **automated key rotation scheme** is implemented; **must be rotated every 200k writes** |
| `kms` | **Envelope encryption**: data is encrypted by **data encryption keys (DEKs)** using AES-CBC with PKCS#7 padding, and the DEKs are encrypted by **key encryption keys (KEKs)** according to the configuration in the **Key Management Service (KMS)** | **Recommended choice for using a third-party tool for key management**; simplifies key rotation (new DEK per encryption, KEK rotation controlled by the user). **The KMS provider must be configured** |

- All providers **support multiple keys for encryption and decryption**. **Use the `kms` provider for enhanced security**, because `EncryptionConfig` provides only **moderate** security for the stored encryption keys in it. The `identity` provider **protects secrets in etcd but does not provide encryption**. _(Mod 11 p150)_

### Encryption at rest — enable and configure _(Mod 11 p149)_

| Step | Detail |
|---|---|
| 1 | Configure `kubectl`; no cluster → create one with a playground such as **Minikube, Katacoda, or Play with Kubernetes** |
| 2 | Server version **higher than or equal to v1.13** (`kubectl version`) and **etcd version v3.0 or later** |
| 3 | The `kube-apiserver` process takes the argument **`--encryption-provider-config`**, which controls the encryption of API data in etcd |

Figure 11.44 — encryption at rest configuration _(Mod 11 p149)_:

```yaml
apiVersion: apiserver.config.k8s.io/v1
kind: EncryptionConfiguration
resources:
- resources:
  - secrets
  providers:
  - identity: {}
  - aesgcm:
      keys:
      - name: key1
        secret: `<not legible in the source figure>`
      - name: key2
        secret: dGhpcyBpcyBwYXNzd29yZA==
  - aescbc:
      keys:
      - name: key1
        secret: `<not legible in the source figure>`
      - name: key2
        secret: dGhpcyBpcyBwYXNzd29yZA==
  - secretbox:
      keys:
      - name: key1
        secret: `<not legible in the source figure>`
```

- **Every `resources` array item constitutes a complete configuration.** `resources.resources` is an **array of Kubernetes resource names**; `providers` is an **ordered list** of the possible encryption providers (`identity` or `aescbc`). _(Mod 11 p149)_
- **Note:** delete the key **from etcd directly** when a resource is **not readable through the encryption config**. _(Mod 11 p149)_

### Steps to encrypt the data _(Mod 11 p150)_

**Create a new encryption config file** (Figure 11.46) _(Mod 11 p150)_:

```yaml
apiVersion: apiserver.config.k8s.io/v1
kind: EncryptionConfiguration
resources:
- resources:
  - secrets
  providers:
  - aescbc:
      keys:
      - name: key1
        secret: `<BASE 64 ENCODED SECRET>`
  - identity: {}
```

**Create a new secret** _(Mod 11 p150)_:

1. **Generate a 32-byte random key** and **encode it to base64**. For Linux and macOS: `head -c 32 /dev/urandom | base64`
2. Enter the resulting value in the **`secret`** field.
3. **Set the flag on the `kube-apiserver`** to point to the location of the config file.
4. **Restart the API server.**

> **Caution:** restrict permissions on master to ensure **only the user who runs the `kube-apiserver` can read it**, since the config file **contains the keys for decrypting etcd content**. _(Mod 11 p150)_

### Verify that the data is encrypted _(Mod 11 p151)_

```bash
kubectl create secret generic secret1 -n default --from-literal=`<not legible in the source figure>`
ETCDCTL_API=3 etcdctl get /registry/secrets/default/secret1 --hexdump -C
```

- `[...]` in the etcdctl line refers to **additional arguments for connecting to the etcd server**. _(Mod 11 p151)_
- Ensure the stored secret is **prefixed with `k8s:enc:aescbc:v1:`** → the `aescbc` provider encrypted the data. _(Mod 11 p151)_
- Ensure the secret is **decrypted correctly when retrieved through the API**: `kubectl describe secret secret1 -n default`. _(Mod 11 p151)_

### Ensure all secrets are encrypted _(Mod 11 p151)_

Update the secrets used for encrypting content; **retry the command if it triggers an error**, and **divide the secrets by namespace or use a script for the update in case of large clusters**. _(Mod 11 p151)_

```bash
kubectl get secrets --all-namespaces -o json | kubectl replace -f -
```

Data-at-rest encryption mechanisms in general: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]], [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]].







