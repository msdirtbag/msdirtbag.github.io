---
layout: post
title: The New Server Endpoint Security Standard
thumbnail-img: ./assets/img/mdcmulti.jfif
---
“Previously, I deployed and managed Defender for Endpoint for Servers but I got to my new employer and the procurement department is telling me that MDE for Servers licenses are not available anymore.“

📣Microsoft has started decommissioning MDE for Servers in favor of Defender for Servers via Defender for Cloud. The legacy plan was converted to Defender for Business (for Servers) for SMB clients that have less than (60) non-Azure Servers.

💡If you plan on adopting Azure as your preferred hosting platform or you plan on using the Sentinel SIEM solution, the MDC DFS P2 Solution @ $15 per node, per month is a slam dunk because of the enhanced functionality and Log Analytics ingest credits.

If that is not the case, Microsoft Defender for Cloud (for Servers) P1 is your logical replacement. You need to deploy Azure Connected Machine Agents to all server endpoints and then MDC will auto-onboard them to MDE.

⚙️MDE Server Policy Management Channels:

MDE Attach- Complete the AD Connect requirements and create the dynamic AAD groups necessary so server policy management can be managed in Intune without MDM enrollment. (and select a backup method to deploy ASR rules)

GPO- Group Policy depends on AD health but it’s still the best way to deploy policy to domain joined servers via GPO & scheduled tasks.

Automanage- Automanage can deploy and manage some MDE policy settings via the Antimalware Extension. (No ASR Rules)

Automanage Machine Configurations-This add-on configuration functionality costs +$6 per month, per Server, and enables granular configuration of everything inside of the guest OS.

ConfigMgr- You can create a package with the Arc onboarding script and deploy it to a collection. You can still use Antimalware & Exploit Guard polices for MDE policy management.

ConfigMgr with Tenant-Attach- Preferred if requirements are met, this option is ideal for organizations that use ConfigMgr today and have already set up co-management 
and configured Tenant-attach.

![Image](/assets/img/mdcmulti.jfif)

🎒Resources:

Deploying Arc Agents: https://learn.microsoft.com/en-us/azure/azure-arc/servers/onboard-service-principal

MDE Attach: https://lnkd.in/gYuV-xef

Tenant Attach: https://learn.microsoft.com/en-us/mem/intune/protect/mde-security-integration

GPO: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/manage-mde-post-migration-group-policy-objects?view=o365-worldwide

ConfigMgr: https://lnkd.in/g3tbydaz

Automanage: https://learn.microsoft.com/en-us/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies

MDC DFS Plans: https://learn.microsoft.com/en-us/azure/defender-for-cloud/plan-defender-for-servers#plan-features

Defender for Business (for servers): https://learn.microsoft.com/en-us/microsoft-365/security/defender-business/get-defender-business-servers

