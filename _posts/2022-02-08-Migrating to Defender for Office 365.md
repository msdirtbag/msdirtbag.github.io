---
layout: post
title: Migrating to Defender for Office 365
thumbnail-img: ./assets/img/mdoeop.jfif
---
Q: How do we replace ProofPoint/Mimecast with Defender for Office 365?

A: Both of those Postini clones are excellent and highly effective at what they do.

📣If you want to understand MDO, the last 10 years of 365 is very important. When I found it, it was “Exchange Forefront Protection” for your on-prem Exchange Servers and Exchange Online but it has matured over the last 10 years.

From Microsoft, there are (2) products for email security solutions currently:

·       Exchange Online Protection- Spam focused and uses explicit mail-flow rules for most functionality.

·       Defender for Office 365- Security focused and uses Machine Learning to detect questionable emails that EOP failed to flag with atomic detections.

⚔️From a cybersecurity perspective, EOP and MDO are available for every Threat Actor that can activate a 365 trial license. Realistically, MDO and EOP are the most bypassed email filters on earth because of the availability factor. It’s a cat & mouse game that Microsoft wins more often than not but there are no promises.

Defender for Office 365 is a machine learning-based email filter so it's excellent in an XDR security context but it is not designed to be a hard allow/block email gateway. To successfully train MDO, feedback loops at the user and admin level are key.

🛡️The best way to think about Defender for Office 365 is a “Machine Learning Add-on” to Exchange Online Protection. By leveraging Spoof Intelligence & Mailbox Intelligence, it has the ability to detect anomalous email patterns that Exchange Online Protection would have missed.

·       Is MDO going to reliably prevent phish emails from arriving in the finance department’s mailboxes? Evaluate & decide

·       Is MDO comparable for managing mail flow with Mimecast, Proofpoint, or Cisco Email Security? Evaluate & decide

🔬Is MDO a goldmine of juicy security bits for orgs that use Exchange Online? Absolutely. EmailPostDeliveryEvents & UrlClickEvents are chronically underrated for detection use cases.

If you wish to consolidate Mimecast and Proofpoint out of the stack, you must teach your email admins to start doing policy in EOP/MDO 1st before the MX record is changed and support them with dedicated training time. You must get them a test email domain and 365 dev tenant to experiment with.

📧I typically advise clients to assume that MDO is a security-focused add-on to their current 365 mail flow that has the potential to displace ProofPoint/Mimecast once adoption, feedback, and migration is complete.

![Image](/assets/img/mdoeop.jfif)
