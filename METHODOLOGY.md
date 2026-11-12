# SNIT Bug Bounty Hunting Methodology

## 1. Introduction

This document defines the standard methodology followed by students and security researchers during authorized bug bounty assessments.

The objective is to provide a structured approach to discovering, validating, documenting, and responsibly reporting web application security vulnerabilities.

All activities must comply with the target organization's bug bounty policy, scope, and rules of engagement.

## 2. Bug Bounty Assessment Workflow

The assessment follows these ten phases:

1. Program Selection and Scope Verification
2. Passive Reconnaissance
3. Asset Discovery
4. Technology Fingerprinting
5. Application Mapping
6. Vulnerability Assessment
7. Safe Vulnerability Validation
8. Risk and Severity Assessment
9. Vulnerability Reporting
10. Responsible Disclosure

---

## Phase 1: Program Selection and Scope Verification

Before starting any assessment, understand the bug bounty program.

### Activities

- Select an authorized bug bounty program.
- Read the program policy.
- Identify in-scope domains and applications.
- Identify excluded assets.
- Review testing restrictions.
- Understand rate limits.
- Review prohibited testing techniques.
- Understand the reporting process.

### Important Questions

- Which domains are authorized?
- Are subdomains included?
- Are mobile applications included?
- Are APIs included?
- Is automated scanning permitted?
- Are there restrictions on authentication testing?

**Deliverable:** Scope documentation.

## Phase 2: Passive Reconnaissance

Passive reconnaissance involves collecting publicly available information without directly interacting with the target application in a way that performs active testing.

### Activities

- Domain information collection
- WHOIS information review
- DNS record analysis
- Certificate transparency research
- Public technology information
- Publicly available documentation review

### Tools

- WHOIS
- dig
- crt.sh
- Search engines
- Subfinder in approved passive collection modes

**Deliverable:** Initial reconnaissance notes.

## Phase 3: Asset Discovery

Asset discovery identifies the authorized systems and resources associated with the program.

### Activities

- Review in-scope domains.
- Identify explicitly authorized subdomains.
- Review publicly documented API endpoints.
- Identify web application entry points.
- Record discovered assets.
- Verify every asset against the program scope.

### Tools

- Subfinder
- DNS utilities
- Certificate transparency services
- Browser
- Public documentation

**Important:** Discovering an asset does not automatically authorize testing it. Confirm scope before interacting with it.

**Deliverable:** Authorized asset inventory.

## Phase 4: Technology Fingerprinting

Identify the technologies used by the authorized application.

### Activities

- Identify web server indicators.
- Identify programming language indicators.
- Identify CMS platforms.
- Identify frameworks.
- Identify JavaScript libraries.
- Inspect HTTP response headers.
- Review TLS certificate information.
- Identify CDN or WAF indicators.

### Tools

- WhatWeb
- Wappalyzer
- curl
- Browser Developer Tools
- Burp Suite

**Deliverable:** Technology fingerprinting worksheet.

## Phase 5: Application Mapping

Application mapping helps students understand the structure and functionality of a web application.

### Activities

- Identify public pages.
- Map login and registration functionality.
- Identify search features.
- Review application forms.
- Identify API endpoints.
- Understand user roles.
- Map application workflows.
- Identify security-relevant input points.

### Tools

- Burp Suite Community
- Browser Developer Tools
- Browser
- curl

**Deliverable:** Application endpoint and functionality map.

## Phase 6: Vulnerability Assessment

Evaluate the application for security weaknesses using approved testing methods.

### Areas to Assess

- OWASP Top 10
- Authentication security
- Session management
- Access control
- IDOR
- SQL Injection
- Cross-Site Scripting
- Security misconfiguration
- Sensitive information exposure
- API security

### Tools

- Burp Suite Community
- OWASP Juice Shop
- PortSwigger Web Security Academy
- Browser Developer Tools

**Deliverable:** Potential vulnerability assessment notes.

## Phase 7: Safe Vulnerability Validation

Validate whether a suspected security issue is genuine.

### Activities

- Reproduce the issue using authorized test accounts.
- Confirm the affected endpoint.
- Review the application response.
- Determine whether a security boundary is violated.
- Collect minimal evidence.
- Avoid accessing private information.
- Stop testing once sufficient evidence is obtained.

### Validation Principles

- Use non-destructive techniques.
- Avoid unnecessary data access.
- Do not modify or delete production records.
- Do not disrupt application availability.
- Follow program-specific restrictions.

**Deliverable:** Validated vulnerability evidence.

## Phase 8: Risk and Severity Assessment

Determine the realistic impact of the confirmed vulnerability.

### Assessment Factors

- Attack Vector
- Attack Complexity
- Privileges Required
- User Interaction
- Confidentiality Impact
- Integrity Impact
- Availability Impact
- Business impact

### Severity Categories

| Severity | Description |
|---|---|
| Critical | Extremely serious security impact |
| High | Significant security impact |
| Medium | Moderate security impact |
| Low | Limited security impact |
| Informational | Security observation without demonstrated direct impact |

Use CVSS as a reference when appropriate.

Reference: https://www.first.org/cvss/

**Deliverable:** Severity assessment.

## Phase 9: Vulnerability Reporting

Prepare a professional vulnerability report.

### Report Structure

1. Vulnerability title
2. Summary
3. Affected asset
4. Vulnerability category
5. Severity
6. Description
7. Steps to reproduce
8. Proof of Concept
9. Security impact
10. Recommended remediation
11. References

### Reporting Guidelines

- Use clear technical language.
- Include reproducible steps.
- Provide relevant evidence.
- Explain realistic impact.
- Avoid unnecessary sensitive information.
- Recommend practical remediation.

**Deliverable:** Final vulnerability report.

## Phase 10: Responsible Disclosure

Responsible disclosure ensures vulnerabilities are communicated securely and professionally.

### Activities

- Submit the report through the authorized platform.
- Follow the organization's communication process.
- Respond to clarification requests.
- Provide additional evidence when requested.
- Respect confidentiality requirements.
- Follow the program's disclosure policy.

**Deliverable:** Submitted vulnerability report and communication record.

---

## 3. Recommended Bug Bounty Workflow

```text
Program Selection
       |
       v
Scope Verification
       |
       v
Passive Reconnaissance
       |
       v
Asset Discovery
       |
       v
Technology Fingerprinting
       |
       v
Application Mapping
       |
       v
Vulnerability Assessment
       |
       v
Safe Validation
       |
       v
Severity Assessment
       |
       v
Report Preparation
       |
       v
Responsible Disclosure
```

## 4. Standard Documentation to Maintain

Students should maintain the following documents throughout an assessment:

| Document | Purpose |
|---|---|
| Scope Notes | Record authorized and excluded assets |
| Reconnaissance Notes | Record collected public information |
| Asset Inventory | Track authorized assets |
| Technology Worksheet | Document application technologies |
| Endpoint Inventory | Record application functionality |
| Vulnerability Notes | Record potential security weaknesses |
| Evidence Folder | Store relevant screenshots and evidence |
| Final Report | Document confirmed vulnerabilities |

## 5. Recommended Training Platforms

- HackerOne: https://www.hackerone.com/
- Bugcrowd: https://www.bugcrowd.com/
- PortSwigger Web Security Academy: https://portswigger.net/web-security
- OWASP Juice Shop: https://owasp.org/www-project-juice-shop/

Use training environments for practical exercises and follow individual program policies for any real-world assessments.

## 6. Final Methodology Checklist

- [ ] Program policy reviewed
- [ ] Scope verified
- [ ] Excluded assets documented
- [ ] Passive reconnaissance completed
- [ ] Authorized assets inventoried
- [ ] Technology fingerprinting completed
- [ ] Application mapping completed
- [ ] Vulnerability assessment performed
- [ ] Findings safely validated
- [ ] Severity assessed
- [ ] Evidence documented
- [ ] Vulnerability report prepared
- [ ] Responsible disclosure requirements followed

## 7. Final Note

The objective of bug bounty hunting is not simply to find vulnerabilities. It is to identify genuine security weaknesses, demonstrate their impact responsibly, and help organizations improve their security posture.

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
