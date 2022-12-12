---
layout: post
title: Privileged Access Groups in Azure AD PIM
thumbnail-img: ./assets/img/pags.jfif
---
AAD Privileged Identity Management manages Just-in-Time access to Azure AD roles & Azure Resource roles.

💡Privileged Access Groups allow IAM teams to create role-enabled security groups in AAD that can be based on something more logical such as biz unit\job role. These groups will have standing access to whatever AAD & Azure Resource roles that position requires. Membership is added as “Eligible” instead of “Active” so members have to PIM into the security group to receive their permissions in a Just-in-Time fashion.

👀By creating a Conditional Access Rule that targets that Privileged Access Group, you can assign specific security controls for users that PIM into the PAG such as: Require PAW with MDE/Intune Compliance, Require Network Location, Require FIDO2 Token, Require GPS read on MS Authenticator app, Require device type, Require AAD IDP Risk score, etc.

You can also create layers in your PIM schema such as:
·       <orgname>-itops-sysadmin-prod-noapproval
·       <orgname>-itops-sysadmin-prod-requireapproval

👉PIM approvers enforces the two-man rule of the information security but is not practical for all job roles/use cases so plan ahead. (break glass)

⚡️While PIM does not support multi-stage access reviews yet, you can create multi-stage access reviews in AAD Identity Governance for your Privileged Access Groups.

PIM Privileged Access Groups should be a core part of your IAM and PAM strategy because it streamlines privileged access management, usage and monitoring.

![Image](/assets/img/pags.jfif)

🎒Resources:

PAGs: https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/groups-features

PAG Approvers: https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/groups-approval-workflow

Conditional Access Conditions: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-conditions

Multi-stage Access Reviews: https://learn.microsoft.com/en-us/azure/active-directory/governance/create-access-review#create-a-multi-stage-access-review
