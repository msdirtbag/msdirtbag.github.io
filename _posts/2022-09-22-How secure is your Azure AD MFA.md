---
layout: post
title: How secure is your Azure AD MFA
thumbnail-img: ./assets/img/GPSMFA.jfif
---
Hopefully you have MFA enabled for every account in your Azure AD tenant. Did you know that you get require GPS reads via Conditional Access?

·       Is Authenticator number matching enabled?
·       Is SMS MFA disabled?
·       Is Legacy Auth disabled for every service & user?

Fantastic! Let’s discuss a security control included in AAD P1 & P2 licensing that frustrates red-teamers and threat actors❗️

🎯While location is not generally accepted as a Factor category (something you know, something you have or something you are), it can be a powerful security control when leveraged properly.

🎤Prompting for GPS reads from the MS Authenticator app during MFA is problematic for threat actors. They can do some OSINT to figure out where the user should be coming from but it’s going to get logged as a data point that can that will stick out during investigation.(Even in Conditional Access Report-only mode)

🥷🏻The TA needs a clean device that has no traces to them. This dramatically increases attacker cost by complicating logistics into the “not worth it” & “find another way” category.

👇After running the audit config below for a few months, you should have the data you need to start creating Conditional Access Rules that enforce MFA GPS locations (Countries-only today, no geo-fencing yet!) for sensitive services and privileged security groups. 

👉Note- User Privacy Concerns: There are some but this is designed to be as “non-creepy” as possible. The exact locations are not surfaced in Azure AD sign-in logs by design. Can Microsoft Support and Law Enforcement retrieve them? The threat actor has to assume they can.

💡Most malicious threat actors do not want to dox themselves by giving up the exact GPS location of where they are actually working from. (bad opsec😉)

![Image](/assets/img/GPSMFA.jfif)

🎒Resources:

Conditional Access Named Location GPS: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/location-condition

Authenticator Location Permissions: https://support.microsoft.com/en-us/account-billing/common-questions-about-the-microsoft-authenticator-app-12d283d1-bcef-4875-9ae5-ac360e2945dd