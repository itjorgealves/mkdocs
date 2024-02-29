---
title: "Notes"
---

## nmap
``` bash
nmap -T4 10.4.20.0/20 --open
# service enumeration -sV and operating system -O
nmap 10.4.17.133 -sV -O
nmap 10.4.17.133 -sV -sC
```

``` bash title="Windows Recon: SMB - Nmap Scripts" linenums="1"
nmap -p445 --script smb-protocols 10.0.17.200
```