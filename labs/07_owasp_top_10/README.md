# Lab 07: OWASP Top 10 Vulnerability Assessment

## 1. Lab Overview

The OWASP Top 10 is a widely used awareness document highlighting important categories of web application security risks.

In this lab, students will learn how to identify, understand, and document common web application security weaknesses using intentionally vulnerable applications such as OWASP Juice Shop and PortSwigger Web Security Academy.

The focus is on understanding vulnerabilities, collecting safe evidence, and preparing professional security findings.

**Important:** Perform practical testing only in authorized lab environments. Never test real websites without explicit permission.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand the OWASP Top 10 categories.
- Recognize common web application vulnerabilities.
- Identify security weaknesses through manual testing.
- Use Burp Suite to inspect HTTP requests and responses.
- Understand authentication and access-control risks.
- Identify insecure configurations and data exposure.
- Document findings with evidence and remediation recommendations.

## 3. OWASP Top 10 (2021)

The following categories are from the OWASP Top 10: 2021 edition.

| Category | Description |
|---|---|
| A01: Broken Access Control | Users can access resources or perform actions beyond their permissions. |
| A02: Cryptographic Failures | Sensitive information is not adequately protected. |
| A03: Injection | Untrusted input is interpreted as commands or queries. |
| A04: Insecure Design | Security weaknesses are introduced through design decisions. |
| A05: Security Misconfiguration | Systems or applications use insecure configurations. |
| A06: Vulnerable and Outdated Components | Applications use components with known vulnerabilities. |
| A07: Identification and Authentication Failures | Authentication or session management is improperly implemented. |
| A08: Software and Data Integrity Failures | Software updates or data are not adequately protected against unauthorized modification. |
| A09: Security Logging and Monitoring Failures | Security events are not adequately logged, monitored, or detected. |
| A10: Server-Side Request Forgery (SSRF) | An application can be manipulated into making unintended server-side requests. |

**Note:** OWASP periodically updates its Top 10. This lab uses the 2021 edition as its reference baseline.

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Security testing environment |
| Burp Suite Community | HTTP request and response analysis |
| OWASP Juice Shop | Intentionally vulnerable web application |
| PortSwigger Web Security Academy | Guided web security labs |
| Browser Developer Tools | Inspect application behavior |
| curl | Inspect HTTP responses |

## 5. Lab Environment Setup

Use one of the following intentionally vulnerable learning environments:

- OWASP Juice Shop
- PortSwigger Web Security Academy

Official resources:

- OWASP Juice Shop: https://owasp.org/www-project-juice-shop/
- PortSwigger Academy: https://portswigger.net/web-security
- OWASP Top 10: https://owasp.org/Top10/

Do not use production websites as practice targets.

## 6. Practical Exercises

### Exercise 1: Understand OWASP Top 10 Categories

1. Review the OWASP Top 10 categories.
2. Select five categories.
3. Write one example scenario for each category.
4. Identify the possible business impact.
5. Suggest one preventive security control.

**Deliverable:** OWASP Top 10 study worksheet.

### Exercise 2: Configure Burp Suite

1. Open Burp Suite Community Edition.
2. Start a temporary project.
3. Select the default configuration.
4. Open the built-in browser.
5. Navigate to your authorized lab application.
6. Open the Proxy HTTP history tab.
7. Observe the requests and responses.

Record:

- HTTP method
- Request URL
- Status code
- Request headers
- Response headers
- Cookies

Do not capture or share real users' credentials or session tokens.

### Exercise 3: Broken Access Control Awareness

Use an assigned access-control exercise in OWASP Juice Shop or PortSwigger Academy.

Understand:

- Authentication versus authorization
- Role-based access control
- Horizontal and vertical privilege boundaries
- Insecure direct object references (IDOR)
- Server-side authorization checks

**Task:** Document the security expectation and observed behavior in the training lab.

### Exercise 4: Cryptographic Failures Awareness

Study how applications protect sensitive information.

Inspect your lab application's use of:

- HTTPS
- TLS certificates
- Secure cookies
- Sensitive information in responses
- Appropriate security headers

**Task:** Prepare a checklist of security controls that protect sensitive information.

### Exercise 5: Injection Vulnerability Awareness

Study injection vulnerabilities using the dedicated PortSwigger Academy learning materials.

Understand:

- SQL injection
- Command injection
- Cross-site scripting
- Input validation
- Parameterized queries
- Context-aware output encoding

**Task:** Explain why untrusted input must be handled safely. Perform practical exercises only within the assigned training lab.

### Exercise 6: Security Misconfiguration

Review the configuration of your training application.

Look for examples of:

- Unnecessary information disclosure
- Missing security headers
- Default configurations
- Verbose error messages
- Unnecessary services or features

**Task:** Document the configuration weakness, potential impact, and recommended correction.

### Exercise 7: Authentication and Session Management

Study:

- Password security
- Multi-factor authentication
- Session expiration
- Cookie security attributes
- Secure logout behavior
- Account recovery controls

Use the assigned learning exercises to understand common authentication weaknesses.

### Exercise 8: Vulnerability Assessment Report

Select one vulnerability category from the lab exercises and prepare a finding.

Include:

- Finding title
- OWASP category
- Affected lab application
- Description
- Evidence
- Security impact
- Severity
- Remediation
- Retest result

Use fictional or lab-only data in submitted screenshots and reports.

## 7. Vulnerability Assessment Checklist

| Security Area | Assessment |
|---|---|
| Access Control | |
| Cryptographic Protection | |
| Injection Protection | |
| Secure Design | |
| Security Configuration | |
| Component Security | |
| Authentication | |
| Data Integrity | |
| Logging and Monitoring | |
| SSRF Protection | |

## 8. Student Assessment Questions

1. What is the OWASP Top 10?
2. What is the difference between authentication and authorization?
3. What is Broken Access Control?
4. What is an injection vulnerability?
5. Why are parameterized queries important?
6. What is a security misconfiguration?
7. What is the purpose of secure cookies?
8. What is SSRF?
9. Why should applications use updated dependencies?
10. What information should a professional vulnerability report contain?

## 9. Expected Learning Outcome

After completing this lab, students should be able to:

- Explain the OWASP Top 10 categories.
- Recognize common web application security weaknesses.
- Inspect HTTP traffic using Burp Suite.
- Understand authentication and authorization risks.
- Identify basic security configuration issues.
- Prepare a structured vulnerability assessment report.

## 10. Safety Guidelines

- Use only intentionally vulnerable training applications or explicitly authorized targets.
- Follow all platform rules and lab instructions.
- Do not test public applications without permission.
- Do not access real user accounts or private information.
- Do not perform destructive testing.
- Use lab-only credentials and data.
- Keep evidence limited to what is necessary.

**Lab Status:** Completed after practical exercises, assessment questions, and report review.
