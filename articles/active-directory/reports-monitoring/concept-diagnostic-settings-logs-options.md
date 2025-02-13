---

title: Logs available for streaming to endpoints from Azure Active Directory
description: Learn about the Azure Active Directory logs available for streaming to an endpoint for storage, analysis, or monitoring.
services: active-directory
author: shlipsey3
manager: amycolannino
ms.service: active-directory
ms.topic: conceptual
ms.workload: identity
ms.subservice: report-monitor
ms.date: 08/09/2023
ms.author: sarahlipsey
ms.reviewer: besiler

---

# Learn about the identity logs you can stream to an endpoint

Using Diagnostic settings in Azure Active Directory (Azure AD), you can route activity logs to several endpoints for long term retention and data insights. You select the logs you want to route, then select the endpoint.

This article describes the logs that you can route to an endpoint from Azure AD Diagnostic settings.

## Prerequisites

Setting up an endpoint, such as an event hub or storage account, may require different roles and licenses. To create or edit a new Diagnostic setting, you need a user who's a **Security Administrator** or **Global Administrator** for the Azure AD tenant.

To help decide which log routing option is best for you, see [How to access activity logs](howto-access-activity-logs.md). The overall process and requirements for each endpoint type are covered in the following articles. 

- [Send logs to a Log Analytics workspace to integrate with Azure Monitor logs](howto-integrate-activity-logs-with-azure-monitor-logs.md)
- [Archive logs to a storage account](howto-archive-logs-to-storage-account.md)
- [Stream logs to an event hub](howto-stream-logs-to-event-hub.md)
- [Send to a partner solution](../../partner-solutions/overview.md)

## Activity log options

The following logs can be sent to an endpoint. Some logs may be in public preview but still visible in the portal.

### Audit logs

The `AuditLogs` report capture changes to applications, groups, users, and licenses in your Azure AD tenant. Once you've routed your audit logs, you can filter or analyze by date/time, the service that logged the event, and who made the change. For more information, see [Audit logs](concept-audit-logs.md).

### Sign-in logs

The `SignInLogs` send the interactive sign-in logs, which are logs generated by your users signing in. Sign-in logs are generated by users providing their username and password on an Azure AD sign-in screen or passing an MFA challenge. For more information, see [Interactive user sign-ins](concept-all-sign-ins.md#interactive-user-sign-ins).

### Non-interactive sign-in logs

The `NonInteractiveUserSIgnInLogs` are sign-ins done on behalf of a user, such as by a client app. The device or client uses a token or code to authenticate or access a resource on behalf of a user. For more information, see [Non-interactive user sign-ins](concept-all-sign-ins.md#non-interactive-user-sign-ins).

### Service principal sign-in logs

If you need to review sign-in activity for apps or service principals, the `ServicePrincipalSignInLogs` may be a good option. In these scenarios, certificates or client secrets are used for authentication. For more information, see [Service principal sign-ins](concept-all-sign-ins.md#service-principal-sign-ins).

### Managed identity sign-in logs

The `ManagedIdentitySignInLogs` provide similar insights as the service principal sign-in logs, but for managed identities, where Azure manages the secrets. For more information, see [Managed identity sign-ins](concept-all-sign-ins.md#managed-identity-for-azure-resources-sign-ins).

### Provisioning logs

If your organization provisions users through a third-party application such as Workday or ServiceNow, you may want to export the `ProvisioningLogs` reports. For more information, see [Provisioning logs](concept-provisioning-logs.md).

### AD FS sign-in logs

Sign-in activity for Active Directory Federated Services (AD FS) applications are captured in this Usage and insight reports. You can export the `ADFSSignInLogs` report to monitor sign-in activity for AD FS applications. For more information, see [AD FS sign-in logs](concept-usage-insights-report.md#ad-fs-application-activity).

### Risky users

The `RiskyUsers` logs identify users who are at risk based on their sign-in activity. This report is part of Azure AD Identity Protection and uses sign-in data from Azure AD. For more information, see [What is Azure AD Identity Protection?](../identity-protection/overview-identity-protection.md).

### User risk events

The `UserRiskEvents` logs are part of Azure AD Identity Protection. These logs capture details about risky sign-in events. For more information, see [How to investigate risk](../identity-protection/howto-identity-protection-investigate-risk.md#risky-sign-ins).

### Risky service principals

The `RiskyServicePrincipals` logs provide information about service principals that Azure AD Identity Protection detected as risky. Service principal risk represents the probability that an identity or account is compromised. These risks are calculated asynchronously using data and patterns from Microsoft's internal and external threat intelligence sources. These sources may include security researchers, law enforcement professionals, and security teams at Microsoft. For more information, see [Securing workload identities](../identity-protection/concept-workload-identity-risk.md)

### Service principal risk events

The `ServicePrincipalRiskEvents` logs provide details around the risky sign-in events for service principals. These logs may include any identified suspicious events related to the service principal accounts. For more information, see [Securing workload identities](../identity-protection/concept-workload-identity-risk.md)

### Enriched Microsoft 365 audit logs

The `EnrichedOffice365AuditLogs` logs are associated with the enriched logs you can enable for Microsoft Entra Internet Access. Selecting this option doesn't add new logs to your workspace unless your organization is using Microsoft Entra Internet to secure access to your Microsoft 365 traffic *and* you enabled the enriched logs. For more information, see [How to use the Global Secure Access enriched Microsoft 365 logs](../../global-secure-access/how-to-view-enriched-logs.md).

### Microsoft Graph activity logs

The `MicrosoftGraphActivityLogs` logs are associated with a feature that is still in private preview. The logs are visible in Azure AD, but selecting these options won't add new logs to your workspace unless your organization was included in the private preview.

### Network access traffic logs

The `NetworkAccessTrafficLogs` logs are associated with Microsoft Entra Internet Access and Microsoft Entra Private Access. The logs are visible in Azure AD, but selecting this option doesn't add new logs to your workspace unless your organization is using Microsoft Entra Internet Access and Microsoft Entra Private Access to secure access to your corporate resources. For more information, see [What is Global Secure Access?](../../global-secure-access/overview-what-is-global-secure-access.md).

## Next steps

- [Learn about the sign-ins logs](concept-all-sign-ins.md)
- [Explore how to access the activity logs](howto-access-activity-logs.md)
