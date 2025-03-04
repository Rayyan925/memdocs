---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: This article describes Microsoft Intune features that are in development.
keywords:
author: dougeby 
ms.author: dougeby
manager: dougeby
ms.date: 01/25/2024
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals

# optional metadata

#audience:

ms.reviewer: lebacon
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection:
- tier1
- M365-identity-device-management
- highpri
- highseo
---

# In development for Microsoft Intune

To help in your readiness and planning, this article lists Intune UI updates and features that are in development but not yet released. Also:

- If we anticipate that you'll need to take action before a change, we'll publish a complementary post in the Office message center.
- When a feature enters production, whether it's in preview or generally available, the feature description will move from this article to [What's new](whats-new.md).  
- Refer to the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) for strategic deliverables and timelines.

This article and the [What's new](whats-new.md) article are updated periodically. Check back for more updates.

> [!NOTE]
> This article reflects our current expectations about Intune capabilities in an upcoming release. Dates and individual features might change. This article doesn't describe all features in development. It was last updated on the date shown under the title.

You can use RSS to be notified when this article is updated. For more information, see [How to use the docs](../../use-docs.md#notifications).
<!-- **RSS feed**: Find out when this article is updated by copying and pasting the following URL into your feed reader: `https://learn.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us` -->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Device security
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Tenant administration
## Notices
-->

<!-- ***********************************************-->

## App management  

### Intune migrating from SafetyNet Attestation API to Google Play Integrity API<!-- 15571389   -->  
Google has deprecated the [SafetyNet Attestation API](https://developer.android.com/training/safetynet/attestation) and replaced it with the [Play Integrity API](https://developer.android.com/google/play/integrity). Intune will be migrating to the new API for app protection policies. The "SafetyNet device attestation" setting name will be updated to align with the new Google Play Integrity API for all policies in the Intune user interface (UI). For related information, see [Discontinuing the SafetyNet Attestation API](https://developer.android.com/training/safetynet/deprecation-timeline) and [Migrating from the SafetyNet Attestation API](https://developer.android.com/google/play/integrity/migrate).

### Enterprise application management<!-- 10986080  -->  
Enterprise Application Management provides a catalog of prepackaged applications designed to simplify discovery, delivery, and updates for third and first party apps. Enterprise Application Management will be generally available in early Q1 2024.

### Company Portal automatically installed on Android Enterprise dedicated devices<!-- 6423852  -->  
Intune Company Portal will now be automatically installed on all Android Enterprise dedicated devices to ensure the appropriate handling of app protection policies. Users won't be able to see or launch the Company Portal, and there are no requirements for users to interact with it. Admins will notice that the Company Portal is automatically installed on their Android Enterprise dedicated devices, without the ability to uninstall.

### Support for multi-SIM iOS/iPadOS device inventory<!-- 17016690  -->  
You'll be able to view the service subscription fields on devices that have multiple SIM cards installed under the per-device Hardware section. The inventory fields that are capable of reporting multiple values to Intune are:

- **ICCID**
- **IMEI**
- **MEID**
- **Phone number**

These fields will default to using labels returned by the device, such as:  *Primary*, *Secondary*, *CTSubscriptionSlotOne*, and *CTSubscriptionSlotTwo*. These returned labels may be displayed in the language of the local device that is reporting its inventory to Intune.

Applies to:

- **iOS/iPadOS**

<!-- *********************************************** -->

## Device configuration

### Import up to 20 custom ADMX and ADML administrative templates<!-- 25780608  -->  
You can import custom ADMX and ADML administrative templates in Microsoft Intune. Currently, you can import up to 10 files.

You'll be able to upload 20 files.

For more information on this feature, go to [Import custom ADMX and ADML administrative templates into Microsoft Intune (public preview)](../configuration/administrative-templates-import-custom.md).

Applies to:

- Windows 10/11

### The macOS Company Portal app will support platform SSO (public preview)<!-- 24325427  -->  
In Intune, you can configure the Enterprise SSO plug-in on Apple devices using a device configuration profile (**Devices** > **Configuration** > **Create** > **macOS** for platform > **Settings Catalog** for profile > **Authentication** > **Extensible Single sign-on (SSO)**).

The Company Portal app version will support the platform SSO settings for macOS 13 and later. Platform SSO allows you to sync your Microsoft Entra ID password to local accounts on Macs using the Enterprise Single Sign-On extension.

For more information on the Enterprise SSO plug-in, go to:

- [Use Intune to deploy the Microsoft Enterprise SSO plug-in for Apple devices](../configuration/use-enterprise-sso-plug-in-ios-ipados-macos.md)
- [Entra ID and the Microsoft Enterprise SSO plug-in overview for Apple devices](/azure/active-directory/develop/apple-sso-plugin)

Applies to:

- macOS 13 and later

### Use assignment filters on Endpoint Privilege Management (EPM) policies<!-- 25230705   -->  
You can use assignment filters to assign a policy based on rules you create. A filter allows you to narrow the assignment scope of a policy, like targeting devices with a specific OS version or a specific manufacturer.

You can use filters on Endpoint Privilege Management (EPM) policies.

For more information about assignment filters, go to [Use filters when assigning your apps, policies, and profiles in Intune](filters.md).

Applies to:

- Windows 10/11

<!-- *********************************************** -->

## Device enrollment

### RBAC changes coming to enrollment settings for Windows Hello for Business<!-- 25661866   -->  
We're updating RBAC in the enrollment area for Windows Hello for Business. Enrollment settings related to Windows Hello for Business will be read-only for all roles except the Intune Service Administrator. The Intune Service Administrator will be able to edit enrollment settings.



<!-- *********************************************** -->

## Device management

### Introducing a remote action to pause the config refresh enforcement interval<!--24249019  -->  
In the Windows Settings Catalog, you can configure **Config Refresh**. This feature lets you set a cadence for Windows devices to reapply previously received policy settings, without requiring devices to check in to Intune. The device will replay and re-enforce settings based on previously received policy to minimize the chance for configuration drift.

To support this feature, a remote action will be added to allow a pause in action. If an admin needs to make changes or run remediation on a device for troubleshooting or maintenance, they can issue a pause from Intune for a specified period. When the period expires, settings will be enforced again.

The remote action **Pause config refresh** can be accessed from the device summary page.

For information on currently available Remote actions, see [Remote actions](../remote-actions/device-management.md).

<!-- *********************************************** -->

## Device security

### HTML formatting supported in noncompliance email notifications <!-- 24197255   -->  
HTML formatting will be supported in noncompliance email notifications for all platforms. You'll be able to use supported HTML tags to add formatting such as italics, URL links, and bulleted lists to your organization's messages.

### Support for Intune Device control policy for devices managed by Microsoft Defender for Endpoint<!-- 15466620, 25470154  -->  

You will be able to use the endpoint security policy for *Device control* (Attack surface reduction policy) from the Microsoft Intune with the devices you manage through the [Microsoft Defender for Endpoint security settings management](../protect/mde-security-integration.md) capability.
 
- **Device control** policies are part of endpoint security [Attack surface reduction policy](../protect/endpoint-security-asr-policy.md).

  Applies to:
  - Windows 10/11- - Available for the *Windows 10, Windows 11, and Windows Server* platform.
 
Prepare for February 2024. This policy change is expected to be released with the February 2024 service update for Intune. When this change takes effect, devices that are assigned this policy while managed by Defender for Endpoint but not enrolled with Intune, will now apply the settings from the policy. Check your policy to make sure only the devices you intend to receive this policy will get it.

<!-- *********************************************** -->

## Monitor and troubleshoot

### Battery report<!-- 9747162 -->  
We're working on a battery health report to provide visibility into the health of batteries in your organization’s devices and its influence on user experience. The scores and insights in this report are aimed to help IT admins with asset management and purchase decisions that improve user experience while balancing hardware costs.

The battery health report is a part of Microsoft Intune Advanced Analytics. It will be included as an Intune-add on under [Microsoft Intune Suite](../fundamentals/intune-add-ons.md) and requires an extra cost to the licensing options that include Microsoft Intune.

### Run on-demand pivot queries on single devices<!--16719466  -->  
Intune allows you to quickly gain on-demand information about the state of your device. When you enter a query on a selected device, Intune will run a query in real time. The data returned can then be used to respond to security threats, troubleshoot the device, or make business decisions.

This feature will be available as part of Microsoft Intune Advanced Analytics, which is available as part of Microsoft Intune Suite, or as an individual add-on. For more information, see [Microsoft Intune add-ons](../fundamentals/intune-add-ons.md).

Applies to:

- Windows devices

<!-- *********************************************** -->

<!-- ## Intune apps -->

<!-- *********************************************** -->

<!-- ## Role-based access control -->

<!-- *********************************************** -->

<!-- ## Tenant administration -->

<!-- *********************************************** -->

## Notices

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## See also

For details about recent developments, see [What's new in Microsoft Intune](whats-new.md).
