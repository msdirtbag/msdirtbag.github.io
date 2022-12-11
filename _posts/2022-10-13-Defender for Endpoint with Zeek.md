---
layout: post
title: Defender for Endpoint with Zeek
thumbnail-img: ./assets/img/mdefw.jfif
---
⁉️Do you use Defender for Endpoint❓
1.     Is Windows Firewall enabled for all zones?
2.     Is Network Protection enabled in block mode?
3.     ▶️Is auditing of Filtering Platform Connect & Packet Drop enabled?

📣Microsoft Defender for Endpoint now has enhanced native network detections and DeviceNetworkEvents in Advanced Hunting with deep packet inspection support through the newest open-source integration with Zeek for Windows. This feature provides organizations with dramatically increased network visibility in 365 Defender.

🧙‍♂️It’s free! But you must ensure that all endpoints have the registry settings that enable the (3) items above.

With workstations managed with Intune, you can quickly create Firewall profiles (pictured)to enable these key requirements.

With servers, it can be a more complicated change if Windows Firewall is currently disabled so coordinate with your system owners. 

⚙️There are various ways to deploy policy but this script may be helpful: https://github.com/msdirtbag/mde/blob/main/MDE-Active.ps1

![Image](/assets/img/mdefw.jfif)

🎒Resources:

Hunting: https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/hunting-for-network-signatures-in-microsoft-defender-for/ba-p/3429520

Network Protection: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/enable-network-protection?view=o365-worldwide#enable-network-protection

Windows Filtering Platform: https://learn.microsoft.com/en-us/windows/win32/fwp/about-windows-filtering-platform

Zeek Integration: https://corelight.com/company/zeek-now-component-of-microsoft-windows



