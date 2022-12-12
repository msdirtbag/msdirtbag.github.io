---
layout: post
title: Defender for Endpoint Restrict App Execution
thumbnail-img: ./assets/img/mderse.jfif
---
👉Let’s discuss Defender for Endpoint’s Restrict App Execution Response Action:

If you are coming from another EDR, you probably have not had a response action like this in your toolkit before.

🔻Restrict App Execution can be enabled on 2016+ endpoints in the 365D portal, via the 365D API from SOAR solutions such as Logicapps, and via 365D Custom Detections rules. Within a few seconds, MDE activates a code integrity policy named ATPSiPolicy.p7b in the \Windows\System32\CodeIntegrity folder and the Windows OS kernel starts enforcing a Microsoft-only code integrity policy via Windows Defender Application Control. (The user is also notified)

This code integrity policy is very similar to WDAC Microsoft Only policy that can be generated with WDAC wizard.

🥷🏻This response action should terminate and prevent all non-Microsoft signed code from running. It won’t kill legitimate system binaries that have been process injected but it will kill most masquerading implants/beacons and is less disruptive than Selective/Full Isolation.

💡It’s also a great automated response action for high/critical alerts because it slows things down while the 5-10 min delay in processing happens and the SOC incident is assigned to an analyst. From there, the analyst can investigate and determine if the endpoint should be fully isolated or released from App Restriction.

⚔️Has live action been detected? Consider hitting Restrict App Execution on your Tier 0 infrastructure until everything is cleaned up. (It shouldn’t be running 3rd party code anyway because that breaks the Active Directory root of trust)

There is tons of great use-cases for Restrict App Execution so go experiment and share your favorites!

![Image](/assets/img/mderse.jfif)

🎒Resources:

Restrict App Execution: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/respond-machine-alerts?view=o365-worldwide

Matt Soseman’ demo: https://www.youtube.com/watch?v=DBQOUQMYEBw

API: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/restrict-code-execution?view=o365-worldwide


