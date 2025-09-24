# Red Team Fundamentals Lab: Web App + Network Adversary Emulation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This repository documents a hands-on, isolated lab project for learning penetration testing fundamentals, HTTP/web technologies, and TCP/IP networking. You'll emulate a red team adversary in a safe, legal environment using vulnerable VMs (DVWA for web app, optional Metasploitable2 for network services) and an attacker machine (Kali/Parrot/REMnux).

**Short Description:**  
Build an isolated lab with a vulnerable web application and target VMs. Perform reconnaissance, scan for services, analyze HTTP interactions, exploit web vulnerabilities (e.g., SQLi, file upload), and capture/analyze TCP/IP traffic with Wireshark. Produce artifacts like scripts, reports, and detection notes for reproducibility.

**Why This Lab?**  
- Gain practical experience with pentesting phases: recon → scan → exploit → post-exploit → report.  
- Master HTTP (methods, headers, cookies, sessions) and common web vulns.  
- Build TCP/IP skills via packet analysis, handshakes, and traffic flows.  
- All in a controlled, ethical setup—perfect for portfolios or certifications (e.g., OSCP prep).

**⚠️ Safety First:** This is for **educational, lab-only use**. Run everything in isolated VMs (e.g., VirtualBox internal network). Do **not** test against production systems without explicit permission. Redact sensitive data before pushing to GitHub.

## Learning Objectives

By the end, you'll master:  
1. Pentesting methodology and report writing.  
2. TCP/IP basics: headers, 3-way handshake, ports, payload inspection.  
3. HTTP/web fundamentals: requests/responses, status codes, headers, cookies, sessions.  
4. Web vulnerabilities: SQLi, file upload, CSRF, basic LFI.  
5. Tools: nmap, curl, Burp Suite, sqlmap, Wireshark, tcpdump.  
6. Ethical exploitation and artifact creation.

## Prerequisites

### Hardware/Software  
- Host machine with 8GB+ RAM (for 3 VMs).  
- Virtualization: VirtualBox (free) or VMware.  
- VMs (pre-built OVAs):  
  - **Attacker VM** (`10.0.0.10`): Kali Linux or Parrot Security (download from official sites).  
  - **Target Web VM** (`10.0.0.20`): DVWA (Damn Vulnerable Web App) on Ubuntu—[OVA here](https://github.com/digininja/DVWA) or build via Docker.  
  - **Optional Target VM** (`10.0.0.30`): Metasploitable2—[download OVA](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/).  
- Network: VirtualBox "Internal Network" named `LabNet` (isolated—no host/internet access).  

### Tools (Install on Attacker VM)  
Run these on your attacker machine:  
```bash
- sudo apt update && sudo apt install -y nmap netcat curl wget tcpdump wireshark sqlmap nikto gobuster python3-pip burpsuite
- pip3 install requests

- Burp Suite Community (free) or OWASP ZAP.
- Metasploit (optional: sudo apt install metasploit-framework).
- See docs/lab-setup.md for full VM import and IP config steps.

# Download wordlists: sudo apt install wordlists (or clone SecLists)
