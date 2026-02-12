# Hybrid Active Directory & Microsoft 365 Lab Environment

This repository documents a Windows-based lab environment simulating small business IT operations. The environment integrates Active Directory Domain Services, Microsoft 365, Entra ID, Intune device management, Conditional Access, endpoint security policies, and structured troubleshooting workflows.

---

### 📍 Details
- Location: Sydney, Australia  
- LinkedIn: [Guy Cheneval](https://www.linkedin.com/in/guy-cheneval-0646b0103)  
-  Contact: guyleonchen@gmail.com
  
---

# Technologies & Tools

Active Directory • Microsoft 365 • Entra ID • Intune • Microsoft Defender • DNS • VMware • Networking • Jira

---

# Microsoft 365 & Entra ID Configuration
- Created a new **tenant**, added **users**, and assigned **licenses**  
- Configured **Multi-factor authentication (MFA)** with Microsoft Authenticator  
- Applied **least privilege roles** (Helpdesk Admin instead of Global Admin)  

[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/c09ac7773c787b297dc067a4709663b4542f80a9/Lab1-M365-Tenant-MFA-Evidence-Final.pdf)

# Intune Device Enrollment & Compliance
- Enrolled **VMware Virtual Machine (VM)** into **Intune** via **Microsoft Entra ID**  
- Applied **password** and **compliance policies**  
- Enforced **least privilege** with a separate local admin account  

 [Technical Documentation (PDF](https://github.com/guyleonchen/Labs-1---6/blob/c09ac7773c787b297dc067a4709663b4542f80a9/Lab2-Intune-Enrollment-Policy-Evidence-Final.pdf)

# Windows Autopilot Deployment
- Configured **Windows Autopilot** for Out-of-Box Experience (OOBE)  
- Enforced **Multi-factor authentication (MFA)** and **Windows Hello for Business** during setup  
- Provisioned devices with **standard user accounts** by default
  
[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/c09ac7773c787b297dc067a4709663b4542f80a9/Lab3A-Cloud-DeviceMgmt-Autopilot-Intune-EntraID-Evidence-Final.pdf)

# Active Directory Domain Services Deployment
- Installed and configured **Active Directory Domain Services (AD DS)** on a Windows Server **Virtual Machine (VM)**  
- Created a new **forest** and `lab.local` **domain**  
- Used **Active Directory Users and Computers (ADUC)**, **Group Policy**, and **Domain Name System (DNS)** for centralized management  

[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/c09ac7773c787b297dc067a4709663b4542f80a9/Lab3B-Local-DeviceMgmt-VMware-ADDS-lab.local-Evidence-Final.pdf)

# Active Directory User Lifecycle & RBAC 
- Created **users** and **groups**, reset **passwords**, and tested **logins**  
- Applied **password complexity rules** with Group Policy  
- Demonstrated **Role-Based Access Control (RBAC)** through AD accounts  


[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/22829c4f34d728f31d2db6d87e114f517004f34b/Lab4-AD-Lifecycle-Summary-Final.pdf)

# Ticketing & Incident Workflow
- Created and closed **tickets** in Freshservice/Jira  
- Documented **Knowledge Base (KB)** articles  
- Simulated and resolved **Windows issues** with **Event Viewer**
  
[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/22829c4f34d728f31d2db6d87e114f517004f34b/Lab5-Ticketing-Windows-Troubleshooting-Summary-Final.pdf)

# Networking & Remote Support
- Ran `ping`, `tracert`, and `ipconfig` for **network troubleshooting**  
- Simulated **Virtual Private Network (VPN) connectivity issues**  
- Delivered **remote support** using **Remote Desktop Protocol (RDP)** and **TeamViewer**
  
[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-1---6/blob/22829c4f34d728f31d2db6d87e114f517004f34b/Lab%206%20%E2%80%93%20Networking%20%2B%20Remote%20Support.pdf)


# Windows Fundamentals (1–3) 

- User and password management  
- Configured **User Account Control (UAC)**  
- Applied **Windows security best practices**  
- Managed **Windows Defender Firewall** (rules & profiles)  

[Technical Documentation (PDF)](https://github.com/guyleonchen/Labs-Tryhackme/blob/ae59476a2888135abea17f4ae6fbd254a13c6da3/Windows%20Fundamentals%201%20to%203%20Labs%20Summary.pdf)

# Linux Fundamentals (1–3)  
- Navigated **Command Line Interface (CLI)** and managed files/folders  
- Controlled **file permissions and ownership** (`chmod`, `chown`)  
- Inspected **system/auth logs** and managed **processes**  
- Archived/compressed files and manipulated **text** (`grep`, `find`, `head`, `tail`)  

[Technical Documentation (PDF)](https://github.com/guyleonchen/Linux-Fundamentals/blob/85715df743a41f86fd37461e11b551f2f2afab1a/linux%20Fundamentals%20Labs%20Summary%201%20to%203%20Labs%20Summary.pdf)

---

# Education, Training & Certifications
<p>
  <img src="https://raw.githubusercontent.com/guyleonchen/PNG-certs/f24a65171e076010443138707ef8019803eafc47/Google-Cybersecurity-Certificate.png" width="220" />
  <img src="https://raw.githubusercontent.com/guyleonchen/PNG-certs/407cb49396938b88b4d2843d93a57efa474d5dc4/cisco%20anyl%20path.png" width="220" />
  <img src="https://raw.githubusercontent.com/guyleonchen/PNG-certs/e88e8d0d36b7ad69fd3ba94034ae900dc4caeda1/sec%20plus.png" width="220" />
</p>


# Cybersecurity & IT
- Google Cybersecurity Professional Certificate – Completed 31 Dec 2024  
- CompTIA Security+ (SY0-701) – Completed 21 Jul 2025 
- Cisco Junior Cybersecurity Analyst Career Path – Completed 04 Aug 2025
- Planning to pursue CCNA in 2026.

---
  
# AI Cybersecurity Projects 
 Projects built with AI-assisted tools to improve security awareness and phishing detection.
 
**AI Cybersecurity Game (LovableAI)**
- Interactive game to train users on phishing detection and safe communication.
- Includes simulations, quizzes, and certification tracking.
  
[Play the game](https://emailsecurityawarenesscampaign.lovable.app/) / 📄 [View PDF](https://github.com/guyleonchen/AI-design/blob/e2a08bef126a3412bc7a3b06e6267ee319cd2718/Game%20Design%20With%20AI.pdf)
  
**CyberGuard Pro – Email Phishing Scanner** 
- React-based phishing detection tool with real-time threat scoring.  
- Flags impersonation, suspicious links, and risky attachments.

[Try CyberGuardPro](https://cyber-guard-analyze.lovable.app/) / 📄 [View PDF](https://github.com/guyleonchen/CyberGuard-Pro/blob/ca1d6f4ea7d5014051a1ac4d52445f38a119c7a2/CyberGuardPro%20AI%20Portfolio.pdf)
 

