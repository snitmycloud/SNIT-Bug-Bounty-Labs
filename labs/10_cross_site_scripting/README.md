# Lab 10: Cross-Site Scripting (XSS) Vulnerability Assessment

## 1. Lab Overview

Cross-Site Scripting (XSS) is a web application vulnerability that occurs when an application handles untrusted input or output without appropriate validation and encoding.

An XSS vulnerability may allow untrusted scripts to execute in another user's browser within the security context of the vulnerable application.

In this lab, students will understand XSS types, identify potential injection points, inspect browser behavior, and learn secure coding practices using intentionally vulnerable training applications.

**Important:** Perform practical testing only in authorized environments such as OWASP Juice Shop and PortSwigger Web Security Academy.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand Cross-Site Scripting.
- Identify reflected, stored, and DOM-based XSS.
- Understand how browsers process HTML and JavaScript.
- Identify potential XSS input points.
- Inspect HTTP requests and responses using Burp Suite.
- Understand output encoding and input validation.
- Recommend appropriate XSS prevention controls.
- Prepare an XSS vulnerability assessment report.

## 3. Topics Covered

1. Introduction to XSS
2. How browsers process HTML and JavaScript
3. Reflected XSS
4. Stored XSS
5. DOM-based XSS
6. Input validation
7. Context-aware output encoding
8. Content Security Policy (CSP)
9. XSS assessment using Burp Suite
10. XSS prevention and reporting

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Burp Suite Community | HTTP request and response inspection |
| OWASP Juice Shop | Intentionally vulnerable application |
| PortSwigger Academy | Guided XSS exercises |
| Browser Developer Tools | Inspect DOM and browser behavior |
| Browser | Verify lab application behavior |

## 5. Understanding Cross-Site Scripting

XSS occurs when an application places untrusted data into a web page in a way that allows the browser to interpret it as executable code.

For example, an application may display user-submitted content without safely encoding it for the output context.

### Types of XSS

| Type | Description |
|---|---|
| Reflected XSS | Untrusted input is included in an immediate server response. |
| Stored XSS | Untrusted input is stored and later displayed to users. |
| DOM-Based XSS | Client-side JavaScript processes untrusted data in an unsafe way, changing the DOM. |

## 6. Potential Impact of XSS

Depending on the application and execution context, XSS may result in:

- Unauthorized actions performed in a user's browser
- Exposure of information accessible to the vulnerable page
- Manipulation of page content
- Phishing or misleading content displayed within the application
- Compromise of application user interactions

The actual impact depends on the application's security controls and the user's privileges.

## 7. Practical Exercises

### Exercise 1: Understand Browser Rendering

1. Open your assigned training application.
2. Open browser Developer Tools using `F12`.
3. Select the Elements or Inspector tab.
4. Examine how the page displays user-provided content.
5. Identify where the content appears in the HTML structure.

**Task:** Explain the difference between displaying text as data and interpreting it as HTML.

### Exercise 2: Understand Reflected XSS

1. Open the assigned reflected XSS exercise in PortSwigger Academy.
2. Read the exercise description.
3. Identify the input parameter.
4. Observe how the application responds to the supplied training input.
5. Review the browser output.

**Task:** Explain why reflected input must be safely encoded before being displayed.

### Exercise 3: Understand Stored XSS

1. Open an assigned stored XSS exercise.
2. Identify a feature that stores user-submitted content.
3. Observe how the application displays that content later.
4. Review the relevant browser behavior.

**Task:** Explain why stored XSS can affect users who visit a page after the content has been submitted.

Use only the training platform's supplied exercises and test data.

### Exercise 4: Understand DOM-Based XSS

1. Open the assigned DOM-based XSS exercise.
2. Open browser Developer Tools.
3. Inspect the Elements and Console tabs.
4. Review how client-side JavaScript handles page input.
5. Identify the source of untrusted data and the way the application processes it.

**Task:** Explain the difference between a client-side DOM-based issue and a server-generated reflected response.

### Exercise 5: Inspect HTTP Traffic Using Burp Suite

1. Start Burp Suite Community Edition.
2. Open its built-in browser.
3. Navigate to your authorized training application.
4. Use a normal search or input feature.
5. Open Proxy HTTP history.
6. Review the request and response.
7. Identify where user input is transmitted and returned.

Record:

- Request URL
- HTTP method
- Parameter name
- Input location
- Response behavior
- Relevant HTML context

Do not test public websites without permission.

### Exercise 6: Understand XSS Prevention

Study the following prevention techniques:

**1. Context-Aware Output Encoding**

Encode untrusted data according to where it is placed, such as HTML text, HTML attributes, JavaScript, or URL contexts.

**2. Safe DOM APIs**

Prefer safe text-handling APIs such as:

```javascript
element.textContent = userInput;
```

Avoid treating untrusted input as executable HTML.

**3. Input Validation**

Validate input according to the expected format and business rules.

**4. Content Security Policy**

Use an appropriate Content Security Policy (CSP) to reduce the impact of certain script injection attacks.

**5. Secure Framework Practices**

Use framework features that automatically escape untrusted output. Avoid unsafe rendering features unless the content has been appropriately sanitized.

## 8. XSS Prevention Checklist

| Security Control | Recommendation |
|---|---|
| Output Encoding | Encode untrusted output for its context. |
| Input Validation | Validate data according to expected formats. |
| Safe DOM Handling | Use safe DOM APIs. |
| HTML Sanitization | Sanitize HTML when user-supplied HTML is genuinely required. |
| Content Security Policy | Configure an appropriate CSP. |
| Framework Security | Avoid unsafe rendering functions. |
| Security Testing | Test all relevant input and output locations. |

## 9. Student Practical Worksheet

| Field | Observation |
|---|---|
| Training Application | |
| Input Feature | |
| Input Parameter | |
| XSS Category Studied | |
| Input Location | |
| Output Location | |
| Browser Behavior | |
| HTTP Response Behavior | |
| Vulnerability Confirmed in Lab | |
| Evidence | |
| Security Impact | |
| Recommended Fix | |

## 10. Assessment Questions

1. What is Cross-Site Scripting?
2. What are the three major types of XSS?
3. What is the difference between reflected and stored XSS?
4. What is DOM-based XSS?
5. Why is output encoding important?
6. What is context-aware encoding?
7. What is the purpose of Content Security Policy?
8. Why should untrusted input not be assigned to unsafe HTML rendering functions?
9. What is the difference between input validation and output encoding?
10. What information should an XSS vulnerability report contain?

## 11. Expected Learning Outcome

After completing this lab, students should be able to:

- Explain reflected, stored, and DOM-based XSS.
- Identify potential XSS input and output locations.
- Inspect browser behavior and HTTP traffic.
- Understand secure DOM handling.
- Explain output encoding and CSP.
- Prepare a structured XSS assessment report.

## 12. Safety Guidelines

- Use only authorized training applications.
- Do not test public websites without explicit permission.
- Never inject scripts into real users' browsers.
- Do not collect credentials, cookies, or personal information.
- Use fictional data and training accounts.
- Follow the assigned platform's instructions.
- Stop testing if unexpected impact occurs.

**Lab Status:** Completed after practical exercises, worksheet completion, and assessment review.
