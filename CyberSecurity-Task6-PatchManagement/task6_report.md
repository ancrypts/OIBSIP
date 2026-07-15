### File: hash_analysis.md

# CRYPTOGRAPHIC HASHING & CREDENTIAL SECURITY ANALYSIS

**Document Reference:** OIBSIP-SEC-TASK6-01

**Author:** [Your Name]

**Assigned Reviewer:** Oasis Infobyte Project Evaluation Board

**Classification:** Internal Security Review Only

**Date:** July 2026

---

## 1. Executive Summary

The integrity of user credentials relies on the secure storage of password hashes. This analysis examines the technical differences between outdated hashing algorithms and modern, adaptive standards. By understanding how attackers leverage vulnerabilities in weak hashing to recover plain-text passwords, organizations can better implement secure authentication architectures.

---

## 2. Cryptographic Hashing Fundamentals

A hash function is a one-way mathematical algorithm that converts an input (a password) into a fixed-length string of characters (a hash). Secure hash functions are designed to be irreversible: it should be computationally impossible to derive the original password from its hash.

---

## 3. Comparison of Hashing Standards

| Algorithm | Status | Vulnerability Profile |
| --- | --- | --- |
| **MD5** | Obsolete | Highly vulnerable to collision attacks; extremely fast to crack. |
| **SHA-1** | Deprecated | Susceptible to collision attacks; no longer suitable for security. |
| **SHA-256** | Secure | Robust for data integrity, but too fast for password storage without salting. |
| **bcrypt** | Recommended | Adaptive algorithm; allows for a cost factor to slow down brute-force attacks. |
| **Argon2id** | Gold Standard | The winner of the Password Hashing Competition; resistant to GPU/ASIC attacks. |

---

## 4. Key Security Concepts

### A. The Role of Salting

Salting involves adding a unique, random string of characters to every password before it is hashed. This ensures that two users with the same password have different hashes in the database, rendering rainbow table attacks ineffective.

### B. Adaptive Work Factors (Key Stretching)

Modern algorithms like `bcrypt` and `Argon2id` incorporate "work factors" or "iterations." This intentionally slows down the hashing process. While this has negligible impact on a single user logging in, it increases the time required for an attacker to perform brute-force attacks by orders of magnitude.

---

## 5. Risk Assessment: Offline Password Cracking

Attackers often obtain a stolen database dump containing username/hash pairs. They then perform offline attacks:

* **Dictionary Attacks:** Attempting millions of common passwords from a wordlist.
* **Brute-Force Attacks:** Exhaustively guessing every character combination.
* **GPU Acceleration:** Using high-end graphics cards to perform billions of hash calculations per second.

---

## 6. Recommendations for Secure Storage

1. **Never use MD5 or SHA-1** for password storage.
2. **Always implement unique salts** for every user.
3. **Use adaptive algorithms** (`Argon2id` or `bcrypt`) to ensure resilience against future hardware advancements.
4. **Enforce minimum length requirements** to increase the entropy of the input space.

---

## 7. Academic References

* *Password Hashing Competition. (2015). Argon2: The memory-hard function for password hashing.*
* *NIST. (2026). Special Publication 800-132: Recommendation for Password-Based Key Derivation.*

---

