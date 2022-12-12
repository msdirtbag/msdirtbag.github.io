---
layout: post
title: Azure Arc Rapid Onboarding
thumbnail-img: ./assets/img/ArcOnboard.jfif
---
“What is the best way to onboard servers to Defender for Cloud with Azure Arc⁉️”

Deploying the Azure Connected Machine agent can be accomplished via many methods. In reality, it’s just pushing an MSI installer & (1) PowerShell registration command on Windows and very similar on Linux distributions. It can be delivered via current management frameworks such as ConfigMgr, GPO, Chef, & Ansible.

👉Most important detail: Set up your Azure Arc landing zone before you onboard anything. Build out your Management Groups, Subscriptions, Resource Groups and Azure Policy sets. Since billing is controlled at Subscription level, make sure to create separate subscriptions for business units that need to bill individually.

💡The best way to onboard: Use the MDC Multicloud Connectors & Azure Migrate Integration

AWS- Obtain the Management Account ID and determine if any projects need to be excluded initially. Run the MDC wizard & download the Cloud Formation template. Ask the AWS Administrator to run the CloudFormation template both as a Stack and as a StackSet. Check back in 24 hours!

GCP- Obtain the Org ID and determine if any projects need to be excluded initially. Run the MDC Wizard & download the provisioning GCP Cloud Shell script. Ask the GCP Administrator to run Cloud Shell script. Check back in 2 hours!

VMware vSphere- Deploy the Azure Migrate OVA and start continuous discovery by inputting vSphere Administrator credentials. Once complete, navigate to the “Onboard to Azure Arc” submenu and input your Arc onboarding Service Principle & Secret generated in the Azure Portal. Check back in 2 hours!

Note: Azure Migrate/MDC will not auto-onboard any VM that does not have VMware tools, AWS SSM, or the GCP OS config agent. Revert to backup methods or MDC agentless VM scanning in this case.

Why❓
·       Speed matters and these methods successfully onboard at the highest rate
·       Defender CSPM needs the MDC connectors to see non-server GCP/AWS resources
·       Net new servers can be automatically onboarded by policy

![Image](/assets/img/ArcOnboard.jfif)

🎒Resources:

Azure Migrate/VMWare: https://learn.microsoft.com/en-us/azure/migrate/onboard-to-azure-arc-with-azure-migrate

MDC AWS Connector: https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings

MDC GCP Connector: https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings