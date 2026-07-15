TECHNICAL AUDIT REPORT: BASIC NETWORK SCANNING & RECONNAISSANCE
Document Reference: OIBSIP-SEC-TASK1-01
Author: Animesh Kumar
Assigned Reviewer: Oasis Infobyte Project Evaluation Board
Classification: Internal Security Review Only
Date: July 2026
1. Executive Summary
This assessment highlights the steps taken during the network discovery and port auditing phase conducted on the local target infrastructure (192.168.1.1). Network visibility and asset identification are foundational requirements for maintaining corporate security. The objective was to discover active network ports, identify software names and version numbers, guess the active operating system, and assess the target's overall surface exposure to external threats. The analysis confirmed the presence of three active $TCP$ services, pointing to a Linux-based platform handling web and secure shell administration traffic.
2. Methodology & Tooling Framework
The audit strictly followed standard industry practices for network security reconnaissance:
•	Utility Engine: Nmap (Network Mapper) Version 7.9X
•	Target Focus: Private Internal Network Infrastructure Asset (192.168.1.1)
•	Transport Focus: $TCP$ (Transmission Control Protocol) Stack Connectivity
•	Scanning Technique: Syn-Stealth Architecture, Service Version Interrogation, and System OS Stack Fingerprinting.
3. Detailed Command Execution History
The following commands were run in sequence to safely gather data from the target network:
Command 1: Environment Verification
Bash
nmap --version
•	Purpose: Confirms the utility is installed correctly and checks the built-in library dependencies before launching network traffic.
Command 2: Host Ping Discovery
Bash
nmap -sn 192.168.1.0/24
•	Purpose: Sends standard ICMP echo requests and TCP ACK packets across the network range to discover live hosts while keeping traffic low.
Command 3: Active Service Port Audit
Bash
nmap -sV -O -F 192.168.1.1 -oN nmap_scan_output.txt
•	Purpose: Fast-scans the target system's top ports, queries open applications for version numbers, attempts to detect the host operating system, and writes the output directly to a text log.
4. Analytical Findings & Portfolio Data
The network scan discovered the following detailed open ports and active applications:
Port Identifier	Protocol Type	Connection State	Software Name	Running Version	Functional Role
22	$TCP$	OPEN	OpenSSH	9.2p1 Debian	Secure Administrative Remote Management
80	$TCP$	OPEN	nginx	1.22.1	Unencrypted Hypertext Web Server
443	$TCP$	OPEN	nginx	1.22.1	Encrypted Transport Layer Web Server ($SSL$/$TLS$)
Operating System Fingerprint Details
•	Kernel Signature: Linux 5.0 - 6.6
•	Deployment Reliability Metric: 96% Match Confidence
•	Network Distance: 1 Hop (Local Subnet Router Core)
5. Security Threat Analysis & Exposure Assessment
1.	Exposed Administrative Portal (Port 22 - SSH): Having a remote shell port open to the wider network creates a high-value target for password-cracking tools and brute-force software. If weak passwords are used, an attacker can gain complete control over the system console.
2.	Web Server Footprint Disclosure (Port 80/443): The scan accurately revealed the web server software vendor (nginx) and its exact version number (1.22.1). Sharing specific software version details helps malicious actors search public vulnerability databases for known exploits targeting that exact version.
6. Actionable Defensive Recommendations
•	Enforce SSH Hardening: Move the SSH service from the standard Port 22 to a random, non-standard port (e.g., Port 2222) to avoid automated scans. Disable password logins completely and require secure SSH cryptographic keys instead.
•	Remove Software Version Banners: Adjust the configuration files of your web server software (nginx.conf) by setting server_tokens off;. This stops the system from broadcasting the exact software version number to anonymous scanners.
•	Deploy Local Firewalls: Set up local firewall rules (such as iptables or Windows Defender Firewall) to restrict access to administrative ports like SSH, allowing connections only from trusted management IP addresses.
7. Professional Conclusion
The targeted network device has a well-defined and relatively small online footprint, but it exposes sensitive infrastructure details, including software versions and administrative options. Implementing the hardening recommendations outlined in this report will significantly improve the system's defenses against unauthorized network tracking and exploit attempts.
8. Academic References
•	Lyon, G. (2009). Nmap Network Scanning: The Official Nmap Project Guide to Network Discovery and Vulnerability Scanning.
•	Center for Internet Security (CIS). (2026). CIS Benchmarks for Hardening Linux Environments and OpenSSH Server Deployments.

