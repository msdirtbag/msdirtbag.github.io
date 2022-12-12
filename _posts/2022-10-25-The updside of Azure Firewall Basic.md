---
layout: post
title: The upside of Azure Firewall Basic
thumbnail-img: ./assets/img/azfwbasic.jfif
---
Is Azure Firewall Basic only suitable for SMBs❓

🧐It may be a valuable tool in the Azure Security Architect’s toolbox:

💥Azure Firewall Basic as-a “segment/boundary firewall” that routes through a Standard/Premium Firewall/WAF further upstream or has compensating controls from Azure Monitor/Network Watcher/Sentinel may make centralized management through Azure Firewall Manager and Defender for Cloud more practical.

🥊From a cloud incident response perspective, it allows for more dynamic SOAR responses & attack path analysis compared to NSG’s.

![Image](/assets/img/azfwbasic.jfif)

🎒Resources:

Azure FW Basic: https://azure.microsoft.com/en-us/blog/azure-firewall-basic-now-in-preview/

Pricing Calculator: https://azure.microsoft.com/en-us/pricing/calculator/

Azure FW Manager: https://learn.microsoft.com/en-us/azure/firewall-manager/overview

Networking Overview: https://learn.microsoft.com/en-us/azure/security/fundamentals/network-overview
