---
layout: post
title: What is Microsoft's endpoint security solution for servers?
---
🕵️‍♂️Defender for Cloud “Defender for Servers” via Arc compared with Defender for Endpoint “for Servers”

🔻You may have noticed that Microsoft’s preferred EPP solution for Server endpoints has been changing for 2 years as of this week. (Ignite Week!) Defender for Endpoint for Servers was removed from CSP price lists in August and do not expect to see it as a option on your next EA renewal.

Defender for Servers P1 ($5 per server, per month) & P2 ($15 per server, per month) is the replacement solution that includes the same MDE EDR/NGAV + MDC CSPM, VM and the holistic Arc fabric for managing all of your server compute fleet with modern Azure parts regardless of where the VM is hosted. (Azure Policy, Azure Automation, Azure Monitor, Azure Automanage, Windows Admin Center, & the nirvana that is Guest Configurations!)

🧐Mr. CFO: It is also usage-based so it bills in increments of (50) hrs, per server via the Azure Subscription & linked billing account. This helps with migrating workloads. (which everyone has)

It can also be quickly deployed to complex organizations via Bicep, Azure Migrate, and the GCP & AWS connectors that use existing plumbing to rapidly onboard Windows & Linux servers.👨‍🔧

*If you are using Microsoft Sentinel for SIEM or Sysmon, you really want to use DFS P2 on all Azure & on-prem/multicloud servers and simplify your LA architecture to the minimum amount of LA workspaces. This gives your maximum functionality and minimum cost because the 500mb per month/per node credit included in DFS P2 can equal $23 of LA ingest credit per month/per node.

**If you are deploying Defender for Servers for Azure, on-prem, or multicloud servers for the first time currently, the important thing is to ensure that the MMA agent is denied by Azure Policy with limited exceptions for edge use cases.

***There are credits available for current MDE for Servers licenses available through Azure support.

🎒Resources:

Defender for Servers: https://learn.microsoft.com/en-us/azure/defender-for-cloud/plan-defender-for-servers

AMA compared to MMA/OMS: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview

MDC new releases: https://learn.microsoft.com/en-us/azure/defender-for-cloud/release-notes

Azure Arc: https://learn.microsoft.com/en-us/azure/azure-arc/overview
