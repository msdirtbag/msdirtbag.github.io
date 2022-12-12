---
layout: post
title: Most Common Defender for Endpoint question
---
Our management purchased MDE but I don’t understand where to apply policy to server/workstation groups of devices. Where do I create AV/EDR polices in the Microsoft Security fabric?

👉MDE for Windows is made by Microsoft, which is the OS manufacturer, so it is unlike every other 3rd party agent-based EDR/NGAV solution you may be familiar with. This can create implementation challenges and long-term holistic endpoint security upside with proper care and feeding.

With MDE, the solution is “baked into” the kernel and uses existing plumbing to deliver NGAV/EDR functionality. It looks to the Windows Registry for policy settings that it needs to be resilient against threat actors TTP’s.

🚦These registry settings can be delivered via MDE Attach, ConfigMgr, Intune, PowerShell, Guest Configurations, and GPO. Each method has its own list of pros/cons/dependencies so the preferred solution varies on environmental variables.

🦾Key lessons learned by purple teaming MDE & MDE IR engagements:

·       Tamper Protection must be enabled for all endpoints in production

·       Local Admin Merge must be disabled by policy

·       Out-of-the-box Advanced Audit Policy creates "blind spots"

·       Network Protection must be enabled in block mode

·       All ASR rules should be enabled in audit/block/warn mode on all endpoints

·       Defender Firewall should be enabled and auditing Filtering Platform Packet Drop & Filtering Platform Connection

·       UAC must auto-deny elevation requests to prevent rundll32/fodhelper EDR unhooking
