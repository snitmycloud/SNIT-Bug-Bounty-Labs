# Lab 06: Directory and File Discovery

## 1. Lab Overview

Directory and file discovery is a web application testing technique used to identify publicly accessible directories, files, endpoints, and resources.

Security testers use this process to understand the application's exposed attack surface and identify potentially sensitive resources that should not be publicly accessible.

In this lab, students will practice directory discovery using an intentionally vulnerable application or an authorized testing environment.

**Important:** Perform discovery only on systems explicitly authorized for testing. Follow the target's scope, rate limits, and rules of engagement.

## 2. Learning Objectives

By the end of this lab, students will be able to:

- Understand directory and file discovery.
- Identify common web application paths.
- Use Gobuster and Feroxbuster for controlled discovery.
- Understand HTTP status codes returned during discovery.
- Identify potentially exposed files and directories.
- Document findings and assess their security relevance.

## 3. Topics Covered

1. Directory and file discovery fundamentals
2. Common web application directories
3. Wordlists and their purpose
4. Gobuster fundamentals
5. Feroxbuster fundamentals
6. HTTP response status codes
7. Response size and false positives
8. Discovery result analysis
9. Security reporting

## 4. Tools Required

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Gobuster | Directory and file discovery |
| Feroxbuster | Recursive content discovery |
| SecLists | Wordlists for security testing |
| Browser | Manual verification |
| curl | HTTP response inspection |
| Burp Suite Community | Request and response analysis |

## 5. Understanding Directory Discovery

Web applications commonly contain paths such as:

```text
/
 /login
 /admin
 /uploads
 /images
 /assets
 /api
 /docs
 /robots.txt
 /sitemap.xml
```

Some paths may be intentionally public. Others may expose information that should be restricted.

Finding a path does not automatically mean a vulnerability exists. The security impact depends on what the resource exposes and whether access is authorized.

## 6. Practical Exercises

### Exercise 1: Check Tool Availability

Check whether Gobuster is installed:

```bash
gobuster version
```

Check Feroxbuster:

```bash
feroxbuster --version
```

If required, install the tools on Kali Linux:

```bash
sudo apt update
sudo apt install gobuster feroxbuster seclists -y
```

### Exercise 2: Understand Wordlists

Wordlists contain possible directory and file names used during discovery.

A common SecLists directory is:

```bash
/usr/share/seclists/Discovery/Web-Content/
```

List available wordlists:

```bash
ls /usr/share/seclists/Discovery/Web-Content/
```

Choose a small wordlist for the introductory lab. Avoid large wordlists until you understand the impact of request volume.

### Exercise 3: Basic Directory Discovery with Gobuster

Use only your authorized lab application.

```bash
gobuster dir -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

Observe:

- Discovered paths
- HTTP status codes
- Response sizes
- Redirect behavior
- Errors and timeouts

Save the output to a file:

```bash
gobuster dir -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt -o gobuster_results.txt
```

### Exercise 4: Filter Results by Status Code

Gobuster can display selected HTTP response status codes.

Example:

```bash
gobuster dir -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt -s 200,204,301,302,307,401,403
```

Understand these common responses:

| Status Code | Meaning |
|---|---|
| 200 | OK |
| 204 | No Content |
| 301 | Permanent Redirect |
| 302 | Temporary Redirect |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

A `403 Forbidden` response indicates that access is denied. Do not attempt to bypass it as part of this lab.

### Exercise 5: Directory Discovery with Feroxbuster

Run a controlled discovery scan against your authorized lab:

```bash
feroxbuster -u http://<AUTHORIZED-LAB-TARGET> -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

Observe:

- Discovered paths
- Response codes
- Content lengths
- Redirects
- Whether additional paths are discovered recursively

For this introductory exercise, use a small wordlist and avoid aggressive settings.

### Exercise 6: Manually Verify Discovered Paths

Take a path discovered during the exercise and inspect it using curl:

```bash
curl -I http://<AUTHORIZED-LAB-TARGET>/<DISCOVERED-PATH>
```

You can also open the path in your browser.

Record:

- Whether the resource exists
- Whether authentication is required
- Whether access is denied
- Whether the resource contains expected public content

Do not download private files or access data belonging to other users.

## 7. Understanding False Positives

Directory discovery tools can report misleading results.

Common reasons include:

- Custom 404 pages returning HTTP 200.
- Multiple paths returning identical response sizes.
- Redirects to the same login page.
- Dynamic application responses.
- WAF or CDN-generated responses.

Always manually verify interesting results before treating them as findings.

## 8. Student Practical Worksheet

| Field | Observation |
|---|---|
| Target URL | |
| Tool Used | |
| Wordlist Used | |
| Number of Discovered Paths | |
| HTTP 200 Responses | |
| HTTP 301/302 Responses | |
| HTTP 401 Responses | |
| HTTP 403 Responses | |
| Interesting Public Resources | |
| False Positives Identified | |
| Evidence Collected | |
| Scope Verified | |

## 9. Assessment Questions

1. What is directory and file discovery?
2. What is a wordlist?
3. What is the purpose of Gobuster?
4. What is the difference between Gobuster and Feroxbuster?
5. What does HTTP status code 403 indicate?
6. Why should discovered paths be manually verified?
7. What is a false positive in directory discovery?
8. Why should testers use controlled request rates?
9. Does finding an `/admin` directory automatically mean a vulnerability exists?
10. Why must a discovered resource be checked against the program scope?

## 10. Expected Learning Outcome

After completing this lab, students should be able to:

- Perform basic directory and file discovery.
- Understand common HTTP response codes.
- Use Gobuster and Feroxbuster in a controlled environment.
- Identify false positives.
- Verify discovered resources safely.
- Document directory discovery results.

## 11. Safety Guidelines

- Use only authorized lab targets.
- Follow program scope and request-rate limits.
- Do not access private or sensitive files.
- Do not attempt authentication bypass.
- Do not bypass access restrictions.
- Stop testing if the application becomes unstable.
- Document only evidence necessary to demonstrate an issue.

**Lab Status:** Completed after exercises and worksheet review.
