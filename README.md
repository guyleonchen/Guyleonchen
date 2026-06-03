# Microsoft Security & Endpoint Management Lab Environment

Hands-on Microsoft security and endpoint management labs focused on real-world enterprise administration, identity, compliance and attack prevention scenarios.

Each lab is structured around a practical scenario, the security or administration problem being addressed, the controls I implemented, the validation testing I performed and the final outcome. The labs demonstrate how Microsoft security and endpoint management controls can be configured, tested and verified within a modern enterprise-style environment.


---

### 📍 Details
- Location: Sydney, Australia  
- LinkedIn: [Guy Cheneval](https://www.linkedin.com/in/guy-cheneval-0646b0103)  
-  Contact: guyleonchen@gmail.com
  
---
# Restricting Temporary Local Administrator Access to Approved Devices Using Entra PIM and Intune

### Scenario:
A support administrator may need local administrator access to complete privileged tasks, but granting permanent access or allowing that access across every device increases risk. This lab addressed how to provide temporary local admin rights only when approved and only on authorised managed endpoints.

### What I Implemented
- Created an Endpoint-Admins security group for users who may require temporary local administrator access
- Created an Approved-Admin-Devices group to control which managed devices could receive local admin rights
- Configured an Intune Account Protection policy to add active members of the Endpoint-Admins group to the local Administrators group
- Scoped the policy so local admin rights only applied to devices in the Approved-Admin-Devices group
- Configured Microsoft Entra PIM to make admin group membership eligible rather than permanently active
- Required MFA, justification, and approval before temporary admin access could be activated
- Configured a one-hour activation limit to ensure elevated access automatically expired

### Validation
- Confirmed the user could not perform an administrative task before activation
- Confirmed the user could successfully perform an administrative task on an approved device after approval and activation
- Tested the same activated account on a non-approved device and confirmed the administrative action was still blocked

### Outcome

Validated that temporary local administrator access could be activated on an approved device while remaining blocked on a non-approved device, demonstrating least privilege and restricting the lateral movement of elevated access across unauthorised endpoints.

### Technical Documentation
[View Technical Documentation PDF)](https://github.com/guyleonchen/Zero-Trust-Local-Admin-Access-with-Entra-PIM-and-Intune-Account-Protection/blob/af973dac41b409924c32780d46ccf89b3eac1516/Lab%2014%20%E2%80%93%20Zero%20Trust%20Local%20Admin%20Access%20with%20Entra%20PIM%20and%20Intune%20Account%20Protection.pdf)

---

#  Microsoft Entra PIM Just-in-Time Administration
- Configured accounts to become eligible for Global Administrator access instead of permanently holding active administrative privileges
- Configured MFA and required users to provide a reason before the administrative access request could be approved
- Configured approval workflows before administrative access could be activated
- Implemented time-bound privileged access with automatic expiry
- Configured notifications to alert approvers and administrators whenever privileged access were requested or activated
- Validated the full activation lifecycle from request, approval, activation, and automatic privilege removal
- Confirmed elevated access by successfully performing administrative actions during the approved activation window
- Verified permissions were automatically revoked after the activation session expired

[Technical Documentation (PDF)](https://github.com/guyleonchen/-Microsoft-Entra-PIM-Just-in-Time-Administration/blob/77b8cd3ea82bcefc5ec538f4cce5a28b7176de55/Lab%2013%20-%20Microsoft%20Entra%20PIM%20Just-in-Time%20Administration..pdf)

# Zero Trust BYOD (MAM + Conditional Access Enforcement)
- Enforced App Protection Policies (MAM) for Outlook
- Required app protection via Conditional Access for Office 365 access
- Blocked access from unmanaged apps and browsers (Safari test confirmed)
- Restricted copy/paste and data sharing outside managed apps
- Prevented data transfer to unmanaged apps (camera/gallery blocked)
- Enforced PIN access before accessing organisational data
- Verified all controls through real testing on an iPhone

[Technical Documentation (PDF)](https://github.com/guyleonchen/Zero-Trust-BYOD-MAM-Conditional-Access-Enforcement-/blob/83cc92c97b2558eff910cba3d5781ae110ce9fe1/Lab12%20Zero%20Trust%20BYOD%20(MAM%20%2B%20Conditional%20Access%20Enforcement).pdf)


# Identity Security – Conditional Access (Location & Session Control)

- Configured Conditional Access policies in Microsoft Entra ID to enforce Zero Trust access controls  
- Defined a Named Location with Australia as a trusted region for location-based access control  
- Created a policy to block sign-ins from all locations outside of Australia across all users and cloud apps  
- Simulated external access using a VPN (US endpoint) to validate location-based restrictions  
- Verified blocked access and policy evaluation using Microsoft Entra sign-in logs  
- Correlated VPN IP address with Entra logs to confirm accurate detection of external sign-in attempts  
- Implemented session control policy using sign-in frequency to limit session duration  
- Configured 1-hour reauthentication requirement across supported cloud applications  
- Enforced MFA as a grant control to strengthen authentication security  
- Validated session expiry by confirming reauthentication was required after the defined time period  
- Confirmed session enforcement using login timestamps and repeated authentication prompts

[Technical Documentation (PDF)](https://github.com/guyleonchen/Conditional-Access-Location-Session-Control/blob/7c3f2001dc8acf174eb748fbfbdca3f3f37476fb/Lab11%20Conditional%20Access%20(Location%20Control%20and%20Session%20Control).pdf)


# Endpoint Management – Win32 Application Deployment (Microsoft Intune)

- Packaged Google Chrome Enterprise installer into a .intunewin file using Microsoft Win32 Content Prep Tool  
- Uploaded packaged application to Microsoft Intune and configured application metadata  
- Configured silent installation using msiexec for automated deployment  
- Defined device requirements including x64 architecture and minimum Windows 10 version  
- Implemented MSI-based detection rules using product code to validate installation status  
- Assigned application as Required to all managed devices for centralized deployment  
- Verified successful deployment using Intune reporting and endpoint validation

[Technical Documentation (PDF)](https://github.com/guyleonchen/Lab-10-Deploying-a-Win32-Application-Google-Chrome-Using-Microsoft-Intune-/blob/82fcec644f147670a92d0192bf138451dfc72add/Lab10%20Deploying%20a%20Win32%20Application%20(Google%20Chrome)%20Using%20Microsoft%20Intune.pdf)

# Endpoint Security – Microsoft Defender Attack Surface Reduction (ASR)

- Created Attack Surface Reduction (ASR) policy using Microsoft Intune Endpoint Security
- Configured critical rules in Block mode to prevent credential theft and Office-based attack chains
- Enabled LSASS credential protection and blocked Office applications from spawning child processes
- Assigned policy to all managed devices for centralized enforcement
- Verified rule deployment using PowerShell and Defender telemetry
- Simulated credential dumping using Sysinternals ProcDump to confirm protection was active

[Technical Documentation (PDF)](https://github.com/guyleonchen/-Endpoint-Security-Microsoft-Defender-Attack-Surface-Reduction-ASR-/blob/e5247d50e3c12a9e8da63c479fef0ba5045b80e6/Lab09%20Intune%20Attack%20Surface%20Reduction.pdf)


# Endpoint Security – Microsoft Defender Firewall

- Created Microsoft Defender Firewall baseline using Intune Endpoint Security
- Enabled firewall protection across Domain, Private, and Public network profiles
- Enforced secure defaults with inbound traffic blocked and outbound traffic allowed
- Assigned firewall policy at the device level to ensure protection regardless of user sign-in
- Verified deployment through Intune policy status and Windows Security on the endpoint

[Technical Documentation (PDF)](https://github.com/guyleonchen/Endpoint-Security-Microsoft-Defender-Firewall/blob/d6ebfcbeba4fc85f1e54e3d0171965a37a32fbb2/Lab8.pdf)


# Intune Compliance & Conditional Access Enforcement

- Created Windows 10/11 compliance policy requiring Microsoft Defender Antivirus to be enabled
- Integrated Intune compliance with Microsoft Entra Conditional Access
- Simulated noncompliant device by disabling antivirus protection
- Verified Conditional Access evaluation using report-only mode
- Reviewed sign-in logs to confirm noncompliant devices would be blocked

[Technical Documentation (PDF)](https://github.com/guyleonchen/Lab-7-Intune-Compliance-Conditional-Access-Enforcement/blob/daf397f6f2958cc17f375ef1aa85997aee7baa1f/Lab7-Intune%20-Compliance%20%26%20Conditional%20Access%20Enforcement.pdf)


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

---

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

 

