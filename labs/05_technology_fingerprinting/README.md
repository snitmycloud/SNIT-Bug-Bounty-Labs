# Lab 05: Technology Fingerprinting & Web Server Identification

## 1. Lab Overview

Technology fingerprinting is the process of identifying the technologies used by a web application. This helps security testers understand the application's technology stack and identify potential areas for further security assessment.

In this lab, students will examine web servers, frameworks, CMS platforms, JavaScript libraries, HTTP headers, cookies, and TLS certificates.

**Important:** Perform all testing only on authorized targets or intentionally vulnerable lab applications.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Identify web server technologies.
- Recognize common CMS platforms and web frameworks.
- Inspect HTTP response headers.
- Identify JavaScript libraries and client-side technologies.
- Examine cookies and basic security attributes.
- Understand TLS certificate information.
- Document fingerprinting results and their confidence level.

## 3. Topics Covered

1. Web technology stack fundamentals
2. Web server identification
3. Framework and CMS detection
4. JavaScript library identification
5. HTTP header analysis
6. Cookie inspection
7. CDN and WAF identification
8. TLS certificate inspection
9. Fingerprinting limitations and false positives

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| WhatWeb | Website technology identification |
| Wappalyzer | Browser-based technology detection |
| curl | HTTP request and response inspection |
| Browser Developer Tools | Inspect network activity and resources |
| Burp Suite Community | Examine HTTP requests and responses |
| OpenSSL | Inspect TLS certificates |

## 5. Understanding a Web Technology Stack

A typical web application may contain several technology layers:

- **Web Server:** Apache, Nginx, Microsoft IIS
- **Programming Language:** PHP, Python, Java, JavaScript
- **Framework:** Django, Laravel, Express, Spring
- **CMS:** WordPress, Drupal, Joomla
- **Database:** MySQL, PostgreSQL, MongoDB
- **JavaScript Libraries:** React, Angular, jQuery
- **CDN/WAF:** Cloudflare and other content delivery or security services

Fingerprinting attempts to identify these technologies using publicly observable information.

## 6. Practical Exercises

### Exercise 1: Identify Website Technologies Using WhatWeb

WhatWeb is a tool used to identify technologies associated with web applications.

Check the installation:

```bash
whatweb --version
```

Run it against an authorized lab target:

```bash
whatweb http://<AUTHORIZED-LAB-TARGET>
```

For more detailed output:

```bash
whatweb -v http://<AUTHORIZED-LAB-TARGET>
```

**Observe:**

- Web server
- Programming language indicators
- CMS
- Framework
- Cookies
- Other detected technologies

Record the results in your worksheet.

### Exercise 2: Inspect HTTP Response Headers

Use curl to retrieve HTTP response headers:

```bash
curl -I http://<AUTHORIZED-LAB-TARGET>
```

For a detailed request and response:

```bash
curl -v http://<AUTHORIZED-LAB-TARGET>
```

Look for headers such as:

- Server
- X-Powered-By
- Content-Type
- Set-Cookie
- Strict-Transport-Security
- Content-Security-Policy
- X-Frame-Options

**Task:** Identify which headers reveal technology information and which headers relate to security.

### Exercise 3: Technology Detection Using Wappalyzer

1. Open your browser.
2. Install the Wappalyzer browser extension from its official browser extension store.
3. Open your authorized lab application.
4. Select the Wappalyzer extension.
5. Review the detected technologies.

Record:

- CMS
- Web server
- JavaScript frameworks
- Analytics tools
- Programming language indicators
- CDN or hosting-related technologies

Compare the results with WhatWeb.

### Exercise 4: Browser Developer Tools Analysis

1. Open your authorized lab application.
2. Press `F12`.
3. Select the **Network** tab.
4. Reload the page.
5. Select the main document request.
6. Inspect the response headers.
7. Review JavaScript and CSS resources.
8. Inspect cookies through the browser's Storage or Application panel.

**Questions to investigate:**

- Which server-related headers are visible?
- Which JavaScript libraries are loaded?
- Are cookies configured with Secure and HttpOnly attributes?
- Is HTTPS being used?
- Are security-related response headers present?

### Exercise 5: Inspect TLS Certificate Information

For an authorized HTTPS lab host, use:

```bash
openssl s_client -connect <AUTHORIZED-HOST>:443 -servername <AUTHORIZED-HOST>
```

Review the certificate information, including:

- Certificate subject
- Issuer
- Validity period
- Subject Alternative Names
- Certificate chain

You can also inspect certificate details through your browser's site information panel.

## 7. Understanding Fingerprinting Limitations

Technology fingerprinting does not always provide definitive results.

Keep these points in mind:

- HTTP headers can be removed or modified.
- A CDN or WAF may hide the origin server.
- Different technologies can produce similar responses.
- Technology detection tools may generate false positives.
- A detected technology version should be verified before reporting a vulnerability.

Always record the evidence and confidence level instead of treating every tool result as confirmed fact.

## 8. Student Practical Worksheet

Complete the following table using an authorized lab application.

| Field | Observation |
|---|---|
| Target URL | |
| Web Server | |
| Programming Language | |
| Framework | |
| CMS | |
| JavaScript Libraries | |
| CDN/WAF | |
| HTTPS Enabled | |
| Security Headers | |
| Cookie Attributes | |
| TLS Certificate Issuer | |
| Evidence Source | |
| Confidence Level | |

## 9. Assessment Questions

1. What is technology fingerprinting?
2. What is the purpose of WhatWeb?
3. How can HTTP response headers reveal technology information?
4. What is the difference between a web server and a web framework?
5. What is the purpose of Wappalyzer?
6. What information can be obtained from a TLS certificate?
7. Why can fingerprinting tools produce false positives?
8. How can a CDN or WAF affect technology identification?
9. What are Secure and HttpOnly cookie attributes?
10. Why should detected technology versions be verified before reporting vulnerabilities?

## 10. Expected Learning Outcome

After completing this lab, students should be able to:

- Perform basic web technology fingerprinting.
- Identify common web application components.
- Inspect HTTP headers and cookies.
- Review TLS certificate information.
- Prepare a technology fingerprinting worksheet.
- Explain the limitations of technology detection.

## 11. Safety Guidelines

- Test only authorized targets.
- Follow the bug bounty program's scope and rules.
- Do not perform exploitation in this lab.
- Do not attempt to bypass security controls.
- Do not access or collect private user information.
- Keep evidence limited to what is necessary for the assessment.

**Lab Status:** Completed after all exercises and the worksheet have been reviewed.
