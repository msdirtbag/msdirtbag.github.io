---
layout: post
title: Windows DNS Events via AMA
thumbnail-img: ./assets/img/sentineldns.jfif
---
Who is using the Windows DNS Events via AMA Data Connector in Microsoft Sentinel❓

Organizations can monitor DNS logs to better understand network activity, and to identify suspicious behavior or attacks targeting resources within the network. The Windows DNS Events via AMA Sentinel data connector provides this type of visibility.

With the DNS Events connector, you can:
·       Identify clients that try to resolve malicious domain names.
·       View and monitor request loads on DNS servers.
·       View dynamic DNS registration failures. (Minimal security value and significant ingest cost)
·       Identify frequently queried domain names and talkative clients.
·       Identify stale resource records.
·       View all DNS related logs in one place.

This connector is fully normalized using Advanced Security Information Model (ASIM) parsers. The connector streams events originated from the analytical logs into the normalized table named ASimDnsActivityLogs. This table acts as a translator, using one unified language, shared across all DNS connectors to come.

📣Opinion:

By enabling the Windows DNS Event Data Connector on your AMA connected Domain Controllers, all of the Domain DNS flows into DNSEvents table in Log Analytics and you can use that table to power Sentinel Workbooks, Notebooks, Watchlists, and Analytic Rules. Start by collecting your DNS root DC’s 256 & 257 events first. Add additional DCs/App servers as ingest budgets permit.

💡Everything in IT depends on DNS and it remains the best CTI dataset for 15 years running. That’s why pDNS is still hyper-effective. 😉

![Image](/assets/img/sentineldns.jfif)

🎒Resources:

AMA Data Connector: https://learn.microsoft.com/en-us/azure/sentinel/connect-dns-ama

DNS Parser: https://learn.microsoft.com/en-us/azure/sentinel/dns-normalization-schema#unifying-parsers

Available Fields for Filtering: https://learn.microsoft.com/en-us/azure/sentinel/dns-ama-fields#available-fields-for-filtering
