---
layout: post
title: Don't Forget Microsoft Defender for Cloud Apps
thumbnail-img: ./assets/img/path.jpg
---
Microsoft Defender for Cloud Apps is not an agent-based Cloud Access Security Broker like ProofPoint or Netskope. It’s an IAM-based CASB so it does not require agents, but it does require the apps be configured for Azure AD SSO for full CASB functionality.

![Image](/assets/img/path.jpg)

😢Unfortunately, application modernization can seem like a daunting initiative for many orgs so MDA often becomes the forgotten Defender. It’s important to mention that most modern SaaS & on-prem apps support AAD SSO and the apps that cannot support SAML, OpenID, or Kerberos may already be on your decom list.

👉Whether you already have the majority of your enterprise apps connected to Azure AD or are just beginning your application modernization journey, do not forget about MDA!

🛑Bad call: “We already have syslog/cef collectors deployed for Sentinel and we’re already seeing Cloud Discovery data from MDE so we don’t need to deploy MDA collectors”

MDA’s Docker-based log collectors increase network visibility because you can point most SASE/Firewall/Proxy log exports at them and collect additional network telemetry beyond MDE-enrolled workstations that have Network Protection enabled. MDA Log Collectors can handle up to 50 GB per hour of logs and compresses them in the collector so don’t undersize them or put them on slow storage or you will see health alerts. Current versions of CentOS is highly preferred.

💡MDA is great for many things but strategically, it’s ideal for the enterprise applications your security team needs visibility into and SIEM log ingest may not be practical. MDA is included in E5/G5, E5/G5 Security, and EMS E5. It does not include ingest charges (like Sentinel) and MDA security alerts can be sent to Sentinel for free.

Example: Perhaps you have done some sampling and determined the Sentinel data connectors for SalesForce and Zscaler are not financially possible yet but you need visibility today. Set up the MDA integrations for both first!

📡Detection: MDA Cloud Discovery + AAD Sign-in logs via AAD SSO integration + AAD Identity Protection

👮‍♂️Governance: Conditional Access (&App Control) + User/Signin Risk Policies + MDA File/Activity/Access Policies

Tips:
Be sure to add all noteworthy Corporate/Risky/VPN/Cloud/Admin IP’s to IP Address Ranges in MDA.
Don’t forget to backup your MDA collector configs with WinSCP.
Connect every applicable MDA API integration that MDA offers.
Start learning CloudAppEvents in Advanced Hunting.
Conditional Access App Control Monitor-only policies are perfect starting points.

🎒Resources:

MDA Log Collectors: https://learn.microsoft.com/en-us/defender-cloud-apps/discovery-docker-ubuntu?tabs=centos

MDA SASE Integrations: https://learn.microsoft.com/en-us/defender-cloud-apps/zscaler-integration

MDA Advanced Hunting: https://learn.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-CloudAppEvents-table?view=o365-worldwide

MDA API Integrations: https://learn.microsoft.com/en-us/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps