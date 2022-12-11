---
layout: post
title: Azure Policy for Arc Servers
thumbnail-img: ./assets/img/arcazpolicy.jfif
---
Is this Azure Policy going to apply to on-prem & multicloud Arc servers? 🤷‍♂️

Arc servers use different resource providers for policy than normal Azure Virtual Machines. Ctrl + F and search the Azure Policy Definition for “Microsoft.HybridCompute”.

If it looks like the ARM template on the left, it is Arc compatible and needs a "IncludeArcServers" parameter to enable.

💡You can use Bicep to deploy the parameter in the deployment template by following the example on the right.

![Image](/assets/img/arcazpolicy.jfif)

🎒Resources:

Azure Bicep: https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/file

Azure Policy: https://github.com/Azure/azure-policy/tree/master/built-in-policies/policyDefinitions