---
title: "Information Gathering"
---

## Introduction

## Passive Information Gathering

### Website Recon & Footprinting
!!! note "What are we looking for:"
    - IP Addresses
    - Directories hidden from search engines
    - Names
    - Email addresses
    - Phone Numbers
    - Physical addresses
    - Web technologies being used
``` bash
# The whatis command is used to get brief information about Linux commands or functions.
whatis host
host hackersploit.org
```
:octicons-link-external-16: [About /robots.txt](https://www.robotstxt.org/robotstxt.html)  
https://hackersploit.org/robots.txt
:octicons-link-external-16: [sitemaps.org](https://www.sitemaps.org/)  
https://hackersploit.org/sitemap.xml
https://hackersploit.org/sitemaps.xml

### Whois Enumeration
!!! danger ""
!!! info ""
:octicons-link-external-16: [ Homepage]()  
:octicons-link-external-16: [ | Kali Linux Tools]()
<!--------->
### Website Footprinting With Netcraft
!!! danger ""
!!! info ""
:octicons-link-external-16: [ Homepage]()  
:octicons-link-external-16: [ | Kali Linux Tools]()
<!--------->
### DNS Recon ###
!!! danger "TO-DO"
    Create a list of DNS records types.
    Ex: AAAA, TXT, MS, MX...
#### dnsrecon (cli tool)
!!! info "DNSRecon"
    DNSRecon is a Python script that provides the ability to perform:

    - Check all NS Records for Zone Transfers.
    - Enumerate General DNS Records for a given Domain (MX, SOA, NS, A, AAAA, SPF and TXT).
    - Perform common SRV Record Enumeration.
    - Top Level Domain (TLD) Expansion.
    - Check for Wildcard Resolution.
    - Brute Force subdomain and host A and AAAA records given a domain and a wordlist.
    - Perform a PTR Record lookup for a given IP Range or CIDR.
    - Check a DNS Server Cached records for A, AAAA and CNAME.
    - Records provided a list of host records in a text file to check.
    - Enumerate Hosts and Subdomains using Google.
:octicons-link-external-16: [DNSRecon Homepage](https://github.com/darkoperator/dnsrecon)  
:octicons-link-external-16: [dnsrecon | Kali Linux Tools](https://www.kali.org/tools/dnsrecon/)
``` bash
dnsrecon -d hackersploit.org
```
#### dnsdumpster.com (web tool)
!!! info "DNSdumpster"
    DNSdumpster.com is a FREE domain research tool that can discover hosts related to a domain. Finding visible hosts from the attackers perspective is an important part of the security assessment process.
:octicons-link-external-16: [DNSdumpster Homepage](https://dnsdumpster.com/)

### WAF With wafw00f ###
!!! info "WAFW00F"
    This package identifies and fingerprints Web Application Firewall (WAF) products using the following logic:

    - Sends a normal HTTP request and analyses the response; this identifies a number of WAF solutions.
    - If that is not successful, it sends a number of (potentially malicious) HTTP requests and uses simple logic to deduce which WAF it is.
    - If that is also not successful, it analyses the responses previously returned and uses another simple algorithm to guess if a WAF or security solution is actively responding to the attacks.
:octicons-link-external-16: [WAFW00F Homepage](https://github.com/EnableSecurity/wafw00f)  
:octicons-link-external-16: [wafw00f | Kali Linux Tools](https://www.kali.org/tools/wafw00f/)
``` bash
wafw00f hackersploit.org
# Option: -a or --findall --> MEANS --> Testing For All Possible WAF Instances
wafw00f hackersploit.org -a
```

### Subdomain Enumeration With Sublist3r ###
!!! info "Sublist3r"
    This package contains a Python security tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting over the network. Sublist3r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu, and Ask. Sublist3r also enumerates subdomains using Netcraft, Virustotal, ThreatCrowd, DNSdumpster, and ReverseDNS.
:octicons-link-external-16: [Sublist3r Homepage](https://github.com/aboul3la/Sublist3r)  
:octicons-link-external-16: [sublist3r | Kali Linux Tools](https://www.kali.org/tools/sublist3r/)
``` bash
sudo apt install sublist3r
sublist3r -d hackersploit.org
sublist3r -d hackersploit.org -e google,yahoo
```

### Google Dorks ###
!!! danger "TO-DO"
    Google Dorks Ex:
:octicons-link-external-16: [Google Homepage](https://www.google.com/)  
:octicons-link-external-16: [Google Hacking Database](https://www.exploit-db.com/google-hacking-database)
```
site:ine.com
site:ine.com inurl:admin
site:*.ine.com
site:*.ine.com inurl:admin
site:*.ine.com intitle:admin
site:*.ine.com filetype:pdf
site:ine.com instructors
intitle:index of

cache:ine.com
waybackmachine -> https://archive.org/web/

inurl:auth_user_file.txt
inurl:passwd.txt
```

### Email Harvesting With theHarvester ###
!!! info "theHarvester"
    The package contains a tool for gathering subdomain names, e-mail addresses, virtual hosts, open ports/ banners, and employee names from different public sources (search engines, pgp key servers).
:octicons-link-external-16: [theHarvester Homepage](https://github.com/laramies/theHarvester)  
:octicons-link-external-16: [theHarvester | Kali Linux Tools](https://www.kali.org/tools/theharvester/)
``` bash
theHarvester -d hackersploit.org -b google,linkedin
```

### Leaked Password Databases
:octicons-link-external-16: [';--have i beenpwned?](https://haveibeenpwned.com)

## Active Information Gathering
!!! danger ""
!!! info ""
:octicons-link-external-16: [ Homepage]()  
:octicons-link-external-16: [ | Kali Linux Tools]()
<!--------->
### DNS Zone Transfers
### Host Discovery With Nmap
### Port Scanning With Nmap
### Windows Recon: Nmap Host Discovery

## Conclusion

## 2.1
#### 2.1.1
##### 2.1.1.1
###### 2.1.1.1.1
####### 2.1.1.1.1.1
######## 2.1.1.1.1.1.1


:simple-youtube:

## 1
## 2
## 3
## 4
## 5





---

### Inline blocks

Admonitions can also be rendered as inline blocks (e.g., for sidebars), placing
them to the right using the `inline` + `end` modifiers, or to the left using
only the `inline` modifier:

<!--=== ":octicons-arrow-right-16: inline end"-->

    !!! info inline end "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
        purus auctor massa, nec semper lorem quam in massa.

    ``` markdown
    !!! info inline end "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Nulla et euismod nulla.
        Curabitur feugiat, tortor non consequat
        finibus, justo purus auctor massa, nec
        semper lorem quam in massa.
    ```

    Use `inline end` to align to the right (left for rtl languages).

=== ":octicons-arrow-left-16: inline"

    !!! info inline "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
        purus auctor massa, nec semper lorem quam in massa.

    ``` markdown
    !!! info inline "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Nulla et euismod nulla.
        Curabitur feugiat, tortor non consequat
        finibus, justo purus auctor massa, nec
        semper lorem quam in massa.
    ```

    Use `inline` to align to the left (right for rtl languages).

__Important__: admonitions that use the `inline` modifiers _must_ be declared
prior to the content block you want to place them beside. If there's
insufficient space to render the admonition next to the block, the admonition
will stretch to the full width of the viewport, e.g., on mobile viewports.
