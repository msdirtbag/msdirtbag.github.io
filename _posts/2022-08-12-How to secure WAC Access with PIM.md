---
layout: post
title: How to secure WAC Access with PIM
thumbnail-img: ./assets/img/wacpim.jfif
---
🥷🏻How to secure Windows Admin Center access via Azure Arc:

1.     Create a custom role for WACAdmin on the subscription containing your Arc servers. (always use custom roles)
2.     Create a role-assignable Security Group in Azure AD.
3.     Enable the Security Group as a Privileged Access Group in Azure AD.
4.     Assign the WACAdmin custom role to the Privileged Access Group under subscription IAM.
5.     Create Conditional Access Rule that targets the PAG Security Group and requires phish-resistant MFA, Management IP ranges, Intune-Compliant device (with MDE risk score), etc.
6.     Customize the PAG Activation workflow to add approvers, shorten windows.
7.     Add Eligible members to the PAG in Azure AD PIM.

🖥️Now, Windows Admin Center Administrators are required to PIM & satisfy Conditional Access security controls before using the powerful WAC administration tools!

![Image](/assets/img/wacpim.jfif)

🎒Resources:
Privileged Access Groups- https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/groups-features

WAC Roles- https://learn.microsoft.com/en-us/windows-server/manage/windows-admin-center/azure/manage-arc-hybrid-machines#azure-permissions

WAC Admin Custom Role- https://github.com/msdirtbag/azurearc/blob/main/WACCustomRole.json


