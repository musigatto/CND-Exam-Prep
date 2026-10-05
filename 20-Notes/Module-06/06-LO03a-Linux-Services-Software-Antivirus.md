---

type: note
module: "06"
lo: "03"
tags: [process, tool, command, threat, bestpractice, mod/06]
topic: "Linux OS Hardening — Services, Software, Antivirus, Repositories"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Disable Services and Remove Unnecessary Software (§6.3)

Open ports of running services can be exploited by intruders. Disable all unnecessary services and software.

## Disable Unnecessary Services (`systemctl`)
- List all services + status (Ubuntu): `systemctl --type service`
- Stop a service: `sudo systemctl stop [service]`
- Disable a service: `sudo systemctl disable [service]`
- Kill a process: `sudo kill -9 [process id]`
- Example: `sudo systemctl stop openvpn`
- Disable services such as **FTP, Telnet, Rlogin/Rsh** if not in use

### Unnecessary server services to remove (Red Hat)
| Service | Risk |
|---|---|
| **Telnet-server** (`telnetd`) | Unencrypted telnet → credential sniffing |
| **RSH-server** (`rsh, rlogin, rcp`) | Clear-text credentials, legacy exposures |
| **NIS-server** (`ypserv`, ex-Yellow Pages) | Insecure; susceptible to DoS, buffer overflows, poor auth for NIS maps |
| **TFTP-server** (`tftp-server`) | No authentication/encryption (no confidentiality/integrity) |
| **TALK-server** (`talk-server`) | Unencrypted messaging protocol |

- Check package: `rpm -q telnet-server` / `rpm -q rsh-server` / `rpm -q ypserv` / `rpm -q tftp-server` / `rpm -q talk-server`
- Remove: `yum erase telnet-server` (etc.)

## Remove or Uninstall Unnecessary Software/Packages
- Review installed packages with package manager (`apt-get`, `dpkg`, `yum`) and delete unwanted ones
- Commands (Ubuntu):
  - `sudo apt autoclean` — clean partial packages
  - `sudo apt-get clean` — clean the apt cache
  - `sudo apt-get autoremove` — remove automatically unused packages (libs installed automatically)
  - `sudo apt remove [packageName]` — uninstall a package
  - `sudo apt-get purge [packageName]` — remove package + config files
  - `dpkg --list` — display all installed packages
- Tools: **UnusedPkg diagnostics** and **Deborphan** list unused packages/libraries
  - Install: `sudo apt-get install deborphan`
  - Run: `deborphan --guess-all`
  - Remove: `sudo deborphan --guess-data | xargs sudo aptitude -y purge`

## Disable Unsafe Repositories
- Ubuntu repositories: **Main, Universe, Restricted, Multiverse** (comprise packages audited by Canonical/developers/security teams)
  - **Main** — Canonical-supported free and open-source software
  - **Universe** — community-maintained free/open-source
  - **Restricted** — proprietary drivers (free downloads but no full support)
  - **Multiverse** — software restricted by copyright or legal issues (paid)
- Ubuntu team does **not audit all** repositories → may provide harmful apps
- Restrict downloading/updating from unsafe/restricted repositories:
  1. Show Applications → **Software & Updates**
  2. Under **Ubuntu Software** tab: keep only Canonical-supported main/universe (uncheck third-party)
  3. Click **Other Software** tab → uncheck **"Canonical Partners"** option
  4. Close → update when prompted; Ubuntu then auto-downloads updates daily

## Install Antivirus (ClamAV)
- ClamAV = open-source (GPLv2) antivirus engine: detects **Trojans, viruses, malware** and other threats
- Install:
  - Debian: `apt-get update` then `apt-get install clamav`
  - RHEL/CentOS: `yum install -y epel-release` then `yum install -y clamav`
  - Fedora: `yum install -y clamav clamav-update`
- Only install needed packages (bare minimum)






