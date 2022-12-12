---
layout: post
title: The best way to share Azure Managed Disks!
thumbnail-img: ./assets/img/disksas.jfif
---
Have you ever felt a little uncomfortable exposing Azure Managed Disk for Disk Export using SAS keys? (I have)

Check out the new "Data access authentication mode" preview!

If you're using Azure Active Directory (Azure AD) to control resource access, you can now use it to restrict uploads and downloads of Azure managed disks. This feature is available as a GA offering in all public cloud regions, it is a currently only available as a preview offering in Azure Government and Azure China regions. 

When a user attempts to upload or download a disk, Azure validates the identity of the requesting user in Azure AD, and confirms that user has the required permissions. At a higher level, a system administrator could set a policy at the Azure account or subscription level, to ensure that all disks and snapshots must use Azure AD for uploads or downloads.

![Image](/assets/img/disksas.jfif)

🎒Resources:

Docs: https://learn.microsoft.com/en-us/azure/virtual-machines/windows/download-vhd?tabs=azure-portal#secure-downloads-and-uploads-with-azure-ad-preview

