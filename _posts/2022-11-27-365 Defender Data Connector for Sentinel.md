---
layout: post
title: 365 Defender Data Connector for Sentinel
thumbnail-img: ./assets/img/365data.jfif
---
Q: Should we enable the 365 Defender Data Connector in Microsoft Sentinel?

A: Only if you want to be successful! If you are buying a SIEM to check a box, you can save up to 15% on your Sentinel Total-Cost-of-Ownership by not ingesting 365D raw logs. Unfortunately, that design decision will blind your security program and make your new SIEM into more of an “alert aggregator” platform than advanced analytics and correlation platform.

Why⁉️

💡While you can get 365D security alerts ingested in Sentinel for free, that’s not an ATT&CK data source, it’s just alerts without context. EDR’s, in general, are guessing platforms that miss 30-40% of evil when purple teamed. That’s why when you investigate an EDR alert in a SOC, you look at the (100) timeline events that happened before and the (100) timeline events that happened after the alert to find the malicious TTP’s the EDR collected telemetry on (but did not generate an alert) to complete the incident investigation.

🔺If you tell an IR pro called in for a case that you have a SIEM but your SIEM doesn’t have process, command line, file, or network data sources, they will stop asking for a login because that is the data that tells the true story.

👉By ingesting 365D raw logs into Sentinel, you can transform your security monitoring program and enable granular visibility on all endpoints. (Instead of only servers with MMA/AMA installed)

You can use this high value dataset to transform your detection analytics program and focus on the invariant behaviors of sub-techniques that do not change regardless of procedural implementation. You can also archive these key datasets for legal and compliance requirements via Azure Data Explorer.

My favorite unique 365D advanced hunting data types:
AADSignInEventsBeta
AADSpnSignInEventsBeta
AlertEvidence
CloudAppEvents
UrlClickEvents
IdentityLogonEvents
IdentityQueryEvents
IdentityDirectoryEvents
DeviceLogonEvents
DeviceNetworkEvents (with Zeek!)

*Note: The AMA agent should still be installed on every server. It handles MDC logs and custom log ingest via Data Collection Rules.

![Image](/assets/img/365data.jfif)

🎒Resources:

365D Data Connector: https://lnkd.in/gsJUhPsy

ATT&CK Data Sources: https://lnkd.in/gJHQ_tcP

Example of DeviceProcess: https://lnkd.in/g-RQFi4q

Understanding Data Sources: https://lnkd.in/grYauWfh



