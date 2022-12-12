---
layout: post
title: Security Baselines with Defender for Endpoint
thumbnail-img: ./assets/img/accesslevels.jfif
---
Endpoint security policy has always determined attacker cost and affected cybersecurity outcomes. With 3rd party agent-based solutions, they told us: “just slap the AV/EDR agent on it” and that supposedly made the endpoint “secured & monitored”.

👻With Defender for Endpoint, that false paradigm is completely abandoned. The AV/EDR is baked into the Windows OS and works with the OS to report Threat & Vulnerability Management information holistically.

Windows 10/11 & Windows Server Baselines resolve those core TVM recommendations and can dramatically increase attacker cost. Workstation Baselines can be customized, tested, and incorporated in default workstation policy quickly with Microsoft Intune.

Server baselines are more complicated. The 1st thing to solve is new server creation. Where is the golden image? Is it in a repo? Is it a vSphere template? Find it and make sure all new servers are created with baseline standards moving forward.

Existing servers: Eliminate every server that will be decommissioned in the next 12 months from your scope. Then, separate your modern servers (2019-2022) and down-level servers (2008-2016) into groups. Plan for full baseline implementation on the modern servers and Modern Package/ASR Rules/Network Protection implementation on the down-level servers with extended service lifecycles.

💡Ideas:
·       Deploy WDACme audit mode on everything to supplement MDE telemetry
·       Deploy Microsoft-only WDAC in block mode on all Tier 0 Infrastructure
·       Ensure WDCG, LSA PPL, and ASR “Block cred stealing” is enabled on everything that supports it
·       Ensure Windows Management Framework 5.1 is installed on all down-level servers
·       Disable NTLM & WinRM basic auth on everything
·       Restrict anonymous access to named pipes and shares
·       Administrator elevation prompt behavior-Prompt for creds
·       Blocking PS, CMD, & Registry access for non-admin users

![Image](/assets/img/accesslevels.jfif)

🎒Resources:

Intune Security Baselines: https://learn.microsoft.com/en-us/mem/intune/protect/security-baselines

Microsoft Security Compliance Toolkit: https://www.microsoft.com/en-us/download/details.aspx?id=55319

Defender TVM Baselines Assessments: https://learn.microsoft.com/en-us/microsoft-365/security/defender-vulnerability-management/tvm-security-baselines?view=o365-worldwide#get-started-with-security-baselines-assessment

WDAC Policy Wizard: https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/wdac-wizard

WDACme: https://github.com/olafhartong/WDACme