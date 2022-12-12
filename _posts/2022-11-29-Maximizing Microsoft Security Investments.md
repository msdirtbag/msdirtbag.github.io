---
layout: post
title: How do we get the most out of our Microsoft Security Investments❓
thumbnail-img: ./assets/img/blopinion.jfif
---
👉Take it from old-school MCITP Enterprise Administrator: “never take the defaults”

·Default Sentinel Analytic Rules
·Default Azure Policies
·Default Azure Resource roles
·Default AAD security settings
·Default AD security settings
·Default/No MDE Policy settings
·Default/No MDE Custom Detections
·Default/No Conditional Access Rules
·Default MDA Policies
·Default Windows Security Configurations
·Intune Devices without Security Baselines

🔻Defaults must be shipped with products but the orgs that maintain them have problematic security outcomes.

💡Part of the Assume Breach methodology is “assume your adversary has trial licenses/past experiences with the default security configs of your platforms because they are professionals (sometimes) and demand respect”

⚔️With Shodan, ROADTools, pDNS, and traditional discovery techniques, everyone can work out what you are using before they phish past your firewalls and destroy your default-configed security products.

The blue team advantage should be based on:

·Custom Detection Analytics added to 365 Defender (IAM, EDR, NGAV, Email, CASB) & Microsoft Sentinel (SIEM)

·Threat Intelligence that is not baked into security platforms by default

·Deception technologies that alert when security controls fail to detect TA’s but detect what they always do when they go shopping for data

·Preventive security controls that force TA’s to do “loud things” that should trigger SOC detections

·Choke points that focus on the invariant behaviors necessary to destroy crown jewels

·BCP plans that are designed for complete loss/ransomware situations

📝Hard Truth: Buying stuff is exciting but implementing stuff is challenging. Maximizing platforms you bought 3 years ago is a lost art that every infosec practitioner should be prepared to embrace for the next 12 months. 


![Image](/assets/img/blopinion.jfif)
