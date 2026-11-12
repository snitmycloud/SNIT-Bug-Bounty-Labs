# Lab 04: Subdomain Enumeration & Asset Discovery

## 1. Objective

Understand subdomain enumeration techniques and learn how to identify, verify, and document subdomains belonging to an authorized bug bounty assessment scope.

## 2. Topics Covered

- What is a subdomain?
- Domain and subdomain structure
- Passive subdomain enumeration
- Active subdomain enumeration
- DNS record analysis
- Certificate Transparency
- Subdomain discovery tools
- DNS resolution and verification
- Identifying inactive subdomains
- Asset inventory preparation

## 3. Tools Required

- Kali Linux
- Subfinder
- Amass
- Assetfinder
- DNS utilities
- crt.sh
- Browser
- curl

## 4. Understanding Subdomains

A subdomain is an additional part of a domain name used to organize websites, services, and applications.

Example:

```text
example.com
www.example.com
mail.example.com
api.example.com
dev.example.com
blog.example.com
```

Common subdomain purposes:

| Subdomain | Typical Purpose |
|---|---|
| www | Main website |
| mail | Email services |
| api | Application programming interface |
| dev | Development environment |
| staging | Pre-production environment |
| portal | User portal |
| blog | Blog platform |

These names are examples only. Actual functionality must be verified.

## 5. Passive Subdomain Enumeration

Passive enumeration collects information from external sources without directly probing the target infrastructure.

Common sources:

- Certificate Transparency logs
- Public DNS information
- Search engines
- Public datasets
- Security research platforms

### Certificate Transparency

Certificate Transparency logs provide publicly accessible records of issued TLS certificates.

Visit:

https://crt.sh/

Search for a domain within an authorized assessment scope.

Example search:

```text
%.example.com
```

Record relevant certificate names for further verification.

A certificate entry does not prove that a subdomain is currently active or authorized for testing.

## 6. Active Subdomain Enumeration

Active enumeration involves sending queries or requests to infrastructure associated with the authorized domain.

Common methods include:

- DNS queries
- DNS brute-force enumeration
- DNS resolution
- Subdomain verification

Only perform active enumeration when explicitly permitted by the program policy.

## 7. Practical Exercises

Use a local lab domain or an explicitly authorized training domain.

### Exercise 1: Install Subfinder

On Kali Linux:

```bash
sudo apt update
sudo apt install subfinder -y
```

Verify installation:

```bash
subfinder -version
```

If your Kali package repository does not provide it, use the official ProjectDiscovery installation instructions.

### Exercise 2: Passive Subdomain Discovery

```bash
subfinder -d <AUTHORIZED-DOMAIN> -silent
```

Observe the discovered subdomains.

### Exercise 3: Save Subdomain Results

```bash
subfinder -d <AUTHORIZED-DOMAIN> -silent -o subdomains.txt
```

Display the results:

```bash
cat subdomains.txt
```

### Exercise 4: Verify DNS Resolution

Use the following command to inspect a discovered hostname:

```bash
dig <DISCOVERED-SUBDOMAIN> A
```

Check IPv6 records:

```bash
dig <DISCOVERED-SUBDOMAIN> AAAA
```

Check CNAME records:

```bash
dig <DISCOVERED-SUBDOMAIN> CNAME
```

### Exercise 5: Verify HTTP Availability

For a hostname that is within the approved scope:

```bash
curl -I https://<DISCOVERED-SUBDOMAIN>
```

Record the HTTP status code and response headers.

A DNS record or HTTP response does not independently establish that the asset is in scope.

## 8. Subdomain Verification

Classify each discovered hostname:

| Hostname | DNS Resolved | HTTP Response | Scope Status |
|---|---|---|---|
| www.example.com | | | |
| api.example.com | | | |
| dev.example.com | | | |
| staging.example.com | | | |

Use fictional entries for classroom exercises. Confirm actual scope using the program policy.

## 9. Asset Inventory Template

| Field | Details |
|---|---|
| Root Domain | |
| Discovered Subdomain | |
| DNS Record Type | |
| Resolved IP | |
| HTTP Status | |
| Technology | |
| Scope Verification | |
| Notes | |

## 10. Assessment Questions

1. What is a subdomain?
2. What is subdomain enumeration?
3. What is the difference between passive and active enumeration?
4. What is Certificate Transparency?
5. What is the purpose of Subfinder?
6. What is the difference between A, AAAA, and CNAME records?
7. Does a discovered subdomain automatically become an authorized target?
8. Why is asset inventory important in bug bounty hunting?

## 11. Learning Outcomes

After completing this lab, students will be able to:

- Explain domain and subdomain structures.
- Understand passive and active enumeration.
- Use Subfinder for authorized subdomain discovery.
- Inspect DNS records.
- Verify discovered hostnames.
- Organize subdomain information.
- Prepare an asset inventory.

## 12. Safety Guidelines

- Enumerate only domains explicitly authorized by the program.
- Follow program-specific rate limits.
- Do not assume discovered subdomains are in scope.
- Avoid testing third-party infrastructure.
- Do not access sensitive data or restricted services.
- Use local lab environments for classroom exercises.

---

**SNIT Training Institute | Bug Bounty Hunting Practical Labs**
