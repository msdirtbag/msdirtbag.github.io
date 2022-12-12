---
layout: post
title: 365 Defender Query Health Report
thumbnail-img: ./assets/img/queryhealth.jfif
---
🔻Advanced Hunting & Custom Detections are powerful KQL tools to customize analytics and supplement native detections.

💡Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries and the restrictions are unique to each query type.

👉Queries ran via the portal:
·       Data range: 30 day (use 365D Data Connector in Sentinel if you want more)
·       Result set: 10,000 rows
·       CPU resources: The portal displays an error whenever a query runs and the tenant has consumed over 10% of allocated resources. Queries are blocked if the tenant has reached 100% until the next 15-minute cycle.

👉Graph & WindowsDefenderATP API queries:
·       Graph is the preferred option moving forward. It offers enhanced functionality, more flexibility, and greater performance. When a throttling threshold is exceeded, Microsoft Graph limits any further requests from that client for a period of time.
·       Currently, Microsoft has not documented any specific throttle thresholds for Graph Advanced Hunting so they default to the 2000 requests per second global threshold. (Welcome clarification or correction!)
·       Any Graph operation on alert, securityActions, secureScore is limited to 150 requests per second

👉Custom Detections:
·       Each CD rule is limited to 100 alerts per run
·       Can run every 1, 3, 12, or 24 hours (additional options road-mapped)
·       Requires DeviceId, Timestamp, & ReportId in results

The query resources report shows your organization's consumption of CPU resources for hunting based on queries that ran in the last 30 days using any of the hunting interfaces. This report is useful in identifying the most resource-intensive queries and understanding how to prevent throttling due to excessive use. You can find this report in the Advanced Hunting tab in the 365 Defender portal.

![Image](/assets/img/queryhealth.jfif)

🎒Resources:

Graph Threat Hunting: https://learn.microsoft.com/en-us/graph/api/security-security-runhuntingquery?view=graph-rest-beta&tabs=http&viewFallbackFrom=graph-rest-1.0

WindowsDefenderATP Threat Hunting: https://lnkd.in/gRuaYBHk

Custom Detections: https://learn.microsoft.com/en-us/microsoft-365/security/defender/api-advanced-hunting?view=o365-worldwide

Query Report: https://learn.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-limits?view=o365-worldwide#query-resource-report-contents

365D Data Tables: https://learn.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-schema-tables?view=o365-worldwide

Graph Throttling Limits: https://learn.microsoft.com/en-us/graph/throttling-limits
