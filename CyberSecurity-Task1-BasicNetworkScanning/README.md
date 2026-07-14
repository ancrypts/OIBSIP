# Task 1 – Basic Network Scanning

## Objective

The objective of this task is to learn how to perform basic network scanning using Nmap. The task focuses on identifying active hosts, open ports, running services, service versions, and operating system information on a target machine.

---

## Tools Used

- Nmap
- Windows Command Prompt / PowerShell (or Kali Linux Terminal)
- Git
- GitHub

---

## Prerequisites

- Nmap installed
- Permission to scan the target system
- Internet connection (only if required)

---

## Commands Used

### Discover Live Hosts

```bash
nmap -sn <target>
```

### Basic Port Scan

```bash
nmap <target>
```

### Service Version Detection

```bash
nmap -sV <target>
```

### Operating System Detection

```bash
nmap -O <target>
```

### Aggressive Scan

```bash
nmap -A <target>
```

### Save Results

```bash
nmap -oA output/scan <target>
```

---

## Output Files

- scan.txt
- scan.xml
- scan.gnmap

---

## Screenshots

- Nmap Installation
- IP Address Identification
- Ping Scan
- Basic Scan
- Service Version Scan
- OS Detection
- Aggressive Scan
- Saved Output Files

---

## Learning Outcomes

- Learned how to identify live hosts.
- Learned how to detect open ports.
- Learned how to identify running services.
- Learned the basics of OS detection.
- Learned how to save scan results for future analysis.

---

## Conclusion

This task provided practical experience with Nmap and demonstrated how network reconnaissance is performed as the first phase of a security assessment.
