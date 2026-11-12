# SNIT Bug Bounty Vulnerability Report Template

Use this template to document confirmed vulnerabilities discovered in authorized training environments or approved bug bounty programs.

**Important:** Never include real passwords, session tokens, private user information, or confidential data in reports.

---

## 1. Report Information

| Field | Details |
|---|---|
| Report ID | |
| Researcher Name | |
| Date | |
| Program Name | |
| Target Asset | |
| Vulnerability Category | |
| Severity | |
| CVSS Score | |

## 2. Vulnerability Title

[Write a clear and descriptive vulnerability title.]

Example:

`Broken Access Control Allows Unauthorized Access to Another User's Order`

## 3. Vulnerability Summary

[Provide a short explanation of the vulnerability and the affected application functionality.]

## 4. Affected Asset

- Application:
- Domain:
- Endpoint:
- HTTP Method:
- Affected Parameter:

Only include assets that are explicitly authorized for testing.

## 5. Vulnerability Category

Select the relevant category:

- [ ] Broken Access Control
- [ ] IDOR
- [ ] SQL Injection
- [ ] Cross-Site Scripting (XSS)
- [ ] Authentication Failure
- [ ] Security Misconfiguration
- [ ] Sensitive Information Exposure
- [ ] Server-Side Request Forgery (SSRF)
- [ ] Other: __________

## 6. Severity Assessment

**Severity:** Critical / High / Medium / Low / Informational

**CVSS Score:** [If applicable]

**Justification:**

[Explain the realistic security impact and why this severity is appropriate.]

## 7. Description

[Explain how the vulnerability occurs, what security control is missing, and which application functionality is affected.]

## 8. Steps to Reproduce

Provide clear and numbered reproduction steps.

1. Open the authorized training application.
2. Log in using the assigned test account, if required.
3. Navigate to the affected functionality.
4. Perform the approved test.
5. Observe the application behavior.
6. Record the result.

Use fictional accounts and training data.

## 9. Proof of Concept (PoC)

[Describe the minimum safe proof of concept needed to demonstrate the issue.]

### Request Evidence

```http
[Insert sanitized HTTP request]
```

### Response Evidence

```http
[Insert sanitized HTTP response]
```

Remove passwords, cookies, authorization headers, session identifiers, and personal information before sharing evidence.

## 10. Screenshots and Supporting Evidence

Attach relevant screenshots.

Suggested filenames:

```text
01-vulnerability-overview.png
02-request-evidence.png
03-response-evidence.png
04-impact-demonstration.png
```

Each screenshot should clearly demonstrate the relevant behavior without exposing sensitive information.

## 11. Security Impact

Explain the realistic impact of the vulnerability.

Consider:

- Confidentiality impact
- Integrity impact
- Availability impact
- Unauthorized access
- Business impact
- Potential affected users

Avoid claiming impacts that have not been demonstrated.

## 12. Recommended Remediation

[Explain how the development or security team can fix the issue.]

Examples:

- Implement server-side authorization checks.
- Use parameterized SQL queries.
- Apply context-aware output encoding.
- Strengthen authentication controls.
- Configure secure session cookies.
- Apply secure application configuration.

## 13. References

Include relevant documentation.

Examples:

- OWASP Top 10: https://owasp.org/Top10/
- OWASP Cheat Sheet Series: https://cheatsheetseries.owasp.org/
- PortSwigger Web Security Academy: https://portswigger.net/web-security
- CVSS: https://www.first.org/cvss/

## 14. Retest Information

| Field | Details |
|---|---|
| Retest Date | |
| Retest Status | Fixed / Partially Fixed / Not Fixed / Not Retested |
| Retest Evidence | |
| Additional Notes | |

## 15. Final Report Checklist

- [ ] Target is authorized and in scope.
- [ ] Vulnerability is confirmed.
- [ ] Title clearly describes the issue.
- [ ] Affected endpoint is identified.
- [ ] Reproduction steps are clear.
- [ ] Evidence is relevant and sanitized.
- [ ] Security impact is explained.
- [ ] Severity is justified.
- [ ] Remediation is recommended.
- [ ] No confidential information is exposed.
- [ ] Report follows program submission rules.

---

## Researcher Declaration

I confirm that the assessment documented in this report was performed within the authorized scope and in accordance with the applicable testing rules.

**Researcher Name:** ____________________

**Date:** ____________________

**Signature:** ____________________

---

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
