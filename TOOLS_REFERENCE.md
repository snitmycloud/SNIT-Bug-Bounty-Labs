# SNIT Bug Bounty Tools Reference

## 1. Introduction

This document provides a reference guide to the tools used in SNIT Bug Bounty Hunting and Web Application Security Labs.

Students will use these tools for reconnaissance, asset discovery, technology fingerprinting, web application analysis, vulnerability assessment, and reporting.

**Important:** Use these tools only against authorized targets or intentionally vulnerable training environments.

## 2. Tools Overview

| Tool | Category | Purpose |
|---|---|---|
| Kali Linux | Operating System | Cybersecurity testing environment |
| Nmap | Network Scanning | Network and service discovery |
| Subfinder | Reconnaissance | Passive subdomain discovery |
| WhatWeb | Fingerprinting | Website technology identification |
| Wappalyzer | Fingerprinting | Browser-based technology detection |
| Gobuster | Content Discovery | Directory and file discovery |
| Feroxbuster | Content Discovery | Web content discovery |
| Burp Suite Community | Web Security | HTTP request and response analysis |
| OWASP ZAP | Web Security | Web application security testing |
| curl | HTTP Utility | Send HTTP requests and inspect responses |
| dig | DNS Utility | DNS record lookup |
| WHOIS | Reconnaissance | Domain registration information |
| OpenSSL | TLS Analysis | Certificate inspection |
| Browser Developer Tools | Web Analysis | Inspect page structure and network activity |
| SecLists | Wordlists | Wordlists for authorized security testing |

## 3. Kali Linux

**Purpose:** A Linux distribution containing many cybersecurity tools.

Official website:

https://www.kali.org/

Update package information:

```bash
sudo apt update
```

Upgrade installed packages:

```bash
sudo apt upgrade
```

Check the operating system:

```bash
cat /etc/os-release
```

## 4. Nmap

**Purpose:** Network discovery and service identification.

Check the version:

```bash
nmap --version
```

Perform a basic scan against an authorized lab host:

```bash
nmap <AUTHORIZED-LAB-IP>
```

Perform service version detection:

```bash
nmap -sV <AUTHORIZED-LAB-IP>
```

Official website:

https://nmap.org/

## 5. Subfinder

**Purpose:** Passive subdomain discovery.

Check the version:

```bash
subfinder -version
```

Discover subdomains for an authorized domain:

```bash
subfinder -d <AUTHORIZED-DOMAIN> -silent
```

Save results:

```bash
subfinder -d <AUTHORIZED-DOMAIN> -silent -o subdomains.txt
```

Official repository:

https://github.com/projectdiscovery/subfinder

## 6. WhatWeb

**Purpose:** Identify technologies used by websites.

Check the version:

```bash
whatweb --version
```

Identify technologies:

```bash
whatweb http://<AUTHORIZED-LAB-TARGET>
```

Verbose output:

```bash
whatweb -v http://<AUTHORIZED-LAB-TARGET>
```

Official repository:

https://github.com/urbanadventurer/WhatWeb

## 7. Wappalyzer

**Purpose:** Identify technologies used by web applications through a browser extension.

Typical workflow:

1. Install Wappalyzer from your browser's official extension store.
2. Open an authorized lab application.
3. Select the Wappalyzer extension.
4. Review detected technologies.
5. Record the results.

Official website:

https://www.wappalyzer.com/

## 8. Gobuster

**Purpose:** Directory and file discovery.

Check the version:

```bash
gobuster version
```

Perform basic discovery against an authorized lab:

```bash
gobuster dir -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

Save results:

```bash
gobuster dir -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt -o gobuster_results.txt
```

Official repository:

https://github.com/OJ/gobuster

## 9. Feroxbuster

**Purpose:** Web content discovery.

Check the version:

```bash
feroxbuster --version
```

Perform basic discovery:

```bash
feroxbuster -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

Official repository:

https://github.com/epi052/feroxbuster

Use a small wordlist and respect the training environment's request limits.

## 10. Burp Suite Community Edition

**Purpose:** Inspect and analyze HTTP requests and responses.

Official website:

https://portswigger.net/burp/communitydownload

Basic workflow:

1. Open Burp Suite.
2. Create a temporary project.
3. Start the built-in browser.
4. Visit your authorized lab application.
5. Open Proxy HTTP history.
6. Inspect requests and responses.
7. Record relevant security observations.

Important features:

- Proxy
- HTTP history
- Repeater
- Decoder
- Comparer
- Intruder with Community Edition limitations

## 11. OWASP ZAP

**Purpose:** Web application security testing and HTTP traffic inspection.

Official website:

https://www.zaproxy.org/

Basic workflow:

1. Open OWASP ZAP.
2. Start a session.
3. Open the authorized training application.
4. Review the Sites and History panels.
5. Inspect requests and responses.
6. Use scanning features only when authorized by the lab instructions.

## 12. curl

**Purpose:** Send HTTP requests and inspect responses from the command line.

Check the version:

```bash
curl --version
```

Retrieve response headers:

```bash
curl -I http://<AUTHORIZED-LAB-TARGET>
```

Retrieve a page:

```bash
curl http://<AUTHORIZED-LAB-TARGET>
```

Verbose request information:

```bash
curl -v http://<AUTHORIZED-LAB-TARGET>
```

Official website:

https://curl.se/

## 13. dig

**Purpose:** DNS record lookup.

Check the version:

```bash
dig -v
```

Look up an A record:

```bash
dig <AUTHORIZED-DOMAIN> A
```

Look up MX records:

```bash
dig <AUTHORIZED-DOMAIN> MX
```

Look up NS records:

```bash
dig <AUTHORIZED-DOMAIN> NS
```

Look up TXT records:

```bash
dig <AUTHORIZED-DOMAIN> TXT
```

## 14. WHOIS

**Purpose:** Retrieve publicly available domain registration information.

Check the version:

```bash
whois --version
```

Look up a domain:

```bash
whois <AUTHORIZED-DOMAIN>
```

Note that privacy protection and registry policies may hide registration details.

## 15. OpenSSL

**Purpose:** Inspect TLS certificate information.

Check the version:

```bash
openssl version
```

Inspect an authorized HTTPS host:

```bash
openssl s_client -connect <AUTHORIZED-HOST>:443 -servername <AUTHORIZED-HOST>
```

Inspect the certificate dates and subject:

```bash
openssl s_client -connect <AUTHORIZED-HOST>:443 -servername <AUTHORIZED-HOST> </dev/null 2>/dev/null | openssl x509 -noout -subject -issuer -dates
```

Official website:

https://www.openssl.org/

## 16. Browser Developer Tools

**Purpose:** Inspect web application behavior.

Open Developer Tools:

```text
F12
```

Important tabs:

| Tab | Purpose |
|---|---|
| Elements | Inspect HTML and DOM |
| Console | Review browser messages and errors |
| Network | Inspect HTTP requests and responses |
| Application / Storage | Inspect cookies and browser storage |
| Sources | Review loaded scripts and resources |
| Security | Review connection security information |

## 17. SecLists

**Purpose:** Provides wordlists used in authorized security assessments.

Install on Kali Linux:

```bash
sudo apt update
sudo apt install seclists -y
```

Common wordlist directory:

```bash
/usr/share/seclists/
```

Web content wordlists:

```bash
/usr/share/seclists/Discovery/Web-Content/
```

Official repository:

https://github.com/danielmiessler/SecLists

## 18. Recommended Tool Usage by Lab

| Lab | Recommended Tools |
|---|---|
| Lab 01: Bug Bounty Fundamentals | Browser |
| Lab 02: Scope and Methodology | Browser, WHOIS |
| Lab 03: Reconnaissance | dig, WHOIS, curl, WhatWeb |
| Lab 04: Subdomain Enumeration | Subfinder, dig |
| Lab 05: Technology Fingerprinting | WhatWeb, Wappalyzer, curl, OpenSSL |
| Lab 06: Directory Discovery | Gobuster, Feroxbuster, SecLists |
| Lab 07: OWASP Top 10 | Burp Suite, OWASP Juice Shop |
| Lab 08: Authentication Testing | Burp Suite, Browser Developer Tools |
| Lab 09: SQL Injection | Burp Suite, PortSwigger Academy |
| Lab 10: Cross-Site Scripting | Burp Suite, Browser Developer Tools |
| Lab 11: Access Control and IDOR | Burp Suite, OWASP Juice Shop |
| Lab 12: Vulnerability Reporting | Markdown Editor, CVSS Calculator |

## 19. Important Tool Usage Guidelines

- Verify the target is authorized before testing.
- Follow program-specific scope restrictions.
- Use controlled request rates.
- Avoid unnecessary automated scanning.
- Do not perform destructive testing.
- Protect credentials and session tokens.
- Do not assume tool output proves a vulnerability.
- Manually verify findings in the authorized environment.
- Keep evidence and reports secure.

## 20. Final Note

Tools support security testing, but they do not replace technical understanding.

Students should understand what each tool does, interpret its output correctly, validate findings safely, and document results professionally.

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
