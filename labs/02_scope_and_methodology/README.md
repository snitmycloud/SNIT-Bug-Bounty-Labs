# Lab 02: Bug Bounty Scope Analysis & Testing Methodology

## 1. Objective

Learn how to analyze bug bounty program policies, identify authorized assets, understand testing restrictions, and develop a structured web application security testing methodology.

## 2. Topics Covered

- Bug bounty program policy analysis
- In-scope and out-of-scope assets
- Wildcard domain scope
- Domain and subdomain relationships
- Testing restrictions
- Rules of engagement
- Vulnerability severity
- Testing methodology
- Evidence collection
- Research documentation

## 3. Tools Required

- Web Browser
- Burp Suite Community Edition
- Browser Developer Tools
- HackerOne
- Bugcrowd
- Markdown editor

## 4. Understanding Bug Bounty Scope

Scope defines which applications, domains, APIs, and systems a researcher is permitted to test.

A professional researcher must review the program policy before performing any security testing.

### Common Scope Types

| Scope Type | Example | Explanation |
|---|---|---|
| Domain | example.com | Specific approved domain |
| Subdomain | app.example.com | Approved application subdomain |
| Wildcard | *.example.com | May include eligible subdomains, subject to policy |
| API | api.example.com | Approved API endpoint or service |
| Mobile Application | Official Android application | Application explicitly listed in scope |

**Important:** A wildcard does not automatically authorize every related asset, third-party service, or infrastructure component. Always follow the program's exact policy.

## 5. In-Scope vs Out-of-Scope

### In-Scope Examples

- Approved web applications
- Listed API endpoints
- Authorized mobile applications
- Explicitly included subdomains

### Out-of-Scope Examples

- Third-party services
- Employee personal accounts
- Systems explicitly excluded by the program
- Denial-of-service testing when prohibited
- Social engineering when prohibited
- Production data belonging to other users

## 6. Understanding Rules of Engagement

Before testing, document:

1. Approved targets
2. Prohibited testing techniques
3. Rate limits
4. Authentication requirements
5. Account creation rules
6. Data handling requirements
7. Reporting procedure
8. Disclosure policy

Researchers must follow the latest published policy throughout the assessment.

## 7. Professional Bug Bounty Testing Methodology

A structured methodology helps researchers perform consistent and controlled assessments.

### Phase 1: Program Analysis

- Read the program policy.
- Identify approved assets.
- Understand exclusions.
- Record testing restrictions.

### Phase 2: Reconnaissance Planning

- Identify approved domains.
- Understand application functionality.
- Identify authentication requirements.
- Document application entry points.

### Phase 3: Application Mapping

- Identify major application pages.
- Understand user roles.
- Observe HTTP requests and responses.
- Identify input fields and API interactions.

### Phase 4: Vulnerability Assessment

- Authentication testing
- Authorization testing
- Input validation testing
- Session management testing
- Security configuration review

### Phase 5: Validation

- Reproduce the suspected issue safely.
- Confirm the actual security impact.
- Avoid accessing other users' information.
- Collect sanitized evidence.

### Phase 6: Reporting

- Write a clear vulnerability description.
- Document reproduction steps.
- Explain potential impact.
- Provide remediation recommendations.
- Submit through the approved channel.

## 8. Practical Exercises

### Exercise 1: Analyze a Public Bug Bounty Policy

Visit:

https://hackerone.com/directory/programs

Select a publicly accessible program and review its published policy.

Document:

- Program name
- Approved domains
- Approved applications
- Out-of-scope assets
- Prohibited testing activities
- Rate limits
- Reporting instructions

Do not perform testing during this exercise.

### Exercise 2: Create a Scope Documentation Sheet

Use a fictional training organization:

`example.com`

Prepare the following sample scope:

| Asset | Scope Status | Reason |
|---|---|---|
| www.example.com | In scope | Explicitly authorized |
| app.example.com | In scope | Explicitly authorized |
| api.example.com | Out of scope | Not authorized |
| payments.thirdparty.com | Out of scope | Third-party service |
| dev.example.com | Unknown | Requires program clarification |

Treat this as a classroom exercise, not permission to test these domains.

### Exercise 3: Identify Application Entry Points

Use an intentionally vulnerable local application such as OWASP Juice Shop.

Study its normal application functionality and document:

- Login page
- Registration page
- Search functionality
- User profile
- Product pages
- API interactions

Do not attempt exploitation in this exercise.

### Exercise 4: Prepare a Testing Plan

Create a short assessment plan containing:

- Assessment objective
- Authorized target
- Testing restrictions
- Application functionality
- Planned test categories
- Evidence collection approach
- Reporting procedure

## 9. Scope Documentation Template

| Field | Details |
|---|---|
| Program Name | |
| Program URL | |
| Approved Domain | |
| Approved Subdomains | |
| Approved Applications | |
| Excluded Assets | |
| Testing Restrictions | |
| Rate Limits | |
| Reporting Channel | |
| Policy Review Date | |

## 10. Assessment Questions

1. What is bug bounty scope?
2. What is the difference between in-scope and out-of-scope assets?
3. Does a wildcard domain always authorize every subdomain?
4. Why should researchers review program policies?
5. What are rules of engagement?
6. What is application mapping?
7. Why is evidence collection important?
8. What should be included in a professional testing plan?

## 11. Learning Outcomes

After completing this lab, students will be able to:

- Analyze bug bounty program policies.
- Identify authorized and excluded assets.
- Understand rules of engagement.
- Prepare a structured testing methodology.
- Identify application entry points.
- Document assessment scope and restrictions.

## 12. Safety Guidelines

- Never assume ownership means authorization.
- Test only explicitly approved assets.
- Follow program-specific restrictions and rate limits.
- Do not access or modify other users' private data.
- Do not perform destructive testing.
- Use local vulnerable applications for classroom practicals.

---

**SNIT Training Institute | Bug Bounty Hunting Practical Labs**
