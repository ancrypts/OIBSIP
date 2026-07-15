# Task 5: Web Application Vulnerability Scanning

## Module Overview

This sub-directory contains the technical documentation, security assessment methodology, and vulnerability analysis report for Task 5 of the Oasis Infobyte Cyber Security Internship. The objective of this task is to utilize automated web application scanners (such as OWASP ZAP or Nikto) to identify common security flaws in a web application environment, including configuration weaknesses, outdated software, and common injection vulnerabilities.

---

## Sub-directory Structure

```text
CyberSecurity-Task5-WebAppScanner/
│
├── README.md               <-- This technical roadmap file
├── scan_results.txt        <-- Exported vulnerability report/scan logs
└── vulnerability_report.md <-- Detailed analysis of identified issues

```

---

## Execution Methodology

The following workflow was utilized to evaluate the target web application:

1. **Passive Reconnaissance:** Intercepting traffic to map site architecture and identify active server technologies.
2. **Automated Active Scanning:** Executing a structured vulnerability sweep to test input fields, header configurations, and path discovery.
3. **False Positive Filtering:** Manually verifying findings to ensure the report accurately reflects exploitable risks rather than configuration artifacts.
4. **Reporting & Remediation:** Categorizing findings by risk level (Critical, High, Medium, Low) and drafting remediation strategies.

---

## Targeted Vulnerability Categories

This assessment specifically focused on identifying vulnerabilities within the **OWASP Top 10** framework:

* **A01:2021-Broken Access Control:** Testing for unauthorized access to administrative panels.
* **A05:2021-Security Misconfiguration:** Identifying exposed error pages, default files, and unnecessary HTTP methods.
* **A06:2021-Vulnerable and Outdated Components:** Checking for server-side libraries or CMS versions with known CVEs.

---

## Quick Reference Tools

* **OWASP ZAP (Zed Attack Proxy):** Primary tool for intercepting proxy and automated web crawling.
* **Nikto:** Command-line tool used for rapid detection of dangerous files and server misconfigurations.
* **Burp Suite (Community Edition):** Used for manual request manipulation and testing business logic.

---


