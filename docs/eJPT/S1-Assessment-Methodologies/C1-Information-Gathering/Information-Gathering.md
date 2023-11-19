---
title: "Information Gathering"
---

## Introduction

## Passive Information Gathering
### Website Recon & Footprinting
### Whois Enumeration
### Website Footprinting With Netcraft
### DNS Recon
!!! note
    cretae list of types of DNS registries

#### dnsrecon (cli tool)

:octicons-link-external-16: [DNSRecon Homepage](https://github.com/darkoperator/dnsrecon)  
:octicons-link-external-16: [dnsrecon | Kali Linux Tools](https://www.kali.org/tools/dnsrecon/)
``` bash
dnsrecon -d hackersploit.org
```

#### dnsdumpster.com (web tool)

:octicons-link-external-16: [DNSdumpster Homepage](https://dnsdumpster.com/)

### WAF With wafw00f
### Subdomain Enumeration With Sublist3r
### Google Dorks
### Email Harvesting With theHarvester
### Leaked Password Databases

## Active Information Gathering
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
