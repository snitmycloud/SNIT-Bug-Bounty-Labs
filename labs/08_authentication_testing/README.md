# Lab 08: Authentication and Session Management Testing

## 1. Lab Overview

Authentication verifies a user's identity, while session management maintains the user's authenticated state across application requests.

Weak authentication and session management can allow unauthorized users to access accounts, misuse sessions, or compromise sensitive information.

In this lab, students will learn how to assess authentication mechanisms, password security, session cookies, logout behavior, and multi-factor authentication using intentionally vulnerable training applications.

**Important:** Perform all practical exercises only in authorized lab environments using test accounts.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand authentication and authorization.
- Identify common authentication weaknesses.
- Understand password security requirements.
- Inspect session cookies.
- Understand session expiration and logout behavior.
- Recognize multi-factor authentication weaknesses.
- Document authentication-related security findings.

## 3. Topics Covered

1. Authentication fundamentals
2. Authentication versus authorization
3. Password security
4. Brute-force protection awareness
5. Multi-factor authentication (MFA)
6. Session management
7. Session cookies
8. Session expiration
9. Secure logout
10. Password reset security

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Burp Suite Community | HTTP traffic inspection |
| Browser Developer Tools | Cookie and session inspection |
| OWASP Juice Shop | Vulnerable training application |
| PortSwigger Academy | Guided authentication labs |

## 5. Authentication Fundamentals

Authentication confirms who a user is.

Common authentication methods include:

- Username and password
- One-time passwords (OTP)
- Multi-factor authentication
- Security keys
- Certificate-based authentication
- Biometric authentication

### Authentication vs Authorization

| Authentication | Authorization |
|---|---|
| Verifies user identity | Determines permitted actions |
| Answers: Who are you? | Answers: What can you access? |
| Example: Login | Example: Admin-only access |

## 6. Practical Exercises

### Exercise 1: Analyze the Login Process

Use a test account in your authorized lab application.

1. Open the lab application.
2. Navigate to the login page.
3. Enter the assigned test credentials.
4. Observe the login request using Burp Suite.
5. Review the HTTP response.
6. Identify how the application indicates successful or unsuccessful login.

Record:

- Login endpoint
- HTTP method
- Response status
- Authentication-related cookies
- Whether HTTPS is used

Do not record actual passwords or reusable session tokens.

### Exercise 2: Password Security Assessment

Review the password requirements in your training application.

Check whether the application provides:

- Minimum password length
- Protection against commonly used passwords
- Secure password reset
- Appropriate error messages
- Rate limiting or other protections against repeated login attempts

**Task:** Prepare recommendations for improving password security.

Do not conduct password guessing against real accounts.

### Exercise 3: Inspect Session Cookies

After logging into your test account:

1. Open browser Developer Tools.
2. Navigate to the Application or Storage tab.
3. Select Cookies.
4. Review the session-related cookies.
5. Inspect their security attributes.

Important cookie attributes:

| Attribute | Purpose |
|---|---|
| Secure | Sends the cookie only over secure HTTPS connections. |
| HttpOnly | Prevents ordinary JavaScript access to the cookie. |
| SameSite | Controls when cookies are sent with cross-site requests. |
| Expires / Max-Age | Defines cookie lifetime. |

**Task:** Record which attributes are configured in your lab application.

Never share session cookie values in screenshots or reports.

### Exercise 4: Session Expiration Awareness

Study how the application handles session expiration.

1. Log in using your test account.
2. Review the application's documented session timeout behavior.
3. Observe what happens after the configured timeout.
4. Check whether protected pages require authentication again.

**Task:** Document whether session expiration works as expected.

Do not attempt to reuse another person's session.

### Exercise 5: Secure Logout Testing

1. Log in to the training application.
2. Navigate to the logout option.
3. Log out.
4. Attempt to access a protected page using the browser.
5. Observe whether the application requires authentication again.

**Expected behavior:** The application should invalidate the authenticated session and prevent further access to protected resources through that session.

### Exercise 6: Multi-Factor Authentication Awareness

Study how MFA improves account security.

Understand:

- OTP-based authentication
- Authenticator applications
- Push notifications
- Hardware security keys
- Recovery codes

Review the MFA implementation in your assigned training environment.

**Task:** Document how MFA protects accounts and identify common implementation risks from the learning materials.

### Exercise 7: Password Reset Security

Review the password reset process in your training application.

Check:

- Whether reset links use HTTPS.
- Whether reset tokens have limited validity.
- Whether reset tokens are single-use.
- Whether users receive appropriate reset notifications.
- Whether the application avoids revealing whether an account exists.

Use only assigned test accounts and lab-provided reset functionality.

## 7. Authentication Security Checklist

| Security Control | Expected Behavior |
|---|---|
| Password Policy | Enforces appropriate password requirements |
| Login Protection | Protects against repeated automated attempts |
| MFA | Supports additional authentication factors |
| Secure Cookies | Uses appropriate cookie attributes |
| Session Timeout | Expires sessions according to policy |
| Logout | Invalidates the active session |
| Password Reset | Uses secure, time-limited reset tokens |
| HTTPS | Protects credentials and session traffic |

## 8. Student Practical Worksheet

| Field | Observation |
|---|---|
| Lab Application | |
| Login Endpoint | |
| HTTP Method | |
| HTTPS Enabled | |
| Login Response | |
| Secure Cookie Attribute | |
| HttpOnly Cookie Attribute | |
| SameSite Attribute | |
| Session Timeout Behavior | |
| Logout Behavior | |
| MFA Available | |
| Password Reset Security | |
| Findings | |
| Recommendations | |

## 9. Assessment Questions

1. What is authentication?
2. What is the difference between authentication and authorization?
3. Why is MFA important?
4. What is session management?
5. What is the purpose of the Secure cookie attribute?
6. What does HttpOnly protect against?
7. What is the purpose of SameSite?
8. Why should sessions expire?
9. What should happen after a successful logout?
10. What makes a password reset process secure?

## 10. Expected Learning Outcome

After completing this lab, students should be able to:

- Explain authentication and session management.
- Inspect login requests and responses.
- Review session cookie attributes.
- Understand password and MFA security.
- Evaluate session expiration and logout behavior.
- Prepare an authentication security assessment.

## 11. Safety Guidelines

- Use only authorized lab applications.
- Use test accounts and fictional credentials.
- Never attempt to access another person's account.
- Do not conduct password guessing against public systems.
- Do not collect or share session tokens.
- Follow the training platform's rules.
- Document only necessary lab evidence.

**Lab Status:** Completed after practical exercises, worksheet completion, and assessment review.
