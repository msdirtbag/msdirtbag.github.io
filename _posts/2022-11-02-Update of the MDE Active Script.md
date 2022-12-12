---
layout: post
title: Update of the MDE-Active Configuration Script
thumbnail-img: ./assets/img/mdeactive.jfif
---
Hello! Made some updates to MDE-Active PowerShell script to resolve some issues identified during a recent purple team. 

1.-Enabled LSA Protected Process Light

The LSA, which includes the Local Security Authority Server Service (LSASS) process, stores Windows account hashed credentials in memory. PPL requires that applications be signed by approved signers to query credentials stored in LSA memory. Introduced in Server 2016, PPL works with Windows Defender Credential Guard & the Attack Surface Reduction "Block credential stealing" rule to help mitigate against various credential dumping TTP’s.

2.-Enabled AllowSwitchToAsyncInspection setting for Network Protection

This policy enables a new performance optimization, that allows synchronously inspected network flows, to switch to async inspection once they've been checked and validated.

3.- Enabled Script Block Logging

Script block logging allows all PowerShell scripts executed on a host machine to be transcribed and saved. To successfully hide the malicious actions of their code, threat attackers will layer obfuscation of classes and methods using a variety of techniques.  This provides additional telemetry that assists MDE Windows Antimalware Scan Interface (AMSI) detections of obfuscated PowerShell scripts and commands.

4.- Enabled RandomizeScheduleTaskTime

The helps ensure that all endpoints do not start regular disk scans at the same time every day.

⚙️Link to MDE-Active Script: https://github.com/msdirtbag/mde/blob/main/MDE-Active.ps1

![Image](/assets/img/mdeactive.jfif)

🎒Resources:

AllowAsyncInspection: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus

Script Block Logging: https://learn.microsoft.com/en-us/powershell/scripting/windows-powershell/wmf/whats-new/script-logging?view=powershell-7.2

Set-MpPreference: https://learn.microsoft.com/en-us/powershell/module/defender/set-mppreference?view=windowsserver2022-ps

PPL: https://learn.microsoft.com/en-us/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection

