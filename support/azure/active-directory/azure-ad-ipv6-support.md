--- 
title: IPv6 Support in Azure AD
description: Bringing IPv6 support to Azure Active Directory
ms.service: active-directory
ms.subservice: aad-general
ms.date: 11/22/2022
ms.author: v-dele
author: DennisLee-DennisLee
ms.reviewer: lhuangnorth, gautama, amycolannino, joflore
ms.collection: M365-identity-device-management
---

# IPv6 Support in Azure Active Directory

We're excited to bring IPv6 support to Azure Active Directory (Azure AD), to support customers with increased mobility, and help reduce spending on fast-depleting, expensive IPv4 addresses. For more information about how this change might affect Microsoft 365, see [IPv6 support in Microsoft 365 services](/microsoft-365/enterprise/ipv6-support).

If your organization's networks don't support IPv6 today, you can safely ignore this information until such time that they do.

## When will IPv6 be supported in Azure AD?

We'll begin introducing IPv6 support to Azure AD in late March 2023.

We know that IPv6 support is a significant change for some organizations. We're publishing this information now so that customers can make plans to ensure readiness.

## Support

If you have questions about this change or need help, we invite you to create a support request, or ask Azure community support.

## What does my organization have to do?

As Microsoft plans the rollout of IPv6 into Azure AD, we want to share changes that you might notice. These changes include some advantages and some changes you must make.

Customers who use Conditional Access location-based policies to restrict and secure access to their apps from specific networks have to:

- Identify egress IPv6 addresses in use in your organization
- [Create or update named locations, to include their identified IPv6 addresses](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)

Customers who have invested in Azure AD Identity Protection, using user and sign-in risk policies, will automatically benefit from the introduction of IPv6 to Azure AD.

--------------
### Azure Active Directory Per-user-MFA 

Customer using per user MFA, who have added IPv4 addresses representing on-premises trusted network (“Skip multi-factor authentication for requests from following range of IP address subnet”), may see MFA prompt for a request initiated via on-premises IPv6 enabled egress points. This MFA trusted IP list may also be used as a selected “location” condition, in Conditional policies.  

###Network with outbound traffic restricted: 

Get an updated list of IPv4, IPv6 addresses for Azure AD services referencing the articles below.  
Office 365 URLs and IP address ranges - https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#microsoft-365-common-and-office-online
Azure AD Connect: Troubleshoot Azure AD connectivity issues - https://learn.microsoft.com/en-us/azure/active-directory/hybrid/tshoot-connect-connectivity#troubleshoot-connectivity-issues-in-the-installation-wizard
Ensure outbound access to the IP ranges specified for Azure AD is allowed at Webproxy or firewall level. 


#### Device level configuration: 

By default, both IPv6 and IPv4 is supported on a Windows and most other OS platforms.  
Check if there is any configuration deployed via the OS image or AD DS group policy to disable IPv6. If disabled, OS may not use IPv6. 
https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/configure-ipv6-in-windows
--------------


### Azure AD B2C

Customers who [add Conditional Access to user flows in Azure Active Directory B2C](/azure/active-directory-b2c/conditional-access-user-flow?pivots=b2c-user-flow#add-a-conditional-access-policy) can follow the same process to [create or update named locations to include their identified IPv6 addresses](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).

## Next steps

We'll keep this article updated. Here's a short link you can use to come back for updated and new information: [https://aka.ms/azureadipv6](https://aka.ms/azureadipv6).

- [Using the location condition in a Conditional Access policy](/azure/active-directory/conditional-access/location-condition)
- [Conditional Access: Block access by location](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)
- [Find help and get support for Azure Active Directory](/azure/active-directory/fundamentals/how-to-get-support)

[!INCLUDE [Azure Help Support](../../includes/azure-help-support.md)] 

