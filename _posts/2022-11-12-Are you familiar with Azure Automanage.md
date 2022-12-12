---
layout: post
title: Are you familiar with Azure Automanage
thumbnail-img: ./assets/img/automanage.jfif
---
Azure Automanage is the policy management solution for Azure & non-Azure (Arc) Servers.

🔹Intelligently onboards virtual machines to selected policies

🔹Supports customization of best practice service configurations

🔹Monitors for drift and corrects for it when detected

🔹Provides a simple experience (point, click, set, forget)

🔺Automanage is a cousin of Azure Policy and extends policy configuration inside of the guest OS kernel via Machine Configurations. (previously called Azure Policy Guest Configurations) Automanage Machine Configurations uses PowerShell Desired State Configuration manifests (Windows & Linux) and Chef InSpec (Linux-only) to specify settings inside of the OS and validates them every 15 minutes.

⚙️When it finds conflicts, Machine Configurations has (3) possible modes:

·Audit: Generate a security recommendation that can be tracked individually or across the entire fleet.

·Apply and monitor: Apply once and monitor for configuration drift.

·Apply and autocorrect: Audit and reconcile differences.

💡What can I use Machine Configurations for?

·Verifying Advanced Audit Policy

·Enforcing mandatory installed applications

·Deploying Security Baselines

·Enforcing key security controls via registry keys

·Customizing every part of the OS endpoint

💰How much does Automanage cost?

Automanage is free of charge. Automanage Machine Configurations is included with Azure Virtual Machines. You should budget $6 per month/per node for Automanage Machine Configurations on Arc Servers.

🤷What should I watch out for?

·Automanage functionality for Arc & Linux endpoints is still expanding

·PowerShell 7.2 is required for generating the DSC profiles and preferred on all endpoints (you can use machine configurations to push PS 7.2😉)

·Arc server access to *.guestconfiguration-azure-com is required

![Image](/assets/img/automanage.jfif)

🎒Resources:

Azure Automanage: https://learn.microsoft.com/en-us/azure/automanage/overview-about

Machine Configurations: https://learn.microsoft.com/en-us/azure/governance/machine-configuration/overview

PowerShell DSC: https://learn.microsoft.com/en-us/powershell/dsc/overview?view=dsc-2.0

Azure VM Deploy: https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Guest%20Configuration/GuestConfiguration_DeployExtensionWindows_Prerequisite.json

Arc VM Deploy: https://learn.microsoft.com/en-us/azure/architecture/hybrid/azure-arc-hybrid-config