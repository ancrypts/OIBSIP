# Task 6: Password Cracking and Hash Analysis

## Module Overview

This sub-directory covers the technical implementation and theoretical analysis for Task 6 of the Oasis Infobyte Cyber Security Internship. The core objective is to understand the mechanics of password storage, the risks associated with weak hashing algorithms, and the methodologies used in performing offline brute-force and dictionary-based password attacks using industry-standard tools.

---

## Sub-directory Structure

```text
CyberSecurity-Task6-PasswordCracking/
│
├── README.md               <-- This technical roadmap file
├── hash_analysis.md        <-- Analysis of cryptographic hashing standards
└── cracking_report.md      <-- Methodology and results of password recovery tests

```

---

## Technical Scope

This module focuses on the following key areas of credential security:

* **Hash Recognition:** Identifying common hash formats (e.g., MD5, SHA-1, SHA-256, bcrypt).
* **Wordlist Preparation:** Utilizing curated dictionaries (such as RockYou) to simulate real-world password recovery attempts.
* **Attack Methodologies:** Differentiating between brute-force, dictionary, and mask-based attacks.
* **Countermeasures:** Implementing strong hashing algorithms with unique salts and adaptive work factors (Key Stretching).

---

## Tooling Framework

The following tools are utilized within this module for educational testing:

* **John the Ripper:** A versatile offline password cracker used for identifying and cracking encrypted hash formats.
* **Hashcat:** An advanced GPU-accelerated password recovery utility used for high-performance brute-force operations.
* **Cewl:** A custom wordlist generator used to profile target websites for context-specific password candidates.

---

## Safety & Ethics Notice

The methodologies practiced in this task are for **educational and authorized security testing purposes only**. Attempting to crack passwords belonging to accounts you do not own or have explicit written permission to test is illegal and unethical.

---
