---
layout: post
title: Pivoting and lateral movement
thumbnail-img: ./assets/img/pivoting.jfif
---
Hybrid (AD + AAD) is the gateway to Digital Transformation but it does add risk. For the threat actor, hybrid is great because it includes all of the exploitable vulnerabilities of AAD/AD/ADFS in a bi-directional trust. AAD/ADFS is publicly exposed so you can discover everything with ROADtools and ADDInternals then pivot to legacy on-prem IAM (AD) that’s easy to pwn because it lets everyone in with user name/password.

Infosec pros that serve hybrid-connected orgs fear this and I’m here to say: “We haven’t seen a legit TA abuse this architecture directly at scale since the Solarwinds”. Is it a bad idea long-term? Absolutely but TA’s would rather find unlocked windows/doors vs build something elaborate that can be easily broken with Microsoft security update.

You must understand the market. I’ve never seen an IAB listing that says “hybrid-enabled” because it’s normally based on an RDP/WinRM/SQL exposed servers or phishing generated.

In the real world, we see a very different thing. We normally see pivoting from on-prem to cloud. We get the call after somebody sees a ransomware note and then we unwrap the details slowly. In those true dumpster-fire situations, we see something else:

We see cases where the TA’s lands a beacon on-prem or buys a IAB listing almost exclusively. When they pull the string, they normally end up getting everything they can that is connected to AD then hand it off to the negotiator.

Often, this means the TA ends up missing the Azure Infrastructure completely or only gets the AD-connected stuff. If they do find the Azure Infrastructure, they normally dump a GA that is synced via AD Connect and deploy their encryptor via Azure Automation and/or do the double tap on Azure Site Recovery because Resource Guard is not enabled then delete everything.

I’ve also seen several incidents where the cybersecurity team didn’t know that MDE was deployed via their Enterprise Scale Landing Zone MDC defaults and that mitigated the damage enough to enable “not paying”.

Assume breach is a lifestyle. Assume the TA already has complete control of your cloud stuff and the on-prem environment. How are you going to keep corporate services running when integrity and confidentiality is out the window and you are down to an availability fight?

![Image](/assets/img/pivoting.jfif)
