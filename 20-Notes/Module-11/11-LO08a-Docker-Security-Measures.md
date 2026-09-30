---
type: note
module: "11"
lo: "08"
tags: [bestpractice, tool, mod/11, flashcard/11]
topic: "Docker Security Measures"
exam_weight: unknown
status: done
unresolved:
  - "p.122 the 'limit a container to 1GB of memory' run-command option string is set in a figure and did not OCR (the CPU one did, as --cpus=2). The memory flag is therefore NOT stated in this note - do not guess it."
  - "p.122 the two figure commands ('Set resource limit for memory in a container' and 'Set resource limit for CPU in a container') are images; only the CPU flag --cpus=2 is legible in the slide text, and the rest of both commands is unverified."
  - "p.121 OCR prints the DCT env var as 'DOCKER CONTENT _ TRUST-I' - read here as DOCKER_CONTENT_TRUST=1 (high confidence from the environment-variable shape, not literal)."
  - "p.121 the unsigned-image error text OCR'd as 'Error: remote trust data does not exist for docker. ioznonongazuordpress : aue trust data for docker. ioznomongazuordpress notary. docker. io does not h' - the image name is garbled (elsewhere in the slice 'auonongazuordpress' = the appcontainers/wordpress search entry) and is elided below rather than guessed."
  - "p.123 'Docker Hub (paid service) scans the repositories you use' is a slide-only claim; the p.123 prose does not repeat it."
---

[[MOC-Module-11]]
# Docker Security Measures (§11.08)

Framing: the previous section covered containers **in general**; these issues and measures "pertain particularly to Dockers". _(Mod 11 p119)_
Block order: **security features → content trust → resource limits → picking sources → third-party tools**. Tools → [[11-LO08b-Docker-Security-Tools]]; image build rules → [[11-LO08c-Docker-Security-Best-Practices]]. _(Mod 11 p120–p126)_

## Docker security features _(Mod 11 p120)_

Adoption of Docker for development/production "has tremendously increased" → Docker-specific measures are crucial.

| Feature | Kernel mechanism | What it gives in Docker |
|---|---|---|
| **Cgroups** | Linux kernel feature to **manage, restrict and audit groups of processes** | Control/limit container access to **CPU, memory, swap, block IO (rates), network**; e.g. set a memory limit |
| **LSMs** | Linux security modules **AppArmor** and **SELinux**, supported in the Docker engine (**via runc**) | **Default profile** applied for engine and containers; e.g. limit access to specific filesystem paths in the container |
| **Capabilities** | Split root privileges, distribute individually **on a thread basis** without granting all permissions to a process at a time | Docker allows **only 14 of the 37 Linux capability groups by default**; add or remove as required; drop unnecessary capabilities |
| **Seccomp** | Secure computing mode — restricts actions within a container | **Fine-grained per-syscall control**; default profile **limits many syscalls**; blocks specific syscalls used by container binaries |
| **Userns** | Isolates the running process, limits access to system resources | User namespaced processes **remap root to unprivileged IDs on the host**; Docker supports **global uid/gid mapping**; can enable user namespaces on the daemon for all containers |

## Docker security: enable Docker content trust (DCT) _(Mod 11 p121)_

- Verifies **authenticity, integrity and publication date** of Docker images in the **Docker Hub registry**.
- **Disabled by default.** Enable it for **signing and verifying** images that users build, push to, or pull from Docker Hub.
- Guarantees the images are **reliable and signed**; with DCT enabled, **signed** images are the ones retrieved by `docker pull`.

```
sudo export DOCKER_CONTENT_TRUST=1
```

Pulling an unsigned image → the trust error, image name garbled in the source: _(Mod 11 p121)_

```
Error: remote trust data does not exist for docker.io/<image>
notary.docker.io does not have trust data for docker.io/<image>
```

## Docker security: set resource limits for containers _(Mod 11 p122)_

**Default state: a container has no limit on resources and can utilize as much resource as the host scheduler provides.** Docker controls the amount of memory or CPU provided to the container; setting these limits requires the **limit-setting capability of Linux, supported by the kernel**. _(Mod 11 p122)_

**Why cap memory:** a container consuming a considerable amount of host memory makes the kernel throw an **out-of-memory exception (OOME)** and kill other processes to free memory — which can collapse the whole system if a crucial process dies. Docker therefore imposes either: _(Mod 11 p122)_

- **Hard memory limits** — the container may only use a particular amount of system memory.
- **Soft memory limits** — the container may use memory without constraints under conditions such as the kernel detecting overall low memory usage.

| Limit | Stated option |
|---|---|
| Limit a container to **2 CPUs** | add the `--cpus=2` option to the `run` command |
| Limit a container to **1 GB of memory** | add the corresponding option to the `run` command — *the flag string is in a figure and did not OCR* |

The figure examples note that **`m` represents megabytes**. _(Mod 11 p122)_

## Docker security: select third-party tools carefully _(Mod 11 p123)_

Risk: a user can pull containers from public repositories **without knowing whether the containers were created securely**; a container might have **malicious or corrupt files**. Mitigation: pull containers **only from reliable sources such as the Docker Hub**. _(Mod 11 p123)_

```
sudo docker search WordPress      # prose form
docker search --filter WordPress  # slide form
```

The results list a WordPress entry plus relevant third-party entries such as `bitnami/wordpress` and `appcontainers/wordpress`, and the **first entry in the list is the official image** — the marker used to **distinguish official sources from third-party sources and tools**. Slide adds: **Docker Hub (paid service) scans the repositories you use**. _(Mod 11 p123)_

Bench-script layer of the same idea: [[11-LO07c-Container-Security-Best-Practices]] (p.118), [[11-LO08b-Docker-Security-Tools]].

## Cards

Docker ships five security features - name them and say what capabilities gives you.
?
Cgroups, LSMs (AppArmor/SELinux via runc), capabilities, seccomp, userns. Capabilities split root privileges on a thread basis; Docker allows only 14 of the 37 Linux capability groups by default, and more can be added or removed. _(Mod 11 p120)_

Seccomp and userns: what does each control?
?
Seccomp gives fine-grained per-syscall control - the default profile limits many syscalls and specific syscalls can be blocked from being used by container binaries. Userns remaps root to unprivileged IDs on the host, isolating the process and limiting access to system resources; Docker supports global uid/gid mapping. _(Mod 11 p120)_

Docker content trust: what does it verify, what is its default state, and how is it enabled?
?
It verifies the authenticity, integrity and publication date of images in the Docker Hub registry; it is disabled by default. Enable with sudo export DOCKER_CONTENT_TRUST=1, then only signed images are retrieved by docker pull. _(Mod 11 p121)_

Resource limits: why does an uncapped container endanger the host, and what two limit types does Docker impose?
?
A container can consume as much as the host scheduler provides; the kernel may throw an OOME and kill other processes, potentially collapsing the system. Docker imposes hard memory limits (only a set amount of system memory) or soft memory limits (unconstrained use under conditions such as overall low memory usage). _(Mod 11 p122)_

Which container resource is limited with which stated option?
?
CPU - add the --cpus=2 option to the run command to limit a container to 2 CPUs. The 1 GB memory limit is the other example, but its option string is not legible in the courseware figure. _(Mod 11 p122)_

Third-party tool selection: what is the risk and how is an official image recognized?
?
Containers pulled from public repositories may have been created insecurely and may contain malicious or corrupt files, so pull only from reliable sources such as the Docker Hub. In the search results the first entry is the official image - that flag distinguishes official from third-party sources and tools. _(Mod 11 p123)_
