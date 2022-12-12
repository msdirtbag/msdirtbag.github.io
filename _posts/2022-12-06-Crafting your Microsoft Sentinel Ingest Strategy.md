---
layout: post
title: Crafting your Microsoft Sentinel Ingest Strategy
thumbnail-img: ./assets/img/mssecops.jfif
---
📝Key factors:

Monitoring estate: What needs security monitoring? What security platforms are already deployed? Where is the estate hosted? How will it look in 12/24 months?

Budget: Is Sentinel replacing an existing legacy or SasS SIEM solution? How was that solution managed/used? Is this a POC/specialized use case or full Enterprise deployment?

Maturity: What is the risk tolerance of the organization? Why are we deploying Sentinel? How advanced is the current security analytics/use case development?

📝Sentinel Log types:

Syslog/CEF/WEF (low quality)- These standardized log formats (kinda) have been traditionally used by on-prem security tools and aggregated in an on-prem SIEM. These components have high administration overhead due to tuning complexities and collector single points of failure.

API (medium quality)- This log type is based on serverless Azure Functions/LogicApps communicating with an externally exposed API’s via REST (or using ASE/Expressroute to private APIs) and pulling the logs in Log Analytics. Initial set-up can be complex for new API data sources, but maintenance is reasonable and tuning is highly-customizable.

Microsoft-native (high quality)- This includes default log types collected by 365 Defender, Defender for Cloud, Azure Monitor, and Azure diagnostic logs for Azure resources. Azure Diagnostic logs can surprise you in dynamic PaaS deployments but the rest are high impact/highly efficient when compared with the alternatives above and with 3rd party SIEM log collection standards.

📝Alerts vs Raw Logs:

Ingesting alerts from relevant security platforms via API & Microsoft-native integrations is always recommended because they generate minimal ingest cost/administration overhead and promote XDR visibility/SecOps via entity mapping. Alerts from CEF/Syslog may be worth ingesting depending on use-case.

💡Raw logs are where the points mentioned in Sentinel Log Types & Key Factors loom large. Strategy, sampling, and logical compromises are key.

For Enterprise deployments, the SOC needs Process, Command, Network, & File logs on everything. The quickest (and best) way to accomplish this is deploying MDE in active or passive mode on everything and activating the 365 Defender Data Connector in Sentinel. From there, sampling the remaining potential raw log data sources should give your Security Architects the data they need to decide which ones provide the most value for your SecOps program.

📝Strategy:

🔻Sort your data sources into the buckets above. Microsoft Sentinel deployments are never finished, they should continuously iterate because the Sentinel fabric is always evolving.

🔻If you plan a Waterfall-based deployment with no improvements until the SIEM solution gets re-evaluated in 3-5 years, you are doing it wrong.

🙏Allocate FTE hours/story points every year to maximize your Sentinel ROI. 

![Image](/assets/img/mssecops.jfif)