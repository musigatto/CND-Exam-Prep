---
type: note
module: "14"
lo: "02"
tags: [tool, process, bestpractice, mod/14]
topic: "Connecting the capture device to a managed switch"
exam_weight: unknown
status: done
unresolved:
  - "p14 the 3Com feature is printed as 'Roving Analysis Port (RAP)'. Reproduced verbatim; not corrected to any other expansion, since the source is the only authority for the name."
  - "p14 the body says a switch 'should be connected and configured as a managed switch, which can only view the network traffic', while the callout says the managed switch 'allows a specific port to run in the monitor mode'. Whether 'can only view' is a restriction on the managed switch or a description of the monitor port is not disambiguated; both printed."
  - "p14 the callout says 'All the packets passing through the switch are replicated to the port in the monitor mode'. No bound on which source ports are mirrored (ingress only, egress only, or both) is given in prose; the figure labels Ingress Traffic and Egress Traffic source but the figure is non-evidence for configuration."
  - "p14 no configuration steps, CLI commands or switch management menu paths are printed anywhere on the page."
---

[[MOC-Module-14]]

# Connecting the Capture Device to a Managed Switch (§14.02c)

> **LO#02: Setting up the Environment for Network Monitoring** _(Mod 14 p9)_
> Covers p14 — the port-mirroring mechanism that feeds the sniffer.

## The mechanism _(Mod 14 p14 callout)_

1. **Connect the capture device to a port running in the monitor mode** (managed switch).
2. *"The managed switch allows a **specific port to run in the monitor mode**."*
3. *"**All the packets passing through the switch are replicated to the port in the monitor mode** —
   **This feature is called port monitoring or port mirroring.**"
4. *"Use the **switch management interface** to **both select the port and assign a specific port to
   monitor**."*

```
traffic on the switch
   |
   +--> [replicated / copied] ---> the MONITOR-MODE port
                                    |
                              capture device + sniffer
```

## Vendor names for the same feature _(Mod 14 p14)_

*"Different vendors have this feature but use **different names** for it."* _(Mod 14 p14)_

| Feature name | Vendor |
|---|---|
| **Switched Port Analyzer (SPAN)** | **Cisco** |
| **Roving Analysis Port (RAP)** | **3Com** |

- Body confirmation: *"the port mirroring feature on **Cisco** switches is known as the **Switched Port
  Analyzer (SPAN)** port."* _(Mod 14 p14)_
- **SPAN** is the only one the page ties to a vendor twice; **RAP** is named once.

## What a managed switch adds _(Mod 14 p14)_

- A switch *"should be connected and **configured as a managed switch**, which can only view the
  network traffic."* _(Mod 14 p14)_
- Configured as a managed switch *"by **enabling the port monitoring or port mirroring** feature on a
  specific port in the switch."* _(Mod 14 p14)_
- **Port mirroring process** = *"**copying the switch network traffic** and **sending it to another
  port** in the switch **so that the monitoring tool can analyze it**."* _(Mod 14 p14)_
- A managed switch can **configure, manage, and monitor a LAN**; it allows **greater control over the
  flow of data**. _(Mod 14 p14)_
- *"**Accessibility to manage the data flow significantly decreases the chances of an intrusion.**"_
  _(Mod 14 p14)_
- Trade-off as printed: *"Though a managed switch **may cost more** than an unmanaged switch, it
  **assures better security and filtered data transmissions**."* _(Mod 14 p14)_

## Exam angle

- The chain that must be reproduced in order: **monitor mode port → replication of switch traffic →
  another port → monitoring tool analyzes**. _(Mod 14 p14)_
- Two-word aliases, identical function: **port monitoring = port mirroring**. _(Mod 14 p14)_
- Vendor → name is the discriminable pair: **Cisco → SPAN**, **3Com → RAP**. _(Mod 14 p14)_

## Related

- What the capture machine then does with the mirrored traffic: [[14-LO02b-How-Network-Sniffers-Work-and-Placement]]
- The sniffers it runs: [[14-LO02a-Network-Sniffers-for-Network-Monitoring]]
- Perimeter-side context: [[MOC-Module-04]] · general network-security context: [[MOC-Module-03]]






