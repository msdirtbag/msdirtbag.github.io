---
layout: post
title: 365 Defender Advanced Hunting Data Tables
thumbnail-img: ./assets/img/365Data.jfif
---
📣I am passionate about the 365 Defender Advanced Hunting tables for threat hunting, DFIR, and threat detection engineering because I know they work and should be imported into Microsoft Sentinel via the 365 Defender Data Connector.

🔻The 365D Advanced Hunting value proposition:
·       It covers all endpoints enrolled in MDE (Not just Windows/Linux servers with MMA/AMA installed)

·       The fields are normalized across Windows/Linux/MacOS kernels

·       It is less dependent on AD Advanced Audit policy

·       It’s an XDR dataset vs EDR dataset so it includes IAM, CASB, Email & TVM as well

Defender for Cloud Apps:

CloudAppEvents- This table in advanced hunting contains information about activities in various cloud apps and services covered by MDA. (AAD/365/Azure)

Best columns: AccountObjectId, ActionType, AccountDisplayName, Application, IsAdminOperation, DeviceName, ActivityType, RawEventData

365 Defender:

AlertEvidence- This table in advanced hunting contains information about various entities—files, IP addresses, URLs, users, or devices.

Best columns: EvidenceDirection, RemoteIP, SHA256, ThreatFamily, RemoteUrl, DeviceName, AccountUpn, ProcessCommandLine, NetworkMessageId, RegistryValueData

Defender Threat & Vunerability Management:

DeviceTvmHardwareFirmware- This table in advanced hunting contains hardware and firmware information of devices as checked by Microsoft Defender Vulnerability Management.

Best columns: DeviceName, ComponentName, ComponentVersion

DeviceTvmSoftwareVulnerabilitiesKB- This table in advanced hunting contains the list of vulnerabilities Microsoft Defender Vulnerability Management assesses devices for.

Best columns: IsExploitAvailable, VulnerabilitySeverityLevel, PublishedDate

Defender for Identity:

IdentityDirectoryEvents- This table in advanced hunting contains information about query activities made through AD & AAD captured by MDI & MDA.

Best columns: ActionType, TargetAccountUpn, Protocol, AccountUpn, DeviceName, LogonType

IdentityLogonEvents- This table in advanced hunting contains information about logon activities made through AD & AAD captured by MDI & MDA.

Best columns: FailureReason, ActionType, LogonType, AccountUpn, DeviceName, Protocol, TargetDeviceName

IdentityQueryEvents- This table in advanced hunting contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.

Best columns: QueryType, QueryTarget, ActionType, Query, Protocol, AccountUpn, DeviceName

Defender for Office 365:

UrlClickEvents- This table in advanced hunting contains information about Safe Links clicks from email messages, Microsoft Teams, and Office 365 apps.

Best columns: ThreatTypes, IsClickedThrough, UrlChain, Url, ActionType, AccountUpn

EmailPostDeliveryEvents- This table in advanced hunting contains information about post-delivery actions taken on email messages processed by Microsoft 365. 

Best columns: RecipientEmailAddress, ActionResult, ActionTrigger, DeliveryLocation, ActionType, DetectionMethods

![Image](/assets/img/365Data.jfif)
