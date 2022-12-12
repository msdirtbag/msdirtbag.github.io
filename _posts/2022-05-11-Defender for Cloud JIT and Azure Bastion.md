---
layout: post
title: Defender for Cloud JIT & Azure Bastion
thumbnail-img: ./assets/img/bas.jfif
---
Should we use Defender for Cloud Just-in-Time or Azure Bastion to secure remote desktop access to our Azure Virtual Machines❓

Use case, data sensitivity, budget and threat profile variables always factor in. Both can be PIM/Conditional Access controlled to require approvers, access reviews, and PAW devices. Both can export logs to Log Analytics for Sentinel Analytic Rules and Threat Hunting.

🎤My opinion:

Bastion is the more dynamic solution that offers private communication over ExpressRoute & pivots to on-prem endpoints that have logical routing.

Each Bastion Standard instance will cost $200+ per month so I believe a balanced approach is best for most organizations.

·       Using Bastion Standard for your Hub, Management Network, Admin access to AVD session hosts, and other high impact use cases is ideal.

·       Using Bastion Basic for your PAW jumpboxes where you don’t want the additional attack surface (file transfer) and cost of Standard has served me well.

·       Using MDC’s “Just-in-time” activations for Azure & AWS VM’s is perfect for everything else.

Please share your thoughts and opinions! Anybody using both on the same server?

![Image](/assets/img/bas.jfif)

🎒Resources:
Bastion: https://learn.microsoft.com/en-us/azure/bastion/bastion-overview
Bastion Client: https://learn.microsoft.com/en-us/azure/bastion/connect-native-client-windows
MDC JIT: https://learn.microsoft.com/en-us/azure/defender-for-cloud/just-in-time-access-overview?tabs=defender-for-container-arch-aks


