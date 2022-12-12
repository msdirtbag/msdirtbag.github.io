---
layout: post
title: CWPP for On-prem Servers?
thumbnail-img: ./assets/img/mdcmdealert.jfif
---
Q: Does the Cloud Workload Protection Platform features in Defender for Cloud improve security operations for on-prem workloads❓

While MDC’s Defender for Servers includes the Defender for Endpoint EDR/NGAV, it is a much larger security monitoring and governance platform.

👀Visibility:

MDC uses the Azure Connected Machine agent and Azure Monitor Agent so it can collect non-EDR logs such as SQL audit logs, IIS logs, file-based LOB application logs and filter them with AMA XPath configurations and pre-ingest transformational Data Collection Rules before they arrive in the Log Analytics Workspace that powers MDC and can be shared with Microsoft Sentinel.

🎯Detection:

MDC adds additional detections to MDE native & custom detections. You can tell the difference by reviewing the Security Alerts page and alert source. (pictured)

Many of these detections are high fidelity alerts that detect offensive activity that MDE does not alert on by default.

My favorites:
·       A logon from a malicious IP has been detected
·       Communication with suspicious domain identified by threat intelligence
·       Detected encoded executable in command line data
·       Detected suspicious commandline used to start all executables in a directory
·       Detected suspicious network activity
·       Fileless attack technique detected
·       Malicious SQL activity
·       Successful brute force attack
·       Suspect integrity level indicative of RDP hijacking

MDC deployments also can report and enforce Advanced Audit Policy via Machine Configurations. Advanced Audit Policy affects MDI, MDE, and Sentinel detections because if the Event ID is never created, security tools will never see the conduct and generate an security alert.

⚔️Response:

The SOAR capabilities of Azure Functions and LogicApps are limitless when combined with Azure Automation hybrid runbook workers that can automate security responses in on-prem Firewalls, NACs, and hypervisors. You don’t have to spend ¼ of the SecOps budget on a 3rd party SOAR platform that requires specialized administrators to manage the playbooks. You can spend a few hundred dollars a month on the specific SOAR use-cases that your security team identifies as they come up.

![Image](/assets/img/mdcmdealert.jfif)

🎒Resources:

Audit Policy Outcomes: https://learn.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-extend-data?view=o365-worldwide#advanced-security-auditing-on-windows-devices

Hybrid Runbook Worker: https://learn.microsoft.com/en-us/azure/architecture/hybrid/azure-automation-hybrid

Machine Configurations: https://learn.microsoft.com/en-us/azure/governance/machine-configuration/overview

AMA XPath queries: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/data-collection-rule-azure-monitor-agent?tabs=portal#filter-events-using-xpath-queries

AMA Transformational DCR’s: https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/data-collection-transformations#why-to-use-transformations

MDC Security Alert List: https://learn.microsoft.com/en-us/azure/defender-for-cloud/alerts-reference#alerts-windows

