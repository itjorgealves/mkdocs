---
title: "Footprinting & Scanning"
---

### Mapping a Network
#### Tools
- wireshark
- arp-scan
``` bash title="arp-scan" linenums="1"
sudo arp-scan -I eth0 -g 192.168.1.0/24
```
- ping
- fping
``` bash title="fping" linenums="1"
# 2>/dev/null - sends erros to null file
fping -I eth0 -g 192.168.1.0/24 -a 2>/dev/null
```
- nmap
``` bash title="nmap" linenums="1"
nmap -sn 192.168.1.0/24
```
- zenmap

:octicons-link-external-16: [Wireshark](https://www.wireshark.org/)  
:octicons-link-external-16: [arp-scan](https://github.com/royhills/arp-scan)  
:octicons-link-external-16: []()



### Port Scanning
``` bash title="nmap" linenums="1"
# ips is a txt with ip from network to scan
nmap -iL ips -sV -O -sC
```

- zenmap - gui nmap
- nmap automator
- masscan
- rustscan
- autorecon


### NMAP Host Discovery
``` bash title="script" linenums="1"
ping 10.4.28.137
arp-scan -g 10.4.28.137
nmap -Pn 10.4.28.137
nmap -Pn 10.4.28.137 -p 80,135,139,445,3389,49154,49155 -sV -O
```