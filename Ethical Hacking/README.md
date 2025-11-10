# 🔍 Penetration Testing on Windows & Linux Systems

## Overview
This project demonstrates a **complete red teaming simulation** against two virtual machines — Windows 7 Professional and CentOS 7 — to identify, exploit, and document security vulnerabilities in a controlled environment.  
The assessment followed a structured ethical hacking methodology (Reconnaissance → Exploitation → Post-Exploitation → Pivoting) aligned with **OWASP**, **PTES**, and **OSSTMM** standards.

---

## Objectives
- Evaluate security posture of Windows 7 and CentOS 7 systems.  
- Identify exploitable vulnerabilities using both local and remote exploits.  
- Demonstrate lateral movement and privilege escalation.  
- Simulate real-world adversarial behavior in a safe lab environment.  
- Document all findings and propose security mitigations.

---

## Methodology & Tools
| Phase | Techniques Used | Tools |
|-------|------------------|-------|
| Login Bypass | Sticky Keys exploit, GRUB root reset | CMD, Linux boot params |
| Reconnaissance | Host discovery, port scanning | Netdiscover, Nmap, Nikto |
| Exploitation | EternalBlue (MS17-010), SMB misconfigurations, SQL Injection | Metasploit, sqlmap, smbclient |
| Pivoting | Lateral movement via Meterpreter | Metasploit |
| Reporting | Risk classification, mitigation planning | Manual analysis |

---

## Key Exploits
- **Windows 7 Sticky Keys (sethc.exe)** – Local privilege escalation via accessibility bypass.  
- **EternalBlue (MS17-010)** – Remote code execution over SMBv1.  
- **CentOS GRUB Password Reset** – Root access through bootloader modification.  
- **SQL Injection on CentOS Web App** – Authentication bypass and credential dump.  
- **Pivoting** – Internal data exfiltration through Windows foothold.

---

## Results Summary
| Vulnerability | Impact | Risk | Fix Priority |
|----------------|---------|------|---------------|
| Sticky Keys exploit | SYSTEM access | Critical | < 7 days |
| EternalBlue (MS17-010) | Remote execution | Critical | < 7 days |
| SQL Injection | Auth bypass | Critical | < 7 days |
| Weak SMB Permissions | Data exposure | High | < 30 days |
| No Segmentation | Lateral movement | High | < 30 days |

---

## 🛡️ Recommendations
- Disable SMBv1 and patch MS17-010.  
- Secure `sethc.exe` and enable full-disk encryption.  
- Implement strict GRUB and BIOS authentication.  
- Enforce prepared statements for SQL queries.  
- Segment internal networks and enable monitoring.

---

## 🧩 Key Learning
This project highlights the importance of **patch management**, **network segmentation**, and **access control** in preventing full-domain compromise through simple misconfigurations.

---

**Tools Used:** `Nmap` • `Metasploit` • `sqlmap` • `Nikto` • `Kali Linux` • `Wireshark`  
**Environment:** VirtualBox / VMware Controlled Lab
