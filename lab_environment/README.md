# SNIT Bug Bounty Lab Environment Setup

## 1. Introduction

This document explains how to prepare a local environment for practicing bug bounty hunting and web application security testing.

Students will use intentionally vulnerable applications, security testing tools, and virtual machines to perform practical exercises.

The objective is to create an isolated and controlled environment where students can learn safely.

## 2. Lab Environment Requirements

### Hardware Requirements

| Component | Minimum Requirement | Recommended |
|---|---|---|
| Processor | Intel Core i5 / AMD equivalent | Intel Core i7 / AMD equivalent |
| RAM | 8 GB | 16 GB or higher |
| Storage | 50 GB free | 100 GB SSD |
| Virtualization | Supported CPU virtualization | VT-x / AMD-V enabled |
| Internet | Required for initial downloads | Stable broadband connection |

### Software Requirements

- Windows 10/11 or Linux host operating system
- VirtualBox or VMware Workstation
- Kali Linux
- Browser
- Burp Suite Community Edition
- OWASP Juice Shop
- Docker, if using the container-based Juice Shop setup

## 3. Recommended Lab Architecture

The following architecture is recommended for beginner training.

```text
                 Student Laptop
                       |
                Host Operating System
                       |
              Virtualization Software
                       |
                Kali Linux VM
                       |
                 Browser / Burp
                       |
             Isolated Lab Network
                       |
                OWASP Juice Shop
```

Keep intentionally vulnerable applications isolated from public networks and unrelated systems.

## 4. Install Virtualization Software

Choose one virtualization platform.

### Option 1: Oracle VirtualBox

Official download:

https://www.virtualbox.org/wiki/Downloads

Installation steps:

1. Download VirtualBox for your host operating system.
2. Run the installer.
3. Follow the installation wizard.
4. Restart if requested.
5. Open VirtualBox.

### Option 2: VMware Workstation

Official website:

https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion

Installation steps:

1. Download the appropriate installer.
2. Run the installer.
3. Follow the installation instructions.
4. Open VMware Workstation.

Use only one virtualization platform for the introductory lab unless your instructor requires otherwise.

## 5. Install Kali Linux

Official download:

https://www.kali.org/get-kali/

Steps:

1. Download the Kali Linux virtual machine image for your virtualization platform.
2. Import or open the virtual machine.
3. Allocate appropriate CPU and memory resources.
4. Configure the virtual network.
5. Start the virtual machine.
6. Complete the initial setup.

Recommended allocation:

| Resource | Recommended |
|---|---|
| CPU | 2 cores |
| RAM | 4 GB |
| Storage | 40 GB |
| Network | NAT for updates; isolated network for local lab exercises |

Do not expose vulnerable lab services to the public internet.

## 6. Update Kali Linux

Open the Kali terminal and run:

```bash
sudo apt update
```

Upgrade installed packages:

```bash
sudo apt full-upgrade -y
```

Verify the operating system:

```bash
cat /etc/os-release
```

## 7. Install Required Security Tools

Install the core tools used throughout the course:

```bash
sudo apt update
sudo apt install -y nmap gobuster seclists whatweb curl dnsutils whois openssl
```

Check the installed tools:

```bash
nmap --version
gobuster version
whatweb --version
curl --version
dig -v
whois --version
openssl version
```

Install Subfinder separately using its official installation documentation:

https://github.com/projectdiscovery/subfinder

Install Feroxbuster using its official documentation:

https://github.com/epi052/feroxbuster

Burp Suite Community Edition:

https://portswigger.net/burp/communitydownload

OWASP ZAP:

https://www.zaproxy.org/download/

## 8. Set Up OWASP Juice Shop

OWASP Juice Shop is an intentionally vulnerable web application designed for security training.

Official project:

https://owasp.org/www-project-juice-shop/

### Option: Run Juice Shop Using Docker

Install Docker using the official instructions:

https://docs.docker.com/engine/install/

Start Juice Shop:

```bash
docker run --rm -d --name juice-shop -p 127.0.0.1:3000:3000 bkimminich/juice-shop
```

Open the application in your browser:

```text
http://127.0.0.1:3000
```

Check whether the container is running:

```bash
docker ps
```

Stop the application:

```bash
docker stop juice-shop
```

**Network safety:** The example binds the application to localhost, making it accessible from the same machine rather than exposing it on every network interface. If students use separate VMs, configure a dedicated isolated lab network and restrict access accordingly.

## 9. Access PortSwigger Web Security Academy

PortSwigger Academy provides guided web application security exercises.

Official website:

https://portswigger.net/web-security

Steps:

1. Open the website.
2. Create an account if required.
3. Select a vulnerability category.
4. Read the exercise instructions.
5. Launch the assigned training lab.
6. Complete the exercise.
7. Record your observations.

Available learning categories include:

- SQL Injection
- Cross-Site Scripting
- Authentication
- Access Control
- Server-Side Request Forgery
- File Upload Vulnerabilities
- API Testing

Follow the Academy's individual exercise instructions.

## 10. Configure Burp Suite

1. Open Burp Suite Community Edition.
2. Create a temporary project.
3. Select the default configuration.
4. Start Burp's built-in browser.
5. Open your local Juice Shop application.
6. Navigate through the application.
7. Review HTTP traffic under Proxy → HTTP history.

Observe:

- Request methods
- URLs
- Parameters
- Request headers
- Response headers
- Status codes
- Cookies

Use only lab accounts and fictional data.

## 11. Verify Your Lab Environment

Complete the following checks:

| Component | Verification | Status |
|---|---|---|
| VirtualBox / VMware | Application opens | |
| Kali Linux | VM boots successfully | |
| Kali Networking | Lab network configured | |
| Nmap | Version command works | |
| Gobuster | Version command works | |
| WhatWeb | Version command works | |
| Burp Suite | Opens successfully | |
| OWASP Juice Shop | Local page loads | |
| Browser | Can access lab application | |
| Docker | Container starts and stops | |

## 12. Troubleshooting

### Problem 1: Virtual Machine Does Not Start

Possible causes:

- Virtualization disabled in BIOS/UEFI.
- Insufficient memory.
- Hypervisor configuration conflicts.

Check virtualization settings and the platform's troubleshooting documentation.

### Problem 2: Juice Shop Does Not Open

Check the Docker container:

```bash
docker ps
```

View container logs:

```bash
docker logs juice-shop
```

Check whether the local port is listening:

```bash
ss -lntp | grep 3000
```

### Problem 3: Security Tool Not Found

Update package information:

```bash
sudo apt update
```

Check whether the package is installed:

```bash
which nmap
which gobuster
which whatweb
```

Install the missing package using the appropriate package manager or official installation instructions.

### Problem 4: Browser Cannot Access Juice Shop

Verify:

- The Docker container is running.
- Port 3000 is mapped correctly.
- The browser is running on the same host as the localhost-bound service.
- The URL is correct.

## 13. Lab Safety Guidelines

- Use intentionally vulnerable applications for practice.
- Keep vulnerable services isolated.
- Do not expose Juice Shop directly to the internet.
- Use test accounts and fictional information.
- Do not scan unrelated devices.
- Do not test public websites without explicit authorization.
- Follow instructor instructions.
- Stop the lab service when practical exercises are complete.

## 14. Expected Learning Outcome

After completing this setup, students should be able to:

- Configure a cybersecurity virtual lab.
- Install and update Kali Linux.
- Install basic bug bounty tools.
- Run OWASP Juice Shop locally.
- Access PortSwigger Academy exercises.
- Inspect web traffic using Burp Suite.
- Perform practical training in a controlled environment.

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
