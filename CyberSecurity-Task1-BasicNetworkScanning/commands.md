# Commands Used in Task 1

## 1. Check Nmap Installation

```bash
nmap --version
```

Purpose:
Verify that Nmap is installed correctly.

---

## 2. Find Your IP Address

Windows:

```bash
ipconfig
```

Linux:

```bash
ip addr
```

Purpose:
Identify your system's IP address and subnet.

---

## 3. Ping Scan

```bash
nmap -sn 192.168.1.0/24
```

Purpose:
Discover active hosts without scanning ports.

---

## 4. Basic Port Scan

```bash
nmap 192.168.1.10
```

Purpose:
Identify open TCP ports.

---

## 5. Service Version Detection

```bash
nmap -sV 192.168.1.10
```

Purpose:
Determine versions of services running on open ports.

---

## 6. Operating System Detection

```bash
nmap -O 192.168.1.10
```

Purpose:
Estimate the target operating system.

---

## 7. Aggressive Scan

```bash
nmap -A 192.168.1.10
```

Purpose:
Run OS detection, version detection, default scripts, and traceroute.

---

## 8. Save Scan Results

```bash
nmap -oA output/scan 192.168.1.10
```

Purpose:
Save results in Normal, XML, and Grepable formats.
