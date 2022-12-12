---
layout: post
title: Does your organization use any Microsoft Cloud Services
thumbnail-img: ./assets/img/aadkey.jfif
---
⚡️Here’s the (3) most important Azure AD security controls (beyond requiring MFA & Disabling Legacy Auth) that affect your organization’s IAM security posture.

They can be found in the User Settings section of the Azure AD panel.

*This also affects organizations that use 3rd party IAM’s such as Centrify, SailPoint, Okta, and other IdP’s via the SAML 2.0, WS-Federation, or OpenID Connect Azure AD integrations.

👬1. “Users can register applications”
Background: This allows every user identity to give up it’s permissions to corporate resources via OAuth2 prompts via EvilGoPhish & others. From there, the threat actor/red-teamer is (2) scripts away from downloading the mailboxes that the victim identity has access to & internally-phishing the privileged users already identified during external recon via ROADtools.

Please do not allow this in production tenants. Download 365-Stealer and test your security controls. The Defender for Cloud Apps App Governance add-on works well to mitigate risk via policy controls. Sentinel LogicApps & Functions can help your security team quickly remediate this type of account compromise if this toggle cannot be disabled. (Risk Avoidance)

👀2. “Restrict access to Azure AD administration portal”
Background: Standard user accounts should not be able to go to portal.azure.com and read your organization’s Azure AD. When tokens are intercepted with tools like PRT viewer, that token can be rapidly replayed to enumerate Azure AD and map out identity-based attack paths to sensitive resources via tools such as AzureHound.

Please restrict access in all production tenants. Standard mail-enabled user accounts should not be allowed to enumerate every sensitive group membership in your corporate Azure AD.

⏰3. <New>“Show option to remain signed in”
Explanation: “The Azure AD sign-in flow gives users the option to remain signed in until they explicitly sign out. This doesn't change Azure AD session lifetime but allows sessions to remain active when users close and reopen their browser. Set this to "No" to hide this option from your users. The capability is only available on the default branding object and not on any language-specific one.”

![Image](/assets/img/aadkey.jfif)

🎒Resources:

365 Idle Session Timeout: https://learn.microsoft.com/en-US/microsoft-365/admin/manage/idle-session-timeout-web-apps

Configuring authentication session controls: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime

Conditional Access Evaluation: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-continuous-access-evaluation

MDA App Governance: https://learn.microsoft.com/en-us/defender-cloud-apps/app-governance-manage-app-governance

365-Stealer: https://github.com/AlteredSecurity/365-Stealer

PRT Viewer: https://github.com/secureworks/primary-refresh-token-viewer

ROADtools: https://github.com/dirkjanm/ROADtools

evilgophish: https://github.com/fin3ss3g0d/evilgophish

AzureHound: https://github.com/BloodHoundAD/AzureHound

TokenMan: https://github.com/secureworks/TokenMan
