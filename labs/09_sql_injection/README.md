# Lab 09: SQL Injection Vulnerability Assessment

## 1. Lab Overview

SQL Injection (SQLi) is a web application vulnerability that occurs when untrusted input is improperly included in database queries.

An attacker may exploit this weakness to access unauthorized information, modify database records, or interfere with application functionality.

In this lab, students will understand SQL Injection concepts, learn how to recognize potential injection points, and practice safe vulnerability assessment using intentionally vulnerable applications.

**Important:** Perform practical testing only in authorized training environments such as OWASP Juice Shop or PortSwigger Web Security Academy.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand SQL Injection vulnerabilities.
- Explain how applications interact with databases.
- Identify potential SQL injection entry points.
- Understand different types of SQL Injection.
- Inspect HTTP requests using Burp Suite.
- Recognize indicators of SQL injection.
- Understand parameterized queries and secure coding practices.
- Prepare a SQL Injection vulnerability report.

## 3. Topics Covered

1. Introduction to SQL Injection
2. How web applications communicate with databases
3. SQL query fundamentals
4. SQL Injection vulnerability causes
5. Authentication-related SQL Injection concepts
6. Error-based SQL Injection
7. Union-based SQL Injection concepts
8. Blind SQL Injection concepts
9. Input validation and parameterized queries
10. SQL Injection reporting and remediation

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Burp Suite Community | HTTP request and response analysis |
| OWASP Juice Shop | Intentionally vulnerable application |
| PortSwigger Academy | Guided SQL Injection exercises |
| Browser Developer Tools | Inspect application behavior |
| curl | HTTP request inspection |

## 5. Understanding SQL Injection

Web applications often retrieve information from databases using SQL queries.

For example, an application might use a query conceptually similar to:

```sql
SELECT * FROM users WHERE username = ?;
```

The application should safely bind user input to the query parameter.

A vulnerability can occur when the application combines untrusted input directly into SQL statements without appropriate protections.

### Potential Impact

- Unauthorized access to records
- Authentication bypass
- Exposure of sensitive information
- Unauthorized modification of data
- Loss of data integrity
- Application availability issues

## 6. Types of SQL Injection

| Type | Description |
|---|---|
| Error-Based SQLi | Uses database error behavior to identify weaknesses. |
| Union-Based SQLi | Combines results from multiple database queries. |
| Boolean-Based Blind SQLi | Infers information from differences in application responses. |
| Time-Based Blind SQLi | Uses response timing to infer database behavior. |
| Second-Order SQLi | Malicious input is stored and causes an issue when used later in a query. |

## 7. Practical Exercises

### Exercise 1: Understand the Application and Database Flow

1. Open your assigned training application.
2. Identify a feature that retrieves information from a database.
3. Observe how the application sends requests.
4. Open Burp Suite and review the HTTP history.
5. Identify parameters that may be processed by the application.

Examples of common input locations:

- Login forms
- Search fields
- Product filters
- URL parameters
- Form submissions

**Task:** Draw a simple diagram showing the browser, web application, and database interaction.

### Exercise 2: Inspect HTTP Requests Using Burp Suite

1. Start Burp Suite Community Edition.
2. Open its built-in browser.
3. Navigate to your authorized training application.
4. Use a normal search or login feature.
5. Review the request in Proxy HTTP history.
6. Identify the HTTP method, URL, parameters, and response.

Record:

- Request endpoint
- Parameter names
- Parameter locations
- Response status
- Response behavior

Do not test real accounts or production databases.

### Exercise 3: Explore SQL Injection Concepts

Use the dedicated SQL Injection learning exercises in PortSwigger Web Security Academy.

Study:

- How unsafe query construction works.
- Why input handling matters.
- How database errors can reveal implementation details.
- How application responses may indicate unexpected query behavior.

Complete only the exercises provided by the training platform.

**Task:** Explain how unsafe input handling can affect database queries.

### Exercise 4: Identify Potential Injection Points

Using your authorized training application:

1. Review its search functionality.
2. Review its login functionality.
3. Review filters and query parameters.
4. Identify which values are sent to the server.
5. Document where database-backed input processing may occur.

A potential injection point is not automatically a confirmed vulnerability.

### Exercise 5: Understand Secure SQL Query Handling

Study the following secure coding example in Python using parameterized queries:

```python
import sqlite3

connection = sqlite3.connect("training.db")
cursor = connection.cursor()

username = input("Enter username: ")

cursor.execute(
    "SELECT * FROM users WHERE username = ?",
    (username,)
)

results = cursor.fetchall()

for record in results:
    print(record)

connection.close()
```

**Observe:**

- The SQL query uses a placeholder.
- User input is supplied separately.
- The database driver handles parameter binding.
- User input is not directly concatenated into the SQL statement.

### Exercise 6: Prepare a SQL Injection Assessment Report

Create a report for a confirmed issue in the assigned training application.

Include:

- Finding title
- Affected endpoint
- Vulnerability category
- Description
- Evidence from the authorized lab
- Security impact
- Severity
- Recommended remediation
- Retest result

Do not include sensitive information or real user data.

## 8. SQL Injection Prevention Checklist

| Security Control | Recommendation |
|---|---|
| Parameterized Queries | Use prepared statements and bound parameters. |
| Input Validation | Validate input according to expected data types and formats. |
| Least Privilege | Give database accounts only the permissions they require. |
| Error Handling | Avoid exposing database errors to end users. |
| Secure ORM Usage | Use ORM features safely and avoid unsafe query construction. |
| Security Testing | Perform regular authorized application security assessments. |
| Database Updates | Keep database software and drivers updated. |

## 9. Student Practical Worksheet

| Field | Observation |
|---|---|
| Training Application | |
| Database-Backed Feature | |
| HTTP Endpoint | |
| HTTP Method | |
| Potential Input Parameters | |
| Request Type | |
| Response Behavior | |
| SQL Injection Category Studied | |
| Vulnerability Confirmed in Lab | |
| Evidence | |
| Security Impact | |
| Recommended Fix | |

## 10. Assessment Questions

1. What is SQL Injection?
2. How does a web application communicate with a database?
3. What causes SQL Injection vulnerabilities?
4. What is the difference between error-based and blind SQL Injection?
5. What is union-based SQL Injection?
6. What is a parameterized query?
7. Why should applications avoid directly concatenating user input into SQL queries?
8. What is the principle of least privilege?
9. Why should database error messages not be exposed to users?
10. What information should a SQL Injection vulnerability report contain?

## 11. Expected Learning Outcome

After completing this lab, students should be able to:

- Explain SQL Injection fundamentals.
- Identify potential database-backed input points.
- Inspect HTTP requests using Burp Suite.
- Understand major SQL Injection categories.
- Explain secure query construction.
- Prepare a structured SQL Injection assessment report.

## 12. Safety Guidelines

- Use only authorized training applications.
- Never test public websites without explicit permission.
- Do not access, extract, modify, or delete real user data.
- Do not test production databases.
- Use lab-provided accounts and fictional data.
- Follow training platform instructions and scope restrictions.
- Stop testing if unexpected data or system impact occurs.

**Lab Status:** Completed after practical exercises, worksheet completion, and assessment review.
