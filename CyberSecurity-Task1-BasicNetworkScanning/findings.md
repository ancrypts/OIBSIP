# Findings

## Scan Summary

The network scan was performed using Nmap to identify active hosts, open ports, running services, and the operating system of the target machine.

---

## Active Host

The target system responded successfully to the scan, confirming that it was online.

---

## Open Ports

| Port | State | Service |
|------|-------|---------|
| 22 | Open | SSH |
| 80 | Open | HTTP |
| 443 | Open | HTTPS |

---

## Services Identified

- OpenSSH
- Apache HTTP Server

---

## Operating System

Linux (Detected by Nmap)

---

## Potential Security Risks

- SSH service exposed.
- HTTP service accessible.
- Service versions should be updated regularly.

---

## Recommendations

- Close unnecessary ports.
- Enable firewall rules.
- Keep software updated.
- Disable unused services.

---

## Conclusion

The scan successfully identified network services and provided useful information for further security assessment.
