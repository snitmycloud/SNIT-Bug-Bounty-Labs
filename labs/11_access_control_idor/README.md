# Lab 11: Access Control and IDOR Vulnerability Assessment

## 1. Lab Overview

Access control ensures that users can access only the resources and perform only the actions permitted by their roles and permissions.

Insecure Direct Object Reference (IDOR) is an access control vulnerability that occurs when an application exposes references to objects, such as user IDs, order IDs, or document IDs, without properly verifying whether the requesting user is authorized to access them.

In this lab, students will learn access control fundamentals, understand IDOR scenarios, inspect application requests, and document security weaknesses using intentionally vulnerable training applications.

**Important:** Perform all practical testing only in authorized training environments using fictional accounts and data.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand access control mechanisms.
- Differentiate authentication and authorization.
- Understand role-based access control.
- Identify horizontal and vertical privilege escalation concepts.
- Explain IDOR vulnerabilities.
- Inspect object references in HTTP requests.
- Understand server-side authorization checks.
- Prepare access control vulnerability reports.

## 3. Topics Covered

1. Access control fundamentals
2. Authentication versus authorization
3. Role-Based Access Control (RBAC)
4. Horizontal privilege escalation
5. Vertical privilege escalation
6. Insecure Direct Object Reference (IDOR)
7. Object-level authorization
8. API access control
9. Server-side authorization
10. Access control remediation

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Burp Suite Community | HTTP request and response analysis |
| OWASP Juice Shop | Intentionally vulnerable application |
| PortSwigger Academy | Guided access control labs |
| Browser Developer Tools | Inspect application behavior |
| curl | HTTP request inspection |

## 5. Understanding Access Control

Access control determines which resources and actions are available to a user.

For example, an application may have three roles:

| Role | Example Permissions |
|---|---|
| Guest | View public information |
| Standard User | Manage their own profile and orders |
| Administrator | Manage users and application settings |

The application must enforce these permissions on the server side. Hiding a button in the browser is not sufficient security.

## 6. Understanding IDOR

IDOR occurs when an application uses a user-controlled object reference without checking whether the current user is authorized to access the referenced object.

Common object references include:

- User IDs
- Order IDs
- Invoice IDs
- Document IDs
- Account numbers
- API resource identifiers

**Example scenario:**

A fictional training application provides an order reference to a user. If the application does not verify ownership before returning the order details, another user may be able to access information they are not authorized to view.

An unpredictable identifier can make guessing harder, but it does not replace proper authorization checks.

## 7. Types of Access Control Weaknesses

### Horizontal Privilege Escalation

A user accesses another user's resources or performs actions outside their own account permissions.

### Vertical Privilege Escalation

A user performs actions that should be restricted to a higher-privileged role, such as an administrator.

### Insecure Direct Object Reference

An application fails to verify authorization when a user requests an object using a direct reference.

## 8. Practical Exercises

### Exercise 1: Understand User Roles

1. Open your assigned training application.
2. Review the available user roles.
3. Identify the actions permitted for each role.
4. Create a role-permission matrix.

**Task:** Explain why the server must verify permissions for every protected action.

### Exercise 2: Inspect Object References

1. Open your authorized training application.
2. Log in using an assigned test account.
3. Navigate to a feature that displays fictional records, such as orders or profiles.
4. Open Burp Suite Proxy HTTP history.
5. Inspect the request parameters and URL path.
6. Identify any object references used by the application.

Record:

- Request method
- Endpoint
- Object reference type
- User role
- Expected access permission

Do not access another user's records outside an explicitly assigned training exercise.

### Exercise 3: Study Horizontal Access Control

Use the assigned access-control exercise in PortSwigger Web Security Academy.

Understand:

- User ownership
- Resource-level authorization
- Horizontal privilege boundaries
- Server-side permission checks

**Task:** Document the expected authorization behavior using the fictional accounts supplied by the training platform.

### Exercise 4: Study Vertical Access Control

Use the assigned vertical privilege escalation exercise.

Understand:

- Standard user permissions
- Administrator permissions
- Role-based authorization
- Restricted administrative functions

**Task:** Prepare a table comparing the permissions of standard users and administrators.

### Exercise 5: Understand IDOR in APIs

Study how APIs expose resources using identifiers.

Example of a fictional API resource:

```text
GET /api/training/orders/{order_id}
```

Review these security questions:

- Does the server authenticate the user?
- Does the server verify ownership of the requested order?
- Are permissions checked on every request?
- Does the API return only authorized information?
- Are unauthorized requests handled appropriately?

Use only the assigned lab exercise to observe these behaviors.

### Exercise 6: Review Secure Access Control Design

Study the following security recommendations:

1. Enforce authorization on the server side.
2. Verify resource ownership for every protected request.
3. Apply least-privilege permissions.
4. Use deny-by-default authorization.
5. Avoid relying on hidden buttons or client-side checks.
6. Validate permissions consistently across web and API endpoints.
7. Log relevant access-control failures.
8. Test authorization with multiple fictional user roles.

## 9. Access Control Security Checklist

| Security Control | Expected Behavior |
|---|---|
| Authentication | Identifies the requesting user |
| Authorization | Verifies permission for each action |
| Resource Ownership | Confirms the user owns or may access the resource |
| Role Validation | Enforces appropriate role permissions |
| Server-Side Checks | Does not rely only on client-side restrictions |
| API Security | Applies authorization to API endpoints |
| Least Privilege | Grants only necessary permissions |
| Error Handling | Prevents unauthorized data disclosure |

## 10. Student Practical Worksheet

| Field | Observation |
|---|---|
| Training Application | |
| User Role | |
| Resource Type | |
| Request Endpoint | |
| HTTP Method | |
| Object Reference | |
| Expected Permission | |
| Actual Lab Behavior | |
| Access Control Category | |
| Vulnerability Confirmed in Lab | |
| Evidence | |
| Security Impact | |
| Recommended Fix | |

## 11. Assessment Questions

1. What is access control?
2. What is the difference between authentication and authorization?
3. What is IDOR?
4. What is horizontal privilege escalation?
5. What is vertical privilege escalation?
6. Why are unpredictable object identifiers not sufficient protection?
7. Why should authorization be enforced on the server?
8. What is Role-Based Access Control?
9. What does least privilege mean?
10. What information should an IDOR vulnerability report contain?

## 12. Expected Learning Outcome

After completing this lab, students should be able to:

- Explain access control fundamentals.
- Understand horizontal and vertical privilege escalation.
- Identify IDOR scenarios.
- Inspect HTTP requests for object references.
- Understand server-side authorization.
- Prepare a structured access control assessment report.

## 13. Safety Guidelines

- Use only authorized training applications.
- Use fictional accounts and test data.
- Never access real users' records.
- Do not attempt privilege escalation on production systems.
- Do not modify or delete real application data.
- Follow the assigned lab instructions.
- Stop testing if unexpected access or data exposure occurs.

**Lab Status:** Completed after practical exercises, worksheet completion, and assessment review.
