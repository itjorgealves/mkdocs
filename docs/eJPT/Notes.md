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
nmap -p445 --script smb-security-mode 10.0.17.200
nmap -p445 --script smb-enum-sessions 10.0.17.200
nmap -p445 --script smb-enum-sessions --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-shares 10.0.17.200
nmap -p445 --script smb-enum-shares --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-users --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-server-stats --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-domains --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-groups --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-services --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200
nmap -p445 --script smb-enum-shares,smb-ls --script-args smbusername=administrator,smbpassword=smbserver_771 10.0.17.200

```