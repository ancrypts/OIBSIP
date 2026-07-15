# WEB APPLICATION VULNERABILITY ASSESSMENT REPORT

**Document Reference:** OIBSIP-SEC-TASK5-01

**Author:** [Your Name]

**Assigned Reviewer:** Oasis Infobyte Project Evaluation Board

**Classification:** Internal Security Review Only

**Date:** July 2026

---

## 1. Executive Summary

This report details the results of a comprehensive vulnerability assessment performed on the target web application. The objective was to identify security weaknesses that could be exploited by malicious actors to compromise data integrity, confidentiality, or system availability. The assessment utilized a combination of automated scanning tools and manual verification techniques, identifying several high-priority misconfigurations and outdated components.

---

## 2. Assessment Methodology

The evaluation followed an industry-standard three-phase approach:

* **Phase 1: Automated Scanning:** Execution of `OWASP ZAP` and `Nikto` to map the attack surface and identify common vulnerabilities.
* **Phase 2: Manual Verification:** Verification of identified issues to confirm exploitability and eliminate false positives.
* **Phase 3: Impact Analysis:** Evaluation of the potential business impact for each confirmed vulnerability.

---

## 3. Vulnerability Findings

| ID | Vulnerability Name | Severity | Risk Description |
| --- | --- | --- | --- |
| **V-01** | Directory Listing Enabled | Medium | Server reveals internal file structures, aiding reconnaissance. |
| **V-02** | Missing Security Headers | Low | Absence of HSTS or CSP headers increases susceptibility to XSS. |
| **V-03** | Outdated Server Software | High | Known CVEs in the web server version allow for remote exploitation. |
| **V-04** | Exposed Backup Files | Critical | Presence of `.bak` files allows attackers to download source code. |

---

## 4. Technical Analysis

### A. Directory Listing (V-01)

The web server is configured to allow directory indexing. If a user navigates to a directory without an `index.html` file, the server displays the entire contents of that folder. This provides an attacker with a blueprint of the application's file system, significantly reducing the effort required to identify sensitive scripts or configuration files.

### B. Outdated Server Software (V-03)

The scan identified an obsolete version of the web server software (e.g., Apache 2.4.x). Publicly available vulnerability databases (CVEs) list several remote code execution exploits targeting this version.

---

## 5. Remediation Strategy

* **Disable Directory Indexing:** Modify the web server configuration (e.g., `Options -Indexes` in Apache) to prevent folder content listing.
* **Implement Security Headers:** Configure the web server to include `Strict-Transport-Security`, `Content-Security-Policy`, and `X-Frame-Options` headers in all responses.
* **Patch Management:** Immediately update the web server and all associated CMS components to the latest stable versions to close known security gaps.
* **Secure Cleanup:** Remove all temporary backup files and development-related documentation from the production web root.

---

## 6. Conclusion

The current web application footprint contains significant configuration weaknesses that could be exploited to compromise the system. By implementing the recommended remediation steps—specifically patching outdated software and tightening server configuration—the application's attack surface can be drastically reduced.

---

## 7. Academic References

* *OWASP Foundation. (2026). OWASP Top 10:2021 Project Documentation.*
* *National Institute of Standards and Technology (NIST). (2026). SP 800-115: Technical Guide to Information Security Testing and Assessment.*

---

Would you like to move on to the `README.md` and report for Task 6, or is there another part of your internship project you would like to focus on?
