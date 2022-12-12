---
layout: post
title: We onboarded everything to MDC/MDE/Sentinel, now what❓
thumbnail-img: ./assets/img/eaccess.jfif
---
🎯Hunt-Statistically, you probably don’t have live TA hanging out in your network and that’s 100% Ok. Teach your staff to hunt and get ready for the inevitable. If you don’t have red-teamers, use Caldera, Atomic Red Team, or any other BAS tool to generate realistic TTP’s and validate your detections. There are (300) things on github that your CSIRT team will probably see in the next couple of years. Practice with them (safely) before the real live action begins!

Focus Areas:
T1055 Process Injection
T1086 PowerShell
T1003 Credential Dumping
T1036 Masquerading
T1059 Command-line Interface
T1064 Scripting
T1053 Scheduled Task
T1060 Registry Run Keys / Startup Folder
T1082 System Information Discovery
T1089 Disabling Security Tools

ATT&CK: https://attack.mitre.org/

🛠️Build new modern infrastructure-
Technical debt is cybersecurity debt. If you are not building, your security posture gets worse by the day because atrophy only goes in one direction. When somebody lands a beacon inside your network via exposed remote access/phishing, they will be shopping for the oldest piece of infrastructure you have because they know it’s going to have the least amount of security controls. Building more secure modern Infrastructure (and migrating to it) mitigates business risk.

🛑Note: If it’s connected to Active Directory, that app is a legacy/high risk app because it has zero adaptive security controls. (AD allows IDs to auth with username/password with no MFA or adaptive security controls) It should require compensating security controls and it should be targeted for asap decommissioning if it cannot support AAD based SAML or Kerberos authentication.

⚙️Harden existing infrastructure-
Use MDC Recommendations and 365D Recommendations as your baseline. While not exhaustive, they are the 1st things that will be attempted when somebody starts working your network. 0-days are not necessary if you still have SMBv1 and LLMNR enabled.😉

![Image](/assets/img/eaccess.jfif)

🎒Resources:

Maturity Model - Security Governance- https://learn.microsoft.com/en-us/security/ciso-workshop/the-ciso-workshop-videos#maturity-model---security-governance

Ransomware response plan- https://learn.microsoft.com/en-us/security/compass/protect-against-ransomware

Security rapid modernization plan- https://learn.microsoft.com/en-us/security/compass/security-rapid-modernization-plan

Enterprise Access Model- https://learn.microsoft.com/en-us/security/compass/privileged-access-access-model

Caldera: https://github.com/mitre/caldera

Atomic Red Team: https://github.com/redcanaryco/atomic-red-team
