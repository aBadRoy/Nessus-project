<div align="center">
  <img src="https://img.shields.io/badge/Nessus-Professional-blue?style=for-the-badge&logo=tenable" alt="Nessus">
  <img src="https://img.shields.io/badge/Metasploit-Exploit-red?style=for-the-badge&logo=metasploit" alt="Metasploit">
  <img src="https://img.shields.io/badge/Security-Ethical%20Hacking-brightgreen?style=for-the-badge" alt="Ethical Hacking">
  <br>
  <img src="https://img.shields.io/github/last-commit/aBadRoy/Nessus-project?style=flat-square" alt="Last Commit">
  <img src="https://img.shields.io/github/repo-size/aBadRoy/Nessus-project?style=flat-square" alt="Repo Size">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License">
</div>

<h1 align="center">Nessus Home Lab & Exploitation Framework</h1>

<p align="center">
  <strong>A hands-on cybersecurity home lab demonstrating vulnerability scanning with Tenable Nessus and exploitation with Metasploit.</strong>
</p>

<p align="center">
  Complete walkthrough of a penetration test lifecycle — from network reconnaissance and vulnerability detection to successful exploitation — all within a controlled home lab environment.
</p>

---

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Lab Topology](#lab-topology)
- [Walkthrough](#walkthrough)
  - [1. Basic Network Scan](#1-basic-network-scan)
  - [2. Configure Target](#2-configure-target)
  - [3. Scan Results](#3-scan-results)
  - [4. Vulnerability Identification](#4-vulnerability-identification)
  - [5. Exploitation with Metasploit](#5-exploitation-with-metasploit)
  - [6. Access Granted](#6-access-granted)
- [Technologies Used](#technologies-used)
- [Disclaimer](#disclaimer)
- [License](#license)

---

## Overview

This project demonstrates a full penetration testing workflow:

1. **Scan** — Use Nessus to perform a basic network scan against a target machine
2. **Identify** — Discover vulnerabilities (e.g., **ProFTPD 1.3.3c**)
3. **Exploit** — Leverage Metasploit to gain access to the target

> **Target:** Metasploitable 2 (vulnerable by design)  
> **Attacker:** Kali Linux with Nessus & Metasploit installed

---

## Prerequisites

| Tool | Purpose |
|------|---------|
| [Nessus](https://www.tenable.com/products/nessus) | Vulnerability scanning engine |
| [Metasploit](https://www.metasploit.com/) | Exploitation framework |
| [Kali Linux](https://www.kali.org/) | Attacker OS |
| [Metasploitable 2](https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/) | Vulnerable target (VM) |

---

## Lab Topology

```
┌─────────────────────┐          ┌──────────────────────┐
│   Attacker Machine  │          │    Target Machine     │
│   (Kali Linux)      │◄────────►│  (Metasploitable 2)   │
│                     │  Network │                       │
│  - Nessus           │          │  - ProFTPD 1.3.3c     │
│  - Metasploit       │          │  - Multiple Vulns     │
└─────────────────────┘          └──────────────────────┘
```

---

## Walkthrough

### 1. Basic Network Scan

Launch Nessus and configure a **Basic Network Scan** to discover live hosts.

![Basic Network Scan](https://github.com/aBadRoy/Nessus-project/assets/93693542/725c799b-36fd-4318-b915-9787331d49f0)

### 2. Configure Target

Enter the target machine's IP address.

![Target Configuration](https://github.com/aBadRoy/Nessus-project/assets/93693542/0b7ceb2d-df6a-4569-ba52-5668381c03b3)

### 3. Scan Results

The scan completes and reveals open ports and services on the target (Metasploitable 2).

![Scan Results](https://github.com/aBadRoy/Nessus-project/assets/93693542/69d14d81-c593-4d75-ba90-8f6d98cff048)

### 4. Vulnerability Identification

Nessus flags **ProFTPD 1.3.3c** as a critical vulnerability.

![Vulnerability 1](https://github.com/aBadRoy/Nessus-project/assets/93693542/b72b6e1b-f434-4579-9e7d-a9fc311d289f)

![Vulnerability 2](https://github.com/aBadRoy/Nessus-project/assets/93693542/f648df05-f48e-4d4c-b674-237b7e2386b7)

### 5. Exploitation with Metasploit

Launch Metasploit and configure the exploit module for ProFTPD 1.3.3c.

![Metasploit 1](https://github.com/aBadRoy/Nessus-project/assets/93693542/a7df4956-164e-4e9e-9b50-8093e1b33f27)

![Metasploit 2](https://github.com/aBadRoy/Nessus-project/assets/93693542/715c806f-2945-485e-b237-a4370b73cd07)

Set the reverse shell payload.

![Payload Setup](https://github.com/aBadRoy/Nessus-project/assets/93693542/65851afe-d2d7-4f86-905f-e302d79060b0)

### 6. Access Granted

The exploit succeeds — shell access to the target machine obtained.

![Access Granted](https://github.com/aBadRoy/Nessus-project/assets/93693542/be1f8a02-290a-4393-8479-69cacb63dfad)

---

## Technologies Used

- [Tenable Nessus](https://www.tenable.com/products/nessus) — Vulnerability assessment
- [Metasploit Framework](https://www.metasploit.com/) — Exploitation
- [Kali Linux](https://www.kali.org/) — Penetration testing distribution
- [Metasploitable 2](https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/) — Vulnerable target

---

## Disclaimer

> **IMPORTANT**: This project is for **educational purposes only** in **controlled environments**.  
> Only use these techniques on systems you **own** or have **explicit written permission** to test.  
> Unauthorized access to computer systems is illegal. The author is not responsible for misuse.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
