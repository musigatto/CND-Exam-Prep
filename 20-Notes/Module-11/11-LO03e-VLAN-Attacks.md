---
type: note
module: "11"
lo: "03"
tags: [threat, mod/11]
topic: "VLAN Attacks"
exam_weight: unknown
status: done
unresolved:
  - "The Switch Spoofing description straddles the p35/p36 page break: p35 ends 'The attacker exploits an' and p36 resumes 'incorrectly configured trunk port to spoof itself to be a switch, and then emulates 802.1Q and DTP messages.' Read as one sentence; a missing phrase between the pages cannot be ruled out."
  - "p34 VLAN Hopping slide ends mid-sentence: 'This is mainly conducted in the Dynamic Trunking Protocol'. The clause is incomplete in the source and is not restated on p35-p36, so no completion is asserted."
  - "No consequence is stated in the courseware for Switch Spoofing, nor for VLAN hopping at the parent level - those cells read 'not stated in courseware' rather than being filled in."
  - "p34 figures ('Poisoned ARP Table' and the 'BPDU Guard' STP diagram) are image-only; only stray labels OCR'd. IP/MAC strings read as 216.3.128.12/.13/.15 and ABCD.EFoom01 / ABCD.EFOO.0002. System B's MAC is read as ABCD.EF00.0002 (only the O/0 glyph is ambiguous). System A's OCR string 'EFoom01' is 6 characters where a MAC suffix has 8, so ABCD.EF00.0001 is a plausible but UNCONFIRMED reading - treat System A's MAC as unverified."
---

[[MOC-Module-11]]
# VLAN Attacks (§11.03)

## Why the switch is the soft target _(Mod 11 p35)_

- "VLAN switches are **not equipped with a mechanism to detect an attack**."
- Consequence: "most **layer 2** attacks target the **incapability of the switch to track the attacker**."

## Attack table _(Mod 11 p34–p36)_

| Attack | Mechanism | Stated effect |
|---|---|---|
| **MAC flooding** | Attacker sends a **large number of fake MAC addresses** to **overflow the CAM table** (content addressable memory) | Table full → **traffic without MAC entries floods out to all ports of the VLAN** → attacker can **more easily view and retrieve** the generated traffic |
| **ARP attack** | Sends **fake ARP messages over the LAN** to associate the attacker's **MAC** with the IP of a **legitimate computer or server** → **poisons the ARP table** | **Tricks the switch** into forwarding packets with **forged identities** to a device in a **different VLAN**; in the **same VLAN** it **tricks end nodes** such as routers and workstations |
| **DHCP starvation** | **Multiple DHCP requests with spoofed MAC addresses** | **Denial of service at the DHCP server** |
| **Multicast brute-force** | **Injects several multicast frames into a VLAN in quick succession** | **Leaking of frames from the original VLAN to other VLANs** |
| **VLAN hopping** | Attacker **transmits traffic to other VLANs or ports that are not normally accessible from a given end system**. Two types: **Double Tags**, **Switch Spoofing**. p34 slide adds a truncated clause: "This is mainly conducted in the Dynamic Trunking Protocol" | not stated in courseware (see subtypes) |
| **Double Tags** _(VLAN hopping)_ | Two **`802.1Q`** tags: **inner = the VLAN the user wants to reach**, **outer = the native VLAN** tag. The switch **removes the native VLAN** tag and **forwards the second frame to the trunk interface(s)** | Attacker **jumps from the native VLAN to the user VLAN**; the strategy can be used to conduct a **DoS attack** |
| **Switch spoofing** _(VLAN hopping)_ | Exploits the default **"dynamic auto"** or **"dynamic desirable"** switch port mode, plus an **incorrectly configured trunk port** to **spoof itself to be a switch**, then **emulates `802.1Q` and DTP messages** | not stated in courseware |
| **Spanning-tree (STP)** — slide title "STP Attack" _(p34) / "Spanning-Tree Attack" _(p36)_ | **(1)** After obtaining the **port ID information**, send **STP configuration / topology change acknowledgement BPDUs** indicating the attacker **is the new root bridge with lower priority**. **(2)** **Install and transmit junk data through a new STP device** in the network | **(1)** **Finally gains access to the network traffic**. **(2)** **Flooding of data packets** → **shutdown of services for a short period of time** |

## The two VLAN-hopping paths _(Mod 11 p35–p36)_

```
DOUBLE TAGS
attacker -> [outer tag = native VLAN | inner tag = target VLAN]
        -> switch strips the native VLAN tag
        -> forwards the 2nd frame to the trunk interface(s)
        -> attacker hops native VLAN -> user VLAN  -> usable for DoS

SWITCH SPOOFING
attacker -> exploits port mode "dynamic auto" / "dynamic desirable"
        -> incorrectly configured trunk port -> spoofs itself as a switch
        -> emulates 802.1Q + DTP messages      (effect not stated)
```

## Figures on p34 _(Mod 11 p34)_

- **Poisoned ARP Table** - `System X 216.3.128.12` / `System Y 216.3.128.13` / `Attacker 216.3.128.15`; `System A MAC` OCR-read `ABCD.EFoom01` (see `unresolved`), `System B MAC ABCD.EF00.0002`; rows read "Modified ARP packets to IP Address: `216.3.128.15`".
- **BPDU Guard** diagram - `Switch 1`, `Switch 2`, `switch 3`, `Switch 4`, `Attacker`, `System A` (OCR-read `ABCD.EFoom01`), `System B` (`ABCD.EF00.0002`). Image-only, accompanying the STP attack.

Countermeasures for each of these: [[11-LO03h-VLAN-Security]].







