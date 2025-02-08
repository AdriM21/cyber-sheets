# Network Tools

A toolset oriented on networks

## Network Sniffing

#### Wireshark

```
sudo wireshark -i *_interface*
```

* To snif packets on network interface \_interface

#### tshark

```
tshark -r *file.pcap* -n
```

* To snif and register traffic inside file.pcap

```
tshark -r *file.pcapng* -Nn
```

* To snif and register traffic inside file.pcapng

#### tcpdump

```
tcpdump -r *file.pcapng* -n -v
```

* To snif and register traffic inside file.pcapng

```
tcpdump -i eth0 -c 50 -v
```

* To capture and display 50 packets by listening on the eth0 interface, which is a wired Ethernet, and displays them verbosely

```
tcpdump -i wlo1 -w data.pcap
```

* To capture packets by listening on the wlo1 interface (the WiFi interface) and writes the packets to data.pcap. It will continue till the user interrupts the capture by pressing CTRL-C)

```
tcpdump -i any -nn
```

* To capture packets on all interfaces and displays them on screen without domain name or protocol resolution

```
sudo tcpdump host example.com -w http.pcap
```

* To filter by host

```
sudo tcpdump -i ens5 port 53 -n
```

* To filter by port

```
sudo tcpdump -i ens5 icmp -n
```

* To filter by protocol

```
tcpdump "tcp[tcpflags] == tcp-syn"
```

* To capture TCP packets with only the SYN (Synchronize) flag set, while all the other flags are unset

```
tcpdump "tcp[tcpflags] & tcp-syn != 0"
```

* To capture TCP packets with at least the SYN (Synchronize) flag set

```
tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"
```

* To capture TCP packets with at least the SYN (Synchronize) or ACK (Acknowledge) flags set

```
tcpdump -r TwoPackets.pcap
```

* To display packets

```
tcpdump -r TwoPackets.pcap -q
```

* To display packets with a brief packet info

```
tcpdump -r TwoPackets.pcap -e
```

* To display link-level header

```
tcpdump -r TwoPackets.pcap -A
```

* To display packets as ASCII

```
tcpdump -r TwoPackets.pcap -xx
```

* To display packets in hexadecimal

```
tcpdump -r TwoPackets.pcap -X
```

* To display packets with best of both worlds

## Advanced Network Tools

#### fping (ping improvement)

```
fping *args*
```

* args:
	* -a: to show alive targets
	* -g: to generate a target list
	* -S: to spoof the source address

#### Burp Suite

```
burpsuite
```

* A proxy to perform web pentest
	* Use foxyproxy extension in browser to redirect traffic!