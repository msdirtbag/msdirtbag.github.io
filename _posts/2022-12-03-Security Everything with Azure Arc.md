---
layout: post
title: Secure Everything with Azure Arc
thumbnail-img: ./assets/img/arcsecurity.jfif
---
“As a security pro, I understand EDR & SIEM. I don’t understand what Arc/Defender for Cloud is and why we need to use it”

🤙This is common and understandable. As infosec pros, we are trained on existing tools such as Wireshark, ELK, Sysmon, etc. When we go shopping for a platform/tool, we default to manufacturers and vendors that the infosec team has used before.

👉The real-world problem this creates is tool/platform sprawl between cybersecurity team focused on confidentiality & integrity and the infrastructure team focused on availability. Beyond the additional cost, it creates “Silos of Chaos” where the left hand doesn’t know what the right hand is doing and configuration gaps are handled in a reactive manner.

🦾Defender for Cloud is a CNAPP (Cloud-native application protection platform) that includes EDR and is best friends with the Sentinel SIEM solution because they use a common Log Analytics Workspace. Additionally, it’s also a CSPM because most incidents in the cloud happen for a specific reason and you won’t be able to see that reason if you are only looking at downstream EDR/application logs.

🥷🏻For many, PaaS services in Azure, GCP, and AWS are unmonitored by the SOC and may be publicly exposed. Threat Actors have figured this out and are pivoting faster than internal security teams. The new gold rush is attacking the PaaS services that are replacing server endpoints.

🛡️Defender for Cloud offers the infosec pro:

Visibility: All of your compute/storage/data estate in the same place. With Arc, you can get all on-prem, IaaS & PaaS reporting into a centralized Azure Security platform. With Defender for DevOps, you get visibility into the CI/CD pipeline.

Governance: Want to make sure new resources are not publicly exposed? Want to make sure all PaaS resources have Diagnostic Logging to Sentinel configured? Want to make sure Private Links are enforced? Want to make sure audit logging is configured inside every VM? Azure Policy and Defender for Cloud can do that.

Enhanced SecOps: By using tools such as the Cloud Security Explorer and Attack Path Analysis, you can investigate incidents with intuitive context. By integrating Windows Admin Center and Azure Automation in your DFIR plans, you can minimize impact and automate security responses. This enhances MDE security investigations with packet captures, process dumps, and full powershell. You can also leverage the Copy-VmDigitalEvidence runbook to capture disks for forensic analysis and processing.

![Image](/assets/img/arcsecurity.jfif)

🎒Resources:

Attack Path Analysis: https://learn.microsoft.com/en-us/azure/defender-for-cloud/how-to-manage-attack-path

Cloud Security Explorer: https://learn.microsoft.com/en-us/azure/defender-for-cloud/how-to-manage-cloud-security-explorer

Azure Policy: https://learn.microsoft.com/en-us/azure/governance/policy/overview

Copy-VmDigitalEvidence: https://github.com/mspnp/solution-architectures/tree/master/forensics