# SNIT Bug Bounty Rules & Responsible Testing Guidelines

## 1. Purpose

This document defines the ethical and operational rules students must follow while performing bug bounty hunting and web application security assessments.

The objective is to ensure that all security testing is authorized, controlled, non-destructive, and professionally documented.

These guidelines apply to all students using SNIT Bug Bounty Labs.

## 2. Authorization Requirements

Before testing any website, application, API, or network asset:

- Obtain explicit authorization.
- Read the bug bounty program policy.
- Verify the target is in scope.
- Identify excluded domains and services.
- Understand testing restrictions.
- Follow the program's rules of engagement.

**Important:** Publicly accessible does not mean authorized for security testing.

## 3. Scope Management

Every bug bounty program defines assets that are allowed or excluded from testing.

### In-Scope Assets

Examples may include:

- Explicitly listed domains
- Approved subdomains
- Specified web applications
- Authorized API endpoints
- Approved mobile applications

### Out-of-Scope Assets

Examples may include:

- Domains explicitly excluded by the program
- Third-party services
- Employee personal accounts
- External infrastructure not covered by authorization
- Production systems excluded by program policy

Always verify the exact asset against the program's current scope.

## 4. Permitted Testing Activities

Only perform activities explicitly permitted by the program or lab instructions.

Examples of commonly permitted activities, subject to authorization:

- Passive reconnaissance
- DNS information collection
- Technology fingerprinting
- Application mapping
- Manual security testing
- Testing assigned lab vulnerabilities
- Reviewing HTTP requests and responses
- Preparing vulnerability reports

Permission for one activity does not automatically authorize every other activity.

## 5. Prohibited Activities

Unless a program explicitly provides separate authorization, students must not perform:

- Denial-of-Service (DoS) attacks
- Distributed Denial-of-Service (DDoS) attacks
- Destructive testing
- Data deletion or modification
- Unauthorized account access
- Credential theft
- Phishing or social engineering
- Malware deployment
- Persistence or backdoor installation
- Unauthorized access to third-party systems
- Testing outside the defined scope
- Exfiltration of private or confidential information
- Security control bypass attempts that violate program policy

## 6. Account and Authentication Safety

During practical assessments:

- Use only assigned training accounts.
- Use fictional or lab-provided credentials.
- Do not attempt to access another person's account.
- Do not collect real credentials.
- Do not share session tokens.
- Do not reuse another user's authenticated session.
- Respect account lockout and rate-limit controls.

## 7. Data Protection Requirements

Students must protect all information encountered during testing.

### Data Protection Rules

- Do not download unnecessary sensitive information.
- Do not expose personal information in screenshots.
- Do not store passwords or session tokens in reports.
- Do not share confidential application data.
- Redact sensitive information before submitting evidence.
- Delete temporary test data according to lab or program instructions.

If sensitive information is accidentally exposed, stop testing and follow the organization's reporting procedure.

## 8. Safe Testing Practices

Follow these practices during every assessment:

1. Use authorized environments.
2. Start with non-destructive testing.
3. Respect request-rate limits.
4. Avoid unnecessary automated scans.
5. Use minimal proof-of-concept evidence.
6. Stop when sufficient evidence is collected.
7. Avoid affecting application availability.
8. Report unexpected exposure promptly.
9. Maintain an accurate testing record.

## 9. Responsible Disclosure

Responsible disclosure means communicating vulnerabilities through the organization's authorized reporting process.

### Disclosure Guidelines

- Submit findings through the official reporting channel.
- Provide clear reproduction steps.
- Include relevant evidence.
- Explain realistic security impact.
- Recommend practical remediation.
- Protect confidential information.
- Follow the organization's disclosure timeline.
- Do not publicly disclose confidential findings without authorization.

## 10. Bug Bounty Platform Rules

When using platforms such as HackerOne or Bugcrowd:

- Read the individual program policy.
- Follow the specified scope.
- Respect prohibited testing techniques.
- Follow rate limits.
- Review duplicate-report policies.
- Use the approved communication channel.
- Respect confidentiality requirements.

Platform membership alone does not grant permission to test every listed organization or asset.

## 11. Student Lab Environment Rules

For SNIT practical training:

- Use OWASP Juice Shop for assigned exercises.
- Use PortSwigger Web Security Academy for guided labs.
- Use instructor-approved virtual machines.
- Use isolated lab networks where appropriate.
- Do not connect intentionally vulnerable applications to public networks unless the exercise explicitly requires an approved setup.
- Do not test unrelated systems on the local network.

## 12. Security Incident Procedure

If unexpected sensitive information, unauthorized access, or system disruption occurs:

1. Stop the testing activity.
2. Do not access additional information.
3. Do not modify or delete any data.
4. Preserve only the minimum necessary evidence.
5. Notify the instructor or authorized program contact.
6. Follow the organization's incident reporting instructions.

## 13. Student Code of Conduct

Every student participating in SNIT Bug Bounty Labs must:

- Act ethically and professionally.
- Respect privacy and confidentiality.
- Follow all authorization requirements.
- Avoid destructive activities.
- Document findings honestly.
- Never exaggerate vulnerability impact.
- Respect organizations and their systems.
- Follow applicable laws and program policies.

## 14. Student Safety Checklist

Before every practical exercise, confirm:

- [ ] The target is authorized.
- [ ] The target is within scope.
- [ ] The testing method is permitted.
- [ ] The assigned test account is being used.
- [ ] Rate limits and restrictions are understood.
- [ ] The activity is non-destructive.
- [ ] No real user data is being accessed.
- [ ] Evidence will be stored securely.
- [ ] Reporting requirements are understood.

## 15. Important Disclaimer

This repository is intended for cybersecurity education and authorized security testing.

SNIT Training Institute does not authorize students to test third-party websites, applications, networks, or infrastructure without explicit permission from the relevant owner.

Students are responsible for following applicable laws, program policies, and instructor guidance.

**Learn ethically. Test responsibly. Report professionally.**

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
