---
layout: post
title: How to customize your AMA deployment
thumbnail-img: ./assets/img/arcamadeploy.jfif
---
Q: How does Azure Monitor Agent agents work?

A: You deploy Azure Connected Machine agents and then Azure Policy deploys the Azure Monitor Agents as Arc Server VM Extensions and links them to Data Collection Rules that feed Azure Monitor and Microsoft Sentinel.

In an ideal world, Azure Monitor, Defender for Cloud, and Microsoft Sentinel use a shared Log Analytics Workspace but sometimes complex architectures are necessary to meet business requirements.

·       Performance logs go Azure Monitor and power VM Insights and hybrid Network Watcher.
·       Security logs are shared by Defender for Cloud and Sentinel and power the CNAPP and SIEM functionality.

💡MDC auto-provisioning settings are just Azure Policy shortcuts. They create a DeployifNotExists Azure Policy Assignment, System Managed Identity, and Remediation task to deploy the relevant agents.

🔻Azure Policy can be created via REST, Bicep, ARM, Terraform, or the Azure Portal. You can group Azure Policies into Initiatives and Blueprints.

Azure Policies are similar to Azure Resource Roles. There are builtin and custom Azure Policies. There are also standard Azure Policies (that govern Azure Resources) and Azure Policies that rely on Machine Configurations (that govern variables inside of the guest OS)

Note: Microsoft charges +$6 per server, per month for non-Azure (Arc) servers that have Azure Policies that include Machine Configurations applied to them. If the ARM parameters of the Azure Policy say “IncludeArcMachines”, you know that policy uses Machine Configurations and will cause usage billing on Arc Servers.

Microsoft has done a good job of labeling Arc related Azure Policies. Search “Azure Policy” in the portal, go to Definitions, then go over to the search on the right side and look for “Arc”.

If you are using Defender for Cloud also on your servers, “Configure machines to create the Microsoft Defender for Cloud pipeline using Azure Monitor Agent” is great. If you are using Azure Monitor, add “Deploy a VMInsights Data Collection Rule and Data Collection Rule Association for Arc Machines”.

Note: Pros don’t use builtin Azure Policies. We customize them in VS Code and push them as IaC. I’m not clicking my way to applying (40) different policies on (500) different Subscriptions in the Azure Portal. If you are new to IaC, please check out bicep. 💪

![Image](/assets/img/arcamadeploy.jfif)

🎒Resources:

MDC Auto-provisioning: https://learn.microsoft.com/en-us/azure/defender-for-cloud/auto-deploy-azure-monitoring-agent#deploy-the-azure-monitor-agent-with-defender-for-cloud

Azure Policy MDC Deployment: https://github.com/Azure/azure-policy/blob/8a78c6f81d92d46985d2227de19d29f18dbeaa5e/built-in-policies/policyDefinitions/Security%20Center/ASC_AMA_UserWorkspacePipeline_DCRA_Arc_Deploy.json

Azure Policy Azure Monitor Deployment: https://github.com/Azure/azure-policy/blob/master/built-in-policies/policySetDefinitions/Monitoring/AzureMonitor_HybridVM_AMA.json

Azure Bicep: https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview?tabs=bicep

Azure Policy Definition Reference: https://learn.microsoft.com/en-us/azure/templates/microsoft.authorization/policydefinitions?pivots=deployment-language-bicep