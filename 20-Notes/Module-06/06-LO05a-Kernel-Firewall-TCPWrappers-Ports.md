---

type: note
module: "06"
lo: "05"
tags: [concept, tool, command, threat, crypto, mod/06]
topic: "Linux Kernel, Firewall, Wrappers, Port Monitoring, IPv6"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-06]]

# Linux Network Security — Kernel, Firewall, TCP Wrappers, Ports (§6.5)

## Configure sysctl to Secure Linux Kernel
- `sysctl`: system control interface; edits Linux kernel parameters at runtime; `/etc/sysctl.conf` = text file of sysctl values read/set at boot
- Edit: `sudo gedit /etc/sysctl.conf` / `sudo nano /etc/sysctl.conf`
- Protects against network-level attacks (**MITM, spoofing**); restrict IPv4/IPv6 network-transmitted config, execshield, SYN flood (syncookies), source IP verification, suspicious-packet logging

### Key IPv4 settings
| Setting | Effect |
|---|---|
| `net.ipv4.icmp_echo_ignore_broadcasts = 1` | Avoid smurf attack |
| `net.ipv4.icmp_ignore_bogus_error_responses = 1` | Bad ICMP error protection |
| `net.ipv4.tcp_syncookies = 1` | SYN flood attack protection |
| `net.ipv4.conf.all/default.log_martians = 1` | Log spoofed/source-routed/redirect packets |
| `net.ipv4.conf.all/default.accept_source_route = 0` | No source-routed packets |
| `net.ipv4.conf.all/default.rp_filter = 1` | Reverse path filtering |
| `net.ipv4.conf.all/default.accept_redirects = 0`, `secure_redirects = 0` | No one alters routing tables |
| `net.ipv4.ip_forward = 0` | Don't act as a router |
| `net.ipv4.conf.all/default.send_redirects = 0` | No send packet redirects |
| `kernel.exec-shield = 1` | Reduce worm/automated remote attacks |
| `kernel.randomize_va_space = 1` | ASLR |
| `fs.file-max = 65535` | File descriptor limit |
| `kernel.pid_max = 65536` | More PIDs (fork() failure prevention) |
| `net.ipv4.ip_local_port_range = 2000 65000` | System IP port limits |
| `net.core.rmem_max/wmem_max = 8388608` | TCP buffer sizes |
| `net.ipv4.tcp_rmem/wmem = 10240 87380 12582912` | TCP buffer min/initial/max |
| `net.core.netdev_max_backlog = 5000` | Input queue backlog |
| `net.ipv4.tcp_window_scaling = 1` | Window scaling |

### IPv6 tuning
- `net.ipv6.conf.default.router_solicitations = 0` · `accept_ra_rtr_pref = 0` · `accept_ra_pinfo = 0` · `accept_ra_defrtr = 0` · `autoconf = 0` · `dad_transmits = 0` · `max_addresses = 1`

## Host-based Firewall with iptables
- Host-based firewalls: protect against firewall failure (adds a layer if primary fails); simple to configure (host needs few protocols → simpler ruleset verification); secure against internal threats; reduce misconfigured-software risk
- **iptables**: preinstalled; kernel-based packet filter; table → chains → rules
- Install/update: `sudo apt-get install iptables`; check rules: `sudo iptables -L -n -v`; specific table: `# iptables -t nat -L -v -n`
- Chains: **INPUT** (verifies incoming connections/IP+port vs rule) · **FORWARD** (forwards incoming to destination) · **OUTPUT** (output connections, allow/deny)
- Caution: small error can lock the system → manual fix required

### Example rules
| Purpose | Command |
|---|---|
| Block specific IP | `iptables -A INPUT -s 10.10.10.55 -j DROP` |
| Block specific port (output) | `iptables -A OUTPUT -p tcp --dport xxx -j DROP` |
| Block Facebook | `iptables -A OUTPUT -d 66.220.144.0/20 -j DROP` |
| Block non-TCP NEW | `iptables -A INPUT -p tcp ! --syn -m state --state NEW -j DROP` |
| Block XMAS scan | `iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP` |
| Drop NULL packets | `iptables -A INPUT -j DROP` |
| Drop fragmented packets | `iptables -A INPUT -f -j DROP` |
| Limit incoming ping flood (Apache port) | `iptables -A INPUT -p tcp --syn -m limit --limit 100/minute --limit-burst 200 -j ACCEPT` |
| Block MAC | `iptables -A INPUT -m mac --mac-source 00:00:00:00:00:00 -j DROP` |
| Block by interface+IP | `iptables -A INPUT -i eth0 -s xxx.xxx.xxx.xxx -j DROP` |
| Disable outgoing mail | `iptables -A OUTPUT -p tcp --dports 25,465,587 -j REJECT` |

## UFW (Uncomplicated Firewall)
- Simpler iptables interface; status default = disabled
- `sudo apt-get install ufw` · check: `sudo ufw status verbose` · enable: `sudo ufw enable`
- Default policies: `sudo ufw default deny incoming` · `sudo ufw default allow outgoing`
- Rules: `sudo ufw allow ssh` / `sudo ufw allow 2000` / `sudo ufw deny 22` / `sudo ufw allow 80/tcp` / `sudo ufw allow http/tcp` / `sudo ufw allow 1725/udp`
- IP rules: allow `sudo ufw allow from 10.10.10.25` · deny `sudo ufw deny from 10.10.10.24`
- Subnet: `sudo ufw allow from 198.51.100.0/24`; IP+port combo: `sudo ufw allow from 198.51.100.0 to any port 22 proto tcp`
- Advanced: `after.rules` / `after6.rules` for post-command rules; `/etc/default/ufw` toggles IPv6, defaults, chain management
- Delete: `sudo ufw delete allow 80`

## TCP Wrappers (TCPD)
- Host-based ACL system providing firewall services via network-traffic monitoring; allows based on `/etc/hosts.allow`, denies via `/etc/hosts.deny`
- Check service support: `ldd $(which sshd) | grep libwrap` (output → service can be TCP-wrapped; e.g., sshd, vsftpd)
- Supports: POP3, FTP, SSHD, telnet, R services
- Advantages: whitelists/blacklists IPs; syslog reporting; pattern-matched access control (run shell commands/scripts); works **at application layer (L7)** → filters apply even with encryption (e.g., HTTPS); protects against spoofing
- Do/do-nots: use both firewall + TCPD; do **not** configure TCPD on the firewall host; keep on workstations; no NIS (YP) netgroups; keep TCPD behind a firewall
- Default: both files empty → everything allowed; `# ls -l /etc/hosts.allow /etc/hosts.deny`; first matching rule wins

### /etc/hosts.allow & hosts.deny examples
- Allow SSH+FTP only to `192.168.0.201` + localhost → hosts.deny: `sshd, vsftpd : ALL` then `ALL : ALL`; hosts.allow: `sshd, vsftpd : 192.168.0.201, LOCAL`
- Changes take effect immediately (no restart)
- Allow all services to a domain: hosts.allow → `ALL : .example.com`
- Deny vsftpd to subnet: hosts.deny → `vsftpd : 10.0.1.`

## Monitor Open Ports and Services
- Understand vulnerabilities/hidden security risks per open port
- **netstat** (Ubuntu: `sudo apt install net-tools`): `netstat -tulpn` — `-t` TCP, `-u` UDP, `-n` numeric addresses, `-l` listening ports, `-p` PID+process name
- **ss**: `ss -tulpn` (same options as netstat; newer)
- **lsof**: `sudo lsof -nP -iTCP -sTCP:LISTEN`
- **nmap**: `nmap -sT -o localhost` (TCP scan) · `nmap -sU localhost` (UDP scan)

## Turn Off IPv6 if Not In Use
- Misconfigured IPv6 exposes the system even though IPv6 improves on IPv4; disable when unused
- Debian: add to `/etc/sysctl.conf` → `net.ipv6.conf.all.disable_ipv6 = 1`, `net.ipv6.conf.default.disable_ipv6 = 1`, `net.ipv6.conf.lo.disable_ipv6 = 1`; save + restart
- GRUB: edit `/etc/default/grub` → `GRUB_CMDLINE_LINUX_DEFAULT="quiet splash ipv6.disable=1"`, `GRUB_CMDLINE_LINUX="ipv6.disable=1"` → `sudo update-grub` → reboot
- Red Hat: `sysctl -w net.ipv6.conf.all.disable_ipv6=1`, `sysctl -w net.ipv6.conf.default.disable_ipv6=1`
- Fix if X11 Forwarding over SSH breaks: `/etc/ssh/sshd_config` → `#AddressFamily any` → `AddressFamily inet`, restart sshd
- Fix postfix issues: `/etc/postfix/main.cf` → `#inet_interfaces = localhost`, `inet_interfaces = 127.0.0.1`
- Check flag value: `cat /proc/sys/net/ipv6/conf/all/disable_ipv6`







