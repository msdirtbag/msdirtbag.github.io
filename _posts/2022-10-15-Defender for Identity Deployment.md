---
layout: post
title: Defender for Identity Deployment
thumbnail-img: ./assets/img/mdilearn.jfif
---
📽️Microsoft’s Active Directory Monitoring solution started as Advanced Threat Analytics, migrated to the cloud as Azure Advanced Threat Protection, and then graduated into the Defender for Identity product that is deeply integrated with the other M365D products such as Defender for Endpoint, Defender for Cloud Apps, and Azure Active Directory Identity Protection.

🛑It’s important to understand that configuring an AD service account and installing the MDI sensor msi does not complete the deployment. If you stop there, your sensor will fail to detect malicious activity that it could because key installation steps were missed.

📝Key things to consider when deploying MDI:
·       Advanced Audit Policy that meets MDI’s auditing requirements is critical
·       Disable LSO on VMware DC’s that show health alerts
·       Allowlist/bypass yourdomain.atp.azure.com TCP 443 traffic from SSL intercept/proxy
·       Make sure that communication isn't blocked for localhost, TCP port 444
·       MDI takes 30 days to baseline the environment for behavioral alerts (pictured)
·       Never use the same gMSA for the monitoring & action accounts
·       Make sure that SAM-R required permissions are configured for Lateral Movement Path detections
·       You do not need to purchase Npcap licenses
·       You can use the Azure service tag AzureAdvancedThreatProtection in NSG/Azure Firewall rules
·       The monitoring gMSA account must be granted the Log on as a service permission

![Image](/assets/img/mdilearn.jfif)

🎒Resources:

Advanced Audit Policy Events: https://learn.microsoft.com/en-us/defender-for-identity/configure-windows-event-collection#relevant-windows-events

Microsoft’s Audit Policy Readiness check script: https://github.com/microsoft/Microsoft-Defender-for-Identity/blob/main/Test-MdiReadiness/Test-MdiReadiness.ps1

Raymond Roethof’s Audit Policy GUI tool: https://github.com/thalpius/Microsoft-Defender-for-Identity-Configuration-Checker

VMware fix: https://learn.microsoft.com/en-us/defender-for-identity/troubleshooting-known-issues#vmware-virtual-machine-sensor-issue

Npcap: https://learn.microsoft.com/en-us/defender-for-identity/technical-faq#why-npcap

Provisioning gMSA’s: https://windowsmanagementexperts.com/microsoft-defender-for-identity-group-managed-service-account-setup/microsoft-defender-for-identity-group-managed-service-account-setup.htm