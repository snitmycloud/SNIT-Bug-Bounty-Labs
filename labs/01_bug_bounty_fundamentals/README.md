# Lab 01: Introduction to Bug Bounty Hunting & Responsible Disclosure

## 1. Objective

Understand Bug Bounty Hunting, vulnerability research, responsible disclosure, and the role of ethical hackers in identifying security weaknesses in web applications.

## 2. Topics Covered

- What is Bug Bounty Hunting?
- What is Vulnerability Research?
- How Bug Bounty Programs Work
- Public vs Private Bug Bounty Programs
- Security Researcher Responsibilities
- Vulnerability Disclosure Lifecycle
- Scope and Out-of-Scope Assets
- Bug Bounty Platforms
- Responsible Disclosure
- Bug Bounty Report Structure

## 3. Tools and Platforms

- Web Browser
- Burp Suite Community Edition
- HackerOne
- Bugcrowd
- PortSwigger Web Security Academy
- OWASP Juice Shop

## 4. Understanding Bug Bounty Hunting

Bug Bounty Hunting is a security research activity in which authorized researchers identify and report vulnerabilities in applications, websites, APIs, and other digital assets.

Organizations may reward researchers for valid security findings according to their program rules.

### Common Vulnerability Categories

| Vulnerability | Description |
|---|---|
| SQL Injection | Improper handling of database queries |
| Cross-Site Scripting | Injection of malicious scripts into web content |
| IDOR | Unauthorized access to another user's resources |
| Broken Authentication | Weaknesses in authentication mechanisms |
| Security Misconfiguration | Incorrect security settings |
| SSRF | Server-side requests made to unintended destinations |
| Sensitive Data Exposure | Inadequate protection of sensitive information |

## 5. Understanding Bug Bounty Platforms

### HackerOne

HackerOne connects organizations with security researchers through vulnerability disclosure and bug bounty programs.

Website: https://www.hackerone.com/

### Bugcrowd

Bugcrowd provides crowdsourced security testing and vulnerability disclosure programs.

Website: https://www.bugcrowd.com/

### PortSwigger Web Security Academy

Provides free web security training and interactive vulnerability labs.

Website: https://portswigger.net/web-security

## 6. Understanding Bug Bounty Scope

Before testing any application, researchers must understand the program scope.

### In-Scope Assets

Assets explicitly permitted for security testing.

Examples:
- Approved website domains
- Approved subdomains
- Approved API endpoints
- Authorized mobile applications

### Out-of-Scope Assets

Assets that the program does not authorize researchers to test.

Examples:
- Third-party services excluded by the program
- Employee personal accounts
- Production systems explicitly excluded from testing
- Infrastructure not listed in the program scope

**Important:** A domain belonging to an organization is not automatically authorized for testing. Always follow the published program scope and rules.

## 7. Vulnerability Disclosure Lifecycle

1. Researcher reviews the program scope.
2. Researcher identifies a potential vulnerability.
3. Researcher validates the issue safely.
4. Researcher collects supporting evidence.
5. Researcher prepares a vulnerability report.
6. Researcher submits the report through the approved channel.
7. Organization reviews and validates the finding.
8. Organization fixes the vulnerability.
9. Researcher and organization follow the disclosure policy.

## 8. Practical Exercises

### Exercise 1: Explore a Bug Bounty Platform

Visit HackerOne:

https://www.hackerone.com/

Study:
- What is a bug bounty program?
- Who can participate?
- How do researchers submit findings?
- What is responsible disclosure?

### Exercise 2: Understand Program Scope

Visit a publicly accessible bug bounty program page.

Study its published policy and document:

- Program name
- In-scope assets
- Out-of-scope assets
- Allowed testing activities
- Prohibited testing activities
- Reporting requirements
- Disclosure policy

Do not perform testing during this exercise.

### Exercise 3: Explore Vulnerability Categories

Visit PortSwigger Web Security Academy:

https://portswigger.net/web-security

Explore the learning sections for:

- SQL Injection
- Cross-Site Scripting
- Authentication
- Access Control
- Server-Side Request Forgery

Record a short explanation of each category.

### Exercise 4: Understand Responsible Disclosure

Prepare a hypothetical scenario where a researcher discovers an access control weakness.

Document:
- What was discovered?
- What evidence is required?
- How should the researcher report it?
- What actions should the researcher avoid?
- Why is responsible disclosure important?

Use fictional data and do not access real users' information.

## 9. Sample Vulnerability Report Structure

| Section | Information |
|---|---|
| Title | Clear vulnerability title |
| Summary | Short vulnerability explanation |
| Affected Asset | Authorized target |
| Vulnerability Type | Identified vulnerability category |
| Steps to Reproduce | Safe reproduction steps |
| Evidence | Screenshots or sanitized requests |
| Impact | Potential security consequences |
| Recommendation | Suggested remediation |

## 10. Assessment Questions

1. What is Bug Bounty Hunting?
2. What is the difference between ethical hacking and unauthorized hacking?
3. What is an in-scope asset?
4. What is an out-of-scope asset?
5. What is responsible disclosure?
6. What is the purpose of HackerOne?
7. What information should a vulnerability report contain?
8. Why must researchers follow program policies?

## 11. Learning Outcomes

After completing this lab, students will be able to:

- Explain Bug Bounty Hunting concepts.
- Understand public and private bug bounty programs.
- Identify in-scope and out-of-scope assets.
- Explain responsible disclosure.
- Understand the vulnerability reporting lifecycle.
- Navigate basic bug bounty program policies.

## 12. Safety Guidelines

- Never test an asset without explicit authorization.
- Follow the exact program scope and testing policy.
- Do not access, modify, or download other users' private data.
- Avoid destructive testing and denial-of-service activities.
- Use intentionally vulnerable applications for classroom exercises.
- Report findings only through approved disclosure channels.

---

**SNIT Training Institute | Bug Bounty Hunting Practical Labs**
