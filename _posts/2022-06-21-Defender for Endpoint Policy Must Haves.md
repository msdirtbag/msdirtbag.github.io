---
layout: post
title: Defender for Endpoint Policy Must Haves
thumbnail-img: ./assets/img/mdekeys.jfif
---
Let’s review some key security configurations that affect MDE resilience against threat actors and red-teamers:

#1️⃣ Tamper Protection: Is it in prod? Then it must have Tamper Protection turned on. No exceptions. Troubleshooting mode can be leveraged as needed. This applies to passive mode deployments as well.
How to enable: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/manage-tamper-protection-microsoft-365-defender?view=o365-worldwide

#2️⃣ Local Admin Merge: Restrict local admins from making MDE exclusions. This is a known threat vector and all exceptions should go through CAB.
How to disable: https://learn.microsoft.com/en-us/mem/intune/protect/antivirus-microsoft-defender-settings-windows

#3️⃣ Network Protection in Block Mode: Audit mode is not suitable for prod. MDE Block Threat Indicators for IP’s/URL’s relies on this OS component.
How to enable: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/enable-network-protection?view=o365-worldwide

#4️⃣ User Account Control: UAC must be fully enabled to mitigate tampering with MDE core components. (defense evasion via lolbins)
How to enable: https://tcm-sec.com/bypassing-defender-the-easy-way-fodhelper/

#5️⃣ Submit all samples: If this is not turned on for all samples, MDE cannot grab a copy of the file before the threat actor deletes the file from disk. (cred dumping, data staged and ingress tool transfer)
How to enable: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission?view=o365-worldwide#how-cloud-protection-and-sample-submission-work-together

⚙️MDE Configuration Script: https://github.com/msdirtbag/mde/blob/main/MDE-Active.ps1

This script can be customized as needed to deploy these (and other) key policy settings.

![Image](/assets/img/mdekeys.jfif)