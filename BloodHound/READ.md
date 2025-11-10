# 🩸 Active Directory Penetration Testing using BloodHound

## Overview
This project showcases a **full Active Directory (AD) exploitation** scenario using **BloodHound** and **Evil-WinRM** within a simulated Windows domain “lands.between”.  
The assessment traced attack paths from low-privilege accounts to **Domain Administrator** by exploiting weak passwords, misconfigured permissions, and GenericAll ACL rights.

---

## objectives
- Enumerate domain structure and user privileges.  
- Identify misconfigurations and privilege escalation vectors.  
- Gain domain administrator access and prove control via flag capture.  
- Demonstrate real-world attack chains within AD environments.

---

## Methodology & Tools
| Stage | Techniques | Tools |
|--------|-------------|-------|
| Reconnaissance | Port scanning, LDAP enumeration | Nmap, ldapsearch |
| Credential Harvesting | Hash cracking and weak password analysis | Impacket, John the Ripper |
| Privilege Escalation | GenericAll permission abuse | rpcclient |
| Domain Mapping | AD relationship visualization | BloodHound, SharpHound |
| Remote Access | Pass-the-hash & WinRM exploitation | Evil-WinRM |

---

## Attack Chain Summary
1. **User “velkan.deathwatch”** with password `password` provided initial foothold.  
2. Discovered **“nymir.gravetide”** had GenericAll rights over **“nymir.runehunter”**.  
3. Reset target’s password and established **Evil-WinRM shell**.  
4. Elevated to **Administrator** by compromising privileged group “ErdtreeThrone”.  
5. Captured two flags proving **full domain compromise**.

---

## Key Findings
| Weakness | Description | Impact |
|-----------|--------------|--------|
| Weak credentials | Default & guessable passwords | Unauthorized access |
| Excessive privileges | GenericAll ACL permissions | Privilege escalation |
| Misconfigured SMB shares | Exposed sensitive files | Data leakage |
| Lack of MFA | Weak remote access security | Account compromise |

---

## Security Recommendations
- Enforce complex password policies and regular rotation.  
- Audit and restrict AD permissions (remove GenericAll).  
- Implement Multi-Factor Authentication (MFA).  
- Limit SMB and LDAP exposure to trusted networks.  
- Monitor suspicious login attempts and privilege escalations.

---

##  Key Learning
The project demonstrates **Active Directory attack paths**, from reconnaissance to full domain compromise, using open-source tools and real-world techniques relevant to **red team operations**.

---

**Tools Used:** `BloodHound` • `Impacket` • `Evil-WinRM` • `rpcclient` • `JohnTheRipper` • `Nmap`  
**Environment:** Windows Server 2022 Domain (lands.between)
