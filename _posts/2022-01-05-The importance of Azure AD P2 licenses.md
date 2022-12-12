---
layout: post
title: The importance of Azure AD P2 licenses
thumbnail-img: ./assets/img/aadp2.jfif
---
Q: Do we need Azure AD P2 Licenses if we have other identity-based security tools?

A: If you are using Microsoft 365 or Azure in any way, you need some Azure AD P2 licenses.

🔻1st- Privileged accounts- If the identity has Security Reader+ in Azure AD roles or Contributor+ in Azure Resource roles, it needs the additional security controls provided by AAD Identity Protection and it needs to activate it’s Eligible permissions in Azure AD Privileged Identity Management.

🔻2nd- Non-user accounts that power integrations, managed services, and can read sensitive data.

🔻3rd- Standard user accounts that have Exchange Online, Teams, SharePoint access.

💡Why? Because security outcomes matter!

👉Azure AD Identity Protection- In my classes, I like to refer to it as “robots for good” but it’s really just UEBA-informed post-auth adaptive access controls.

🤔 Anomalous Token: This detection indicates that there are abnormal characteristics in the token such as an unusual token lifetime or a token that is played from an unfamiliar location. This detection covers Session Tokens and Refresh Tokens. The exact detection thresholds are not published so YMMV but it is your best chance to catch token replay games.

😅 Token Issuer Anomaly: This detection is low-volume and will be seen infrequently by most organizations. However, when it does occur it's high risk and users should be remediated.

😷 Possible attempt to access Primary Refresh Token (PRT): This risk detection type is detected by Microsoft Defender for Endpoint (MDE). A Primary Refresh Token (PRT) is a key artifact of Azure AD authentication on Windows 10, Windows Server 2016, and later versions, iOS, and Android devices. A PRT is a JSON Web Token (JWT) that's specially issued to Microsoft first-party token brokers to enable single sign-on (SSO) across the applications used on those devices. Attackers can attempt to access this resource to move laterally into an organization or perform credential theft. This detection will move users to high risk and will only fire in organizations that have deployed MDE. This detection is low-volume and will be seen infrequently by most organizations. However, when it does occur it's high risk and users should be remediated.

![Image](/assets/img/aadp2.jfif)

🎒Resources:

Graph Risk API: https://learn.microsoft.com/en-us/graph/api/resources/riskdetection?view=graph-rest-1.0

Azure AD IDP: https://learn.microsoft.com/en-us/azure/active-directory/identity-protection/overview-identity-protection

365D AAD IDP: https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/identity-protection-alerts-now-available-in-microsoft-365/ba-p/3660997

Conditional Access Evaluation: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-continuous-access-evaluation




