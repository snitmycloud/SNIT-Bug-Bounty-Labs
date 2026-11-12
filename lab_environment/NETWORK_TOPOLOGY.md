# SNIT Bug Bounty Lab Network Topology

## 1. Introduction

This document describes the recommended network architecture for the SNIT Bug Bounty Hunting and Web Application Security Lab.

The objective is to provide a controlled environment where students can practice reconnaissance, web application testing, HTTP traffic analysis, and vulnerability assessment without affecting unrelated systems.

## 2. Lab Network Architecture

The recommended architecture contains:

- Host Operating System
- Kali Linux Virtual Machine
- OWASP Juice Shop
- Browser
- Burp Suite Community Edition
- Isolated Virtual Network

### Network Diagram

```text
                 Student Laptop
                       |
                       |
               Host Operating System
                       |
                Virtualization Platform
                       |
             ---------------------------
             |                         |
             |                         |
         Kali Linux VM           Lab Application
             |                  (OWASP Juice Shop)
             |                         |
         Browser                  Web Application
             |
         Burp Suite
             |
             |
       HTTP Inspection
```

For a separate application VM, connect both VMs to the same dedicated isolated virtual network.

## 3. Recommended Network Configuration

Use a dedicated host-only or internal virtual network for practical testing.

Example addressing plan:

| Component | Example IP Address |
|---|---|
| Lab Network | 192.168.56.0/24 |
| Host-only Adapter | 192.168.56.1 |
| Kali Linux VM | 192.168.56.10 |
| Juice Shop VM | 192.168.56.20 |
| Network Mask | 255.255.255.0 |

These are example addresses. Configure the actual network according to your virtualization platform and verify that the selected subnet does not conflict with an existing network.

## 4. VirtualBox Network Configuration

For a separate Kali VM and Juice Shop VM:

### Step 1: Create a Host-Only Network

1. Open VirtualBox.
2. Open Tools or Network Manager, depending on your version.
3. Select Host-only Networks.
4. Create a new host-only network.
5. Configure the host adapter address.
6. Set the subnet and DHCP settings according to your lab plan.

### Step 2: Configure Kali Linux VM

1. Select the Kali Linux VM.
2. Open Settings.
3. Select Network.
4. Choose an available adapter.
5. Select Host-only Adapter.
6. Choose the host-only network created earlier.
7. Save the settings.

### Step 3: Configure Juice Shop VM

1. Select the Juice Shop VM.
2. Open Settings.
3. Select Network.
4. Configure its adapter to use the same host-only network.
5. Save the settings.

Both VMs should now be connected to the same isolated virtual network.

**Important:** Do not use bridged networking for an intentionally vulnerable application. Do not configure port forwarding that exposes the application to the public internet.

## 5. Network Configuration for a Single-Machine Docker Lab

If Juice Shop runs directly on the same Kali machine using Docker, the separate VM network is unnecessary.

Example:

```text
Kali Linux
    |
    |-- Browser
    |
    |-- Burp Suite
    |
    |-- Docker
           |
           |-- OWASP Juice Shop
               127.0.0.1:3000
```

Run Juice Shop with a localhost-only port binding:

```bash
docker run --rm -d --name juice-shop -p 127.0.0.1:3000:3000 bkimminich/juice-shop
```

Access it using:

```text
http://127.0.0.1:3000
```

This setup is recommended for beginners because it avoids exposing the vulnerable application to other devices.

## 6. Verify Network Connectivity

On Kali Linux, display network interfaces:

```bash
ip addr
```

Display the routing table:

```bash
ip route
```

Check the application VM's reachability, using its actual assigned address:

```bash
ping -c 4 192.168.56.20
```

If ICMP is blocked, that does not necessarily mean the application is unreachable.

Check the web application port:

```bash
curl -I http://192.168.56.20:3000
```

Use this command only when the Juice Shop VM is configured to listen on that address and port.

## 7. Network Communication Flow

### Browser to Juice Shop

The browser sends HTTP requests to the training application.

### Browser to Burp Suite

When the browser is configured to use Burp Suite as its proxy, HTTP traffic can be inspected.

### Burp Suite to Juice Shop

Burp Suite forwards requests to the application and receives its responses.

### Kali Linux to Other Training Resources

Internet access may be needed for software updates and authorized external learning platforms.

Keep this access separate from the intentionally vulnerable application network.

## 8. Recommended Security Boundaries

| Component | Recommended Access |
|---|---|
| Kali Linux VM | Dedicated lab network |
| Juice Shop VM | Dedicated lab network only |
| Host Operating System | Host-only connectivity as required |
| Public Internet | Only for approved updates and learning resources |
| Production Systems | No testing without explicit authorization |

## 9. Network Safety Guidelines

- Use a dedicated isolated virtual network.
- Keep vulnerable applications away from public networks.
- Avoid bridged networking for vulnerable lab VMs.
- Do not expose unnecessary ports.
- Do not configure public port forwarding.
- Use fictional accounts and data.
- Verify network connectivity before testing.
- Stop vulnerable services when exercises are complete.

## 10. Troubleshooting

### Problem 1: Kali Cannot Reach Juice Shop VM

Check:

- Both VMs use the same host-only or internal network.
- IP addresses belong to the configured subnet.
- Network interfaces are enabled.
- The application is running.
- The application is listening on the expected interface and port.

### Problem 2: Juice Shop Is Not Accessible

Check Docker:

```bash
docker ps
```

Check application logs:

```bash
docker logs juice-shop
```

Check listening ports:

```bash
ss -lntp
```

### Problem 3: IP Address Conflict

Check the assigned addresses:

```bash
ip addr
```

Verify that the Kali VM and application VM have unique addresses within the subnet.

## 11. Expected Learning Outcome

After completing this exercise, students should be able to:

- Understand the bug bounty lab network architecture.
- Configure an isolated virtual network.
- Connect Kali Linux to a training application.
- Verify basic network connectivity.
- Understand the role of Burp Suite in HTTP traffic inspection.
- Apply basic network isolation and safety principles.

## 12. Final Note

A properly isolated lab environment is essential for safe cybersecurity training.

All practical exercises must remain within the assigned training environment or explicitly authorized scope.

**SNIT Training Institute | Bug Bounty Hunting & Web Application Security Labs**
