---
layout: post
title: Doing more with less P2
thumbnail-img: ./assets/img/edrinblock.jfif
---
🔻Doing more when less = = Use what you have today

Do you have MDE P1/P2 licensing included in any of your current Microsoft licensing❓

M365 E5/G5, E5/G5 Security, E3/G3 and other plans include portions of MDE workstation licensing.

💡From Microsoft Learn Documentation:

“Suppose that your organization is using a mix of Microsoft endpoint security subscriptions, such as Defender for Endpoint Plan 1 and Defender for Endpoint Plan 2. Currently, the highest functional Microsoft endpoint security subscription sets the experience for your tenant. In this example, your tenant experience would be Defender for Endpoint Plan 2 for all users.

However, you can contact support and request an override for your tenant experience. That is, you could request an override to keep the Defender for Endpoint Plan 1 experience for all users.”

*Note: Most orgs do not have unused MDE Server licensing, but many have MDE workstation licensing that they are not using/aware of. Consult with your Microsoft Representative about what MDE entitlements you currently have.

Got another 3rd party AV/EDR agent already installed?

⚔️Defense in Depth with MDE's “EDR in Block mode” is broadly compatible with CrowdStrike Falcon, Carbon Black Defense, Cisco Secure-X, Trend Micro XDR, Sentinel One, Forticlient/FortiEDR, Palo XDR, Sophos Intercept-X, FireEye HX,etc.

MDE uses the “Windows Defender Advanced Threat Protection” Service that is built into modern Windows Kernels. It automatically switches to Passive Mode (Workstations only) when a 3rd party AV/EDR is installed.

🔥Benefits of adding MDE with 3rd party AV/EDR agents:

👉EDR in Block mode- MDE will not run Real Time Protection or signature inspect files as they are written to disk or loaded into memory. MDE can detect and remediate (if Full Automation is enabled) malicious TTP’s that were missed by the primary AV/EDR.

👉Conditional Access/Intune Device Compliance with MDE Risk Scores- Define and require acceptable device risk scores for sensitive/privileged corporate services. (see below)

👉Defender Threat & Vulnerability Management- Leverage Threat Analytics and Recommendations to focus on high-impact mitigations that improve cyber resilience.

👉Defender for Cloud Apps/DLP-IRM Integration- The MDE dataset is shared with Purview Data Loss Prevention and Insider Risk Management. Network telemetry is shared with MDA for CASB functionality.

👉M365D Response Actions- Restrict App Execution, Contain unmanaged Device, Isolate MDE Device, Live Response Shell, Disable user in AAD/AD, Revoke Sessions, and Force Password Reset.

👉Advanced Hunting & Custom Detections- KQL based Threat Hunting & SOAR response actions that contain damage.

![Image](/assets/img/edrinblock.jfif)

🎒Resources:

MDE Plans/licenses- https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-users-to-benefit-from-the-service-1

Mixed Licensing Scenario- https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1-2?view=o365-worldwide#mixed-licensing-scenarios

EDR in Block Mode: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/edr-in-block-mode?view=o365-worldwide

MDE Device Compliance Risk Scores: https://learn.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-windows#microsoft-defender-for-endpoint


