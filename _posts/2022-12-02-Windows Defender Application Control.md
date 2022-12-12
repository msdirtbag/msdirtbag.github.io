---
layout: post
title: Windows Defender Application Control
thumbnail-img: ./assets/img/wdac.jfif
---
If we have MDE, should we deploy Windows Defender Application Control❓

Simply put: Yes, but you need to have a plan that your organization is prepared to support and approved by management. WDAC is a very powerful tool to increase attacker cost, but it can affect user productivity if deployed incorrectly. WDAC uses Device Guard/Code Integrity policies to determine what can/cannot run on your endpoints. (or audit them)

Note: MDE uses this same functionality for the "Restrict App Execution" response action. I have had excellent results using that response option as the initial triage response action for most high/critical alerts. It doesn't shut everything down like Isolate but it kills most C2 implants and gives you time to investigate fully and determine if it's true/false positive.

👇Microsoft’s well-informed WDAC design guidance:

Executive sponsorship and organizational buy-in is in place.

There's a clear business objective for using application control, and it's not being planned as a purely technical problem from IT.

The organization has a plan to handle potential helpdesk support requests for users who are blocked from running some apps.

The organization has considered where application control can be most useful (for example, securing sensitive workloads or business functions) and also where it may be difficult to achieve (for example, developer workstations).

Q&A:

Should we use AppLocker as well?
·       No with rare exceptions
What OS’s support WDAC?
·       Server 2016+ & Modern W10 builds+

🔻Strategy to get started:

Assign at least (2) WDAC system owners. They must learn everything about WDAC and they must produce documentation continuously for the helpdesk team and maintain org policy.

1st- Install WDACme on all W10 workstations

2nd- Enable “Smart Application Control” in Evaluation mode on W11 endpoints that support it

3rd- Lock down Tier 0 (DC’s, ADFS & AD Connect servers) with WDAC Microsoft-only mode in block mode. (No 3rd party software should ever be installed on the Tier 0 server type)

4th- Deploy a supplemental policy to block the Microsoft recommended block list

🔑Golden rule: “Audit is better than nothing”

🎯Desired state: “Zero Trust for unapproved code”

![Image](/assets/img/automanage.jfif)

🎒Resources:

Recommended Block Rules: https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/microsoft-recommended-block-rules

WDAC Policy Wizard: https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/wdac-wizard

W11 Smart App Control: https://support.microsoft.com/en-us/topic/what-is-smart-app-control-285ea03d-fa88-4d56-882e-6698afdb7003

Hunting WDAC Events in KQL: https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/querying-application-control-events-centrally-using-advanced-hunting

WDAC Deployment: https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide

⛄️ Olaf Hartong's: WDACMe: https://github.com/olafhartong/WDACme



