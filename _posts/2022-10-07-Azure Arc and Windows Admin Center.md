---
layout: post
title: Azure Arc + Windows Admin Center
thumbnail-img: ./assets/img/arcwac.jfif
---
Windows Admin Center is a free solution for managing Windows Servers and includes several powerful tools that the security team might want to leverage!

With the Windows Admin Center extension in Azure, you get the management, configuration, troubleshooting, and maintenance functionality for managing your Arc-enabled servers in the Azure portal. You can securely manage hybrid machines from anywhere–without needing a VPN, public IP address, or other inbound TCP ports forwarded to endpoints.

Using Windows Admin Center in the Azure portal, you can manage:

✅Certificates
✅Devices
✅Events
✅Files and file sharing
✅Firewall
✅Installed apps
✅Local users and groups
✅Performance Monitor
💰Full PowerShell
🔥Processes Dumps
🔥Packet Captures
✅Registry
✅Remote Desktop
✅Roles and Features
✅Scheduled tasks
✅Services
✅Storage
✅Updates
✅Hyper V Virtual machines
✅Virtual switches

Notes:

*Starting August 2022, Windows Admin Center now allows you to use Azure AD-based authentication for your hybrid machine. You will no longer be prompted for the credentials of a local administrator account.

*Enabling this capability will replace your existing instance of Windows Admin Center and removes the capability to manage other machines. Your previously deployed instance of Windows Admin Center will no longer be usable. Please don’t do this if you use your instance of Admin Center to manage multiple servers.

![Image](/assets/img/arcwac.jfif)

🎒Resources:

Arc + WAC: https://learn.microsoft.com/en-us/windows-server/manage/windows-admin-center/azure/manage-arc-hybrid-machines

Arc Agents: https://learn.microsoft.com/en-us/azure/azure-arc/servers/agent-overview

Automanage Deployment for Azure VM’s: https://learn.microsoft.com/en-us/azure/automanage/automanage-windows-server#participating-services

Azure Policy Deployment for Arc VM’s: https://github.com/msdirtbag/azurearc/blob/749021f26245f152cb12169979eb1fa2335abc52/DeployWACArc.json

Windows Admin Center: https://learn.microsoft.com/en-us/windows-server/manage/windows-admin-center/use/manage-servers#tools
