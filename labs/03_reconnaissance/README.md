# Lab 03: Web Application Reconnaissance

## 1. Objective

Understand web application reconnaissance techniques and learn how to collect, analyze, and document information about authorized web applications before performing security testing.

## 2. Topics Covered

- Introduction to Web Application Reconnaissance
- Passive and Active Reconnaissance
- Domain and DNS Information
- HTTP Request and Response Analysis
- Website Technology Identification
- Application Mapping
- Publicly Available Information
- robots.txt and sitemap.xml
- Identifying Application Entry Points
- Reconnaissance Documentation

## 3. Tools Required

- Kali Linux
- Browser Developer Tools
- Burp Suite Community Edition
- Nmap
- WhatWeb
- DNS utilities
- curl
- WHOIS

## 4. Understanding Web Application Reconnaissance

Reconnaissance is the process of collecting information about a target before conducting a security assessment.

It helps researchers understand:

- Application structure
- Domain and subdomain information
- Technologies used by the application
- Available pages and endpoints
- HTTP communication
- Publicly exposed information

### Passive Reconnaissance

Collecting information from publicly available sources without directly interacting with the target infrastructure.

Examples:

- Public DNS records
- Search engine results
- Public documentation
- Certificate transparency records
- Public technology information

### Active Reconnaissance

Interacting directly with an authorized target to collect technical information.

Examples:

- HTTP header inspection
- DNS queries
- Technology detection
- Application mapping
- Authorized service discovery

## 5. Understanding HTTP Requests and Responses

A browser communicates with a web server through HTTP requests and responses.

### Sample HTTP Request

```http
GET / HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Accept: text/html
```

### Sample HTTP Response

```http
HTTP/1.1 200 OK
Content-Type: text/html
Server: nginx
```

Important response status codes:

| Code | Meaning |
|---|---|
| 200 | OK |
| 301 | Permanent Redirect |
| 302 | Temporary Redirect |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

## 6. Practical Exercises

Use an intentionally vulnerable local application or an explicitly authorized training target.

### Exercise 1: Inspect Website HTTP Headers

Using curl:

```bash
curl -I http://<AUTHORIZED-LAB-TARGET>
```

Observe:

- HTTP status code
- Server header
- Content type
- Redirect information
- Security-related headers

### Exercise 2: Inspect Website Response

```bash
curl -v http://<AUTHORIZED-LAB-TARGET>
```

Study the request and response information displayed by curl.

Do not publish cookies, authentication tokens, or other sensitive response data.

### Exercise 3: Identify Website Technologies

Using WhatWeb against your authorized lab application:

```bash
whatweb http://<AUTHORIZED-LAB-TARGET>
```

Observe:

- Web server
- Framework
- Programming language indicators
- CMS information
- Other detected technologies

Technology detection results are estimates and should be independently verified.

### Exercise 4: Inspect DNS Information

Check the DNS A record:

```bash
dig <AUTHORIZED-LAB-DOMAIN> A
```

Check the MX record:

```bash
dig <AUTHORIZED-LAB-DOMAIN> MX
```

Check the NS record:

```bash
dig <AUTHORIZED-LAB-DOMAIN> NS
```

Check the TXT record:

```bash
dig <AUTHORIZED-LAB-DOMAIN> TXT
```

Use only domains included in your approved assessment scope.

### Exercise 5: Inspect robots.txt

Visit:

```text
http://<AUTHORIZED-LAB-TARGET>/robots.txt
```

Observe whether the file contains:

- User-agent directives
- Disallowed paths
- Sitemap references

Remember that robots.txt is not an access control mechanism. A listed path is not permission to access it.

### Exercise 6: Inspect sitemap.xml

Visit:

```text
http://<AUTHORIZED-LAB-TARGET>/sitemap.xml
```

Observe the publicly listed website URLs and document the application structure.

### Exercise 7: Analyze Browser Requests

1. Open your authorized lab application.
2. Press F12.
3. Select the Network tab.
4. Reload the application.
5. Inspect HTTP requests.
6. Review request methods, status codes, headers, and response types.

Document the important application endpoints without collecting sensitive user data.

## 7. Application Mapping Worksheet

| Application Component | Observation |
|---|---|
| Homepage | |
| Login Page | |
| Registration Page | |
| Search Functionality | |
| User Profile | |
| API Endpoints | |
| Technology Stack | |
| robots.txt | |
| sitemap.xml | |

## 8. Reconnaissance Report Template

Document the following:

- Assessment name
- Authorized target
- Assessment date
- Domain information
- DNS observations
- HTTP response details
- Detected technologies
- Application entry points
- Publicly available information
- Screenshots and supporting evidence

## 9. Assessment Questions

1. What is web application reconnaissance?
2. What is the difference between passive and active reconnaissance?
3. What information can HTTP headers reveal?
4. What is the purpose of DNS A, MX, and NS records?
5. What is the purpose of robots.txt?
6. What is sitemap.xml?
7. How does WhatWeb identify website technologies?
8. Why should researchers map an application before vulnerability testing?

## 10. Learning Outcomes

After completing this lab, students will be able to:

- Explain web application reconnaissance.
- Differentiate passive and active reconnaissance.
- Inspect HTTP requests and responses.
- Collect basic DNS information.
- Identify website technologies.
- Understand website structure.
- Document application entry points.
- Prepare a basic reconnaissance report.

## 11. Safety Guidelines

- Test only explicitly authorized applications.
- Use local vulnerable applications for classroom exercises.
- Respect program scope and rate limits.
- Do not access restricted paths or sensitive information.
- Do not collect or disclose authentication tokens or personal data.
- Document findings responsibly.

---

**SNIT Training Institute | Bug Bounty Hunting Practical Labs**
