---
layout: post
title: Defender for Databases with Arc-enabled Data Services
thumbnail-img: ./assets/img/mdcdatabase.jfif
---
👉Defender for Cloud’s Defender for Databases is a broadly compatible security add-on for database workloads. It includes threat protection monitoring and vulnerability assessment services for Azure SQL, SQL Managed Instances, PostgreSQL, CosmosDB, MySQL & SQL Servers on Windows/Linux VM’s inside and outside of Azure.

💡The focus of Defender for Databases is security but the service has a split architecture to balance data uploading and speed with performance. Lab tests of the solution demonstrate CPU usage averaging 3% for peak slices, comparing it against benchmark loads.

Non-Azure SQL servers leverage the Azure Arc agent + Azure Monitor Agent + VM Extension (WindowsAgent.SqlServer), which will create an Azure resource for each discovered SQL Server instance.

🛡️Threat Protection:
Advanced Threat Protection provides an additional layer of security by providing security alerts on anomalous activities around authentication, SQL injection, and data exfiltration.

🔬Vulnerability Management:
SQL vulnerability assessment includes actionable steps to resolve security issues and enhance your database security reported as MDC Security Recommendations. The vulnerability assessment service scans your databases every 12 hours. Each database is randomly assigned a scan time on a set day of the week.

🔻Notes:
·       SQL Auditing is not required for Defender for Databases specifically but is still recommended for all production deployments of SQL server for additional auditing granularity and long-term log retention.
·       Defender for Databases for Arc-enabled SQL Servers is billed at $0.015/Core/Hour.
·       It must be enabled at the Subscription & Workspace level in MDC Environmental Settings.

![Image](/assets/img/mdcdatabase.jfif)

🎒Resources:

SQL Vulnerabilities Checks: https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-database-vulnerability-assessment-rules?view=azuresql#authentication-and-authorization

SQL Security Alerts: https://learn.microsoft.com/en-us/azure/defender-for-cloud/alerts-reference#alerts-sql-db-and-warehouse

Azure Policy to deploy agent: https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/SQL/ArcMachineWithSQL_InstallArcEnabledExtension.json

Azure Policy to configure auditing: https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/SQL/SqlServerAuditing_Deploy.json

Azure Arc SQL: https://learn.microsoft.com/en-us/sql/sql-server/azure-arc/connect-at-scale?view=sql-server-ver16&tabs=azure%2Cwindows#connect-at-scale-using-the-automatic-arc-enabled-sql-server-registration-method-recommended

Setting SQL baselines: https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-sql-on-machines-vulnerability-assessment#set-a-baseline


