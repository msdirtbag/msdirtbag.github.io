---
layout: post
title: Microsoft Monitoring Agent End-of-Life
thumbnail-img: ./assets/img/mmaeolplan.jfif
---
Does your organization use the Microsoft Monitoring Agent❓

💡The Microsoft Monitoring Agent (or OMS Agent) was introduced in System Center 2012 R2. Over the years, various Microsoft product teams adopted it, and MMA became the default monitoring agent for MDE, MDC, and Sentinel.

🔻On August 31st 2024, that Microsoft Monitoring Agent will be decommissioned and anything that is still using it becomes YMMV.

There are (2) ways to handle this transition:

Let it ride- Don’t change a thing, keep rolling new servers with MMA, and hope that enough people complain and get the deadline extended to December 2024 then deal with it last minute and curse Microsoft for making you replace (1) agent with (2).

Get busy- There is no 1-for-1 replacement agent. The Azure Monitor Agent is much improved but requires the Azure Arc fabric agent that makes your non-Azure server a 90% capable Azure server for Azure Management platforms such as Azure Automation, Azure Monitor, Azure Policy, Update Management Center, Windows Admin Center, Microsoft Sentinel and Defender for Cloud.

👉Strategy:

With the Arc addition to Defender for Cloud and Sentinel, Azure can become that common fabric that the Infrastructure & Security team uses to manage and secure your Compute estate but it’s not going to happen automagically.

You need to ask your Microsoft Rep to check if you are eligible for a “Secure Multicloud Environments” workshop and/or start testing with a Jumpstart ArcBox for IT Pros.

As the Forrester Total Economic Impact study reports, there are significant economic, security, and governance reasons to evaluate the Azure Arc/AMA solution but technical POC’s are the best way to craft realistic expectations and plan your transition.

![Image](/assets/img/mmaeolplan.jfif)

🎒Resources:

Forrester Report: https://azure.microsoft.com/en-us/blog/forrester-total-economic-impact-study-azure-arc-delivers-206-percent-roi-over-3-years/

Azure Arc Jumpstart: https://azurearcjumpstart.io/azure_jumpstart_arcbox/itpro/

MMA to AMA Migration: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration

MMA EOL: https://azure.microsoft.com/en-us/updates/were-retiring-the-log-analytics-agent-in-azure-monitor-on-31-august-2024/
