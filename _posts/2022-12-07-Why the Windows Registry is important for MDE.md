---
layout: post
title: Why the Windows Registry is important for MDE
thumbnail-img: ./assets/img/mderegistry.jfif
---
Q: Why do I need to know the Windows Registry to be a Defender for Endpoint Administrator❓

A: Because MDE isn’t like every other NGAV/EDR. 😉 Previously, we were all told: “Slap the latest AV/EDR agent on it (that the CISO liked) and then that endpoint is 100% secured”

That was never true. Most motivated and skilled red teamer/threat actors can bypass AV/EDR tools and do their job. The only question is the amount of overall effort required and how aggressively do you raise attacker cost by detecting TTP's & isolating hosts & disabling compromised accounts quickly?

👉MDE does not have a traditional built-in management channel. There is no section of the security-microsoft-com dashboard named “Policies” where you can customize your settings and apply them to device groups. (yet)

Defender for Endpoint is a federation of WDAV (NGAV) & WDATP (EDR) services that look to the Windows registry for policy settings.

ConfigMgr, MDE Attach, PowerShell, Machine Configurations, GPO, & Intune are all methods of delivering the Windows registry keys needed for MDE & OS Security policy settings and now that conversation is appropriately blended between system owners and infosec.   

This is where teams should collaborate because from a SOC & DFIR perspective, the Window Registry is a key battle ground and many of these registry keys affect MDE resilience to defense evasion techniques and detection coverage.

🔻MDE Hives:

Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Advanced Threat Protection

Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender

Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender Security Center

Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection

Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender

Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Windows Advanced Threat Protection


🔻PowerShell to create key MDE registry keys:


Set-ItemProperty -Path “HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System” -Name “ConsentPromptBehaviorAdmin” -Value 1 -Force

Set-ItemProperty -Path “HKLM:\SOFTWARE\Policies\Microsoft\Windows Defender” -Name “DisableLocalAdminMerge” -Value 0 -Force

Set-ItemProperty -Path "HKLM:\SOFTWARE\Wow6432Node\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name "EnableScriptBlockLogging" -Value 1 -Force

Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection" -Name "latency" -Value expedite -Force

Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\Lsa" -Name "RunAsPPL" -Value 1 -Force

Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\Lsa" -Name "DisableRestrictedAdmin" -Value 0 -Force

Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\Lsa" -Name "restrictanonymoussam" -Value 1 -Force 

![Image](/assets/img/mderegistry.jfif)
