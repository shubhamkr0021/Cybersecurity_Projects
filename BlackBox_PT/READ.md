# 🕵️‍♂️ Black Box Penetration Testing on Enterprise Network (192.168.11.0/24)

## Overview
This project presents a **black-box penetration test** simulating an external adversary targeting a corporate network.  
The engagement identified ten hidden flags, revealing misconfigurations, unpatched systems, SQL injections, CMS exploits, and privilege escalation opportunities.

---

## Objectives
- Conduct reconnaissance to identify live hosts and services.  
- Exploit vulnerabilities using industry-grade tools.  
- Capture hidden flags as proof of successful compromises.  
- Provide actionable remediation and hardening steps.

---

## Methodology & Tools
| Phase | Focus | Tools |
|--------|--------|-------|
| Reconnaissance | Host discovery, vulnerability scanning | Nmap, Nessus, Nikto |
| Exploitation | SMB (EternalBlue), CMS & SQL Injection | Metasploit, Sqlmap |
| Privilege Escalation | Local misconfigurations | Linux priv-esc scripts |
| Post-Exploitation | Flag discovery, steganography | Netcat, Steghide, Burp Suite |
| Reporting | Risk analysis & recommendations | Manual |

---

## Flag Summary
| Flag | Technique | Vulnerability | Result |
|------|------------|----------------|--------|
| 1 | SMB Exploit | MS17-010 (EternalBlue) | RCE & shell |
| 2 | File Analysis | PNG extraction | Sensitive flag |
| 3 | Registry Enum | Windows registry key | Local persistence |
| 4 | CMS Exploit | WolfCMS RCE | Web shell |
| 5 | Priv. Esc. | Misconfigured sudo | Root access |
| 6 | DNS Zone Transfer | Recon | Hidden QR flag |
| 7 | SQL Injection | OpenDocMan | Web shell access |
| 8 | Root Escalation | Weak credentials | Root flag |
| 9 | File Upload Vulnerability | PHP reverse shell | Command execution |
| 10 | Steganography | Hidden data | Flag recovery |

---

## Mitigation Strategies
- Patch outdated OS and disable legacy protocols (e.g., SMBv1).  
- Enforce strong authentication and password policies.  
- Validate and sanitize all user inputs in web apps.  
- Restrict DNS zone transfers and implement DNSSEC.  
- Deploy IDS/IPS systems for continuous monitoring.  
- Apply least privilege and routine vulnerability scans.

---

## Key Learning
This project reinforced proficiency in **offensive security tools** and **red team methodologies**, showcasing end-to-end penetration testing skills—from reconnaissance to exploitation and remediation planning.

---

**Tools Used:** `Nmap` • `Nessus` • `Nikto` • `Metasploit` • `SQLmap` • `Steghide` • `Burp Suite` • `Netcat`  
**Environment:** Simulated Enterprise Network – 192.168.11.0/24 (Kali Linux)
