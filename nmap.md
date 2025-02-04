# nmap

An exaustive list of nmap parameters and use cases

## Parameters

#### Port Specification Options

```
nmap *args* TARGET_IP
```

* args:
	* -p X: port scan - scans specific port "X"
	* -p X-Y: port scan - scans specific port range from "X" to "Y"
	* -p-: port scan - scans entire port range
	* -F: port scan - fast port scan

#### Scanning Types

```
nmap *args* TARGET_IP
```

* args:
	* -sS: port scan - TCP SYN (stealth scan)
	* -sT: port scan - TCP connect (complete 3-way handshake)
	* -sU: port scan - UDP

#### Host Discovery

```
nmap *args* TARGET_IP
```

* args:
	* -sL: lists host without scanning
	* -sn: disables port scan
	* -Pn: disables host discovery
	* -n: disables DNS resolution
	* -PS: host discovery - TCP SYN
	* -PA: host discovery - TCP ACK
	* -PU: host discovery - UDP
	* -PR: host discovery - ARP
	* -PE: host discovery - ICMP ping

#### Version Detection

```
nmap *args* TARGET_IP
```

* args:
	* -sV: version detection scan
	* -O: OS detection scan
	* -sC: runs automatic nmap script
	* -A: aggressive scan, replace -O -sV -sC

#### Timing Options

```
nmap *args* TARGET_IP
```

* args:
	* -Tx: set nmap scan speed, "x" goes from 0 to 5

#### Firewall Spoofing

```
nmap *args* TARGET_IP
```

* args:
	* -f: fragments packets
	* -mtu X: sets MTU to "X"
	* -ttl X: sets TTL to "X"
	* -data-length X: sets packet-length to "X"
	* -source-port X: sets source port to "X"
	* -D X: allows decoy from address "X"
	* -g X: sends packets trough port "X"
	* --scan-delay X: sets the delay between probes to "X"
	* --host-timeout X: set a timeout to "X" for each target
	* --send-ip: sends raw packets to skip ARP requests on a local network
	* --min-parallelism X: sets minimum number of parallel probes to "X"
	* --max-parallelism X: sets maximum number of parallel probes to "X"
	* --min-rate X: sets minimum rate of packets to "X"
	* --max-rate X: sets maximum rate of packets to "X"

#### TARGET_IP Specifications

```
nmap *args* TARGET_IP
```

* TARGET_IP:
	* IP: single IP
	* IP_1 IP_2: multiple IPs
	* IPx-y: range of IPs
	* X: domain "X"
	* IP.0/X: use of mask
* args:
	* -iL X: scan from file "X"
	* --exclude X: exclude IP "X" from the scan

#### Readability

```
nmap *args* TARGET_IP
```

* args:
	* --reason: displays why a port is open
	* -v: more complete verbose
	* -vv, -vvv, -vvvv, -v2, -v3, -v4: increases verbose level
	* -d: increases debug
	* -d2 --> -d9: increases debug level
	* -h: help menu

#### Output Formats

```
nmap *args* TARGET_IP *outputs*
```

* outputs:
	* -oN X.txt: outputs results in a .txt file called "X"
	* -oX X.xml: outputs results in a .xml file called "X"
	* -oS X: outputs results in a file with script kiddie format called "X"
	* -oG X: outputs result in a file with grep format called "X"
	* -oA: outputs results in the 3 main formats

#### Scripts (NSE)

```
ls -al /usr/share/nmap/scripts
```

* Displays all NSE scripts

```
ls -al /usr/share/nmap/scripts | grep -e "X"
```

* Displays scripts related to string "X"

```
nmap *args* TARGET_IP *scripts*
```

* scripts:
	* --script-update-db: updates scripts
	* --script-help=X: displays help about script "X"
	* --script=X: uses NSE script "X"
	* --script-args "X": uses NSE script with arguments "X"

## Use Cases

#### Basics

```
nmap -sn TARGET_SUB/MASK -T4 -oX nmap_discovery.xml
```

```
nmap -Pn -A -p- TARGET_IP -T4 -oX nmap_pscan.xml
```

#### WebDav

```
nmap -sV -sC TARGET_IP
```

```
nmap -sV -p 80 TARGET_IP --script=http-enum
```

#### EternalBlue

```
nmap -sV -p 445 -O TARGET_IP
```

```
nmap -sV -p 445 TARGET_IP --script=smb-vuln-ms17-010
```

#### ShellShock

```
nmap -sV TARGET_IP
```

```
nmap -sV TARGET_IP --script=http-shellshock --script-args "http-shellshock.uri=/gettime.cgi"
```

#### eJPT Examples

```
nmap -sn -v -T4 TARGET_IP
```

```
nmap -sn -PS21,22,25,80,445,3389,8080 -T4 TARGET_IP
```

```
nmap -sn -PS21,22,25,80,445,3389,8080 -PU137,138 -T4 TARGET_IP
```

```
nmap -Pn -sS -sV -p445,3389 -f --data-length 200 -D SPOOF_1,SPOOF_2 TARGET_IP
```

```
nmap -Pn -sS -sV -p445,3389 -f --data-length 200 -g 23 -D SPOOF_1,SPOOF_2 TARGET_IP
```

```
nmap -Pn -sS -F --host-timeout 5s TARGET_SUB/24
```

```
nmap -sS -sV -F --host-timeout 5s TARGET_SUB/24
```

```
nmap -sS -sV -F --scan-delay 5s TARGET_SUB/24
```

```
nmap -sS -sV -F -T1 TARGET_SUB/24
```

```
nmap -Pn -sS -F -T4 TARGET_IP -oN nmap_normal.txt
```

```
nmap -Pn -sS -F -T4 TARGET_IP -oN nmap_xml.xml
```

```
nmap -Pn -sS -F -T4 TARGET_IP -oG nmap_grep.txt
```

```
egrep -v "^#|Status: Up" nmap_grep.txt | cut -d' ' -f2,4- | sed -n -e 's/Ignored.*//p' | awk '{print "Host: " $1 " Ports: " NF-1; $1=""; for(i=2; i<=NF; i++) { a=a" "$i; }; split(a,s,","); for (e in s) { split(s[e],v,"/"); printf "%-8s %s/%-7s %s\n" , v[2], v[3], v[1], v[5]}; a="" }'
```