# Task 1: Basic Network Scanning with Nmap

## Module Overview

This sub-directory houses the full engineering implementation, operational commands, and security findings for Task 1 of the Oasis Infobyte Cyber Security Internship. The core goal of this project module is to safely perform network infrastructure discovery, determine port statuses, profile running application services, and run OS fingerprinting via Nmap.

---

## Sub-directory Structure

```text
CyberSecurity-Task1-BasicNetworkScanning/
│
├── README.md               <-- This technical roadmap file
├── task1_report.md         <-- PDF-ready professional audit report
├── nmap_scan_output.txt    <-- Raw exported Nmap console output log


```

---

## Quick Start Execution Sequence

To replicate the exact technical workflow demonstrated in this module, execute the following commands in sequence on an administrative console:

```bash
# 1. Verify utility visibility within system environment
nmap --version

# 2. Map local loopback/gateway to establish discovery metrics
nmap -sn 192.168.1.0/24

# 3. Perform basic fast port profiling
nmap 192.168.1.1

# 4. Trigger advanced service version parsing and system stack interrogation
nmap -sV -O -F 192.168.1.1 -oN nmap_scan_output.txt

```

---

## Summary of Findings

* **Target Evaluated:** 192.168.1.1
* **Active Open Connections Found:** Port 22 ($TCP$), Port 80 ($TCP$), Port 443 ($TCP$)
* **Operational Network Platform:** Linux Kernel 5.X / 6.X
* **Identified Vulnerability Exposure:** The presence of an open SSH administration service (Port 22) requires strict access control lists ($ACLs$) and key-based authentication to prevent remote unauthorized access attempts.
