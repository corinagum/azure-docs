---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Beyond Identity Admin Console'
description: Learn how to configure single sign-on between Azure Active Directory and Beyond Identity Admin Console.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: CelesteDG
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: jeedes

---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Beyond Identity Admin Console

In this tutorial, you'll learn how to integrate Beyond Identity Admin Console with Azure Active Directory (Azure AD). When you integrate Beyond Identity Admin Console with Azure AD, you can:

* Control in Azure AD who has access to Beyond Identity Admin Console.
* Enable your users to be automatically signed-in to Beyond Identity Admin Console with their Azure AD accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Beyond Identity Admin Console single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Beyond Identity Admin Console supports **SP** initiated SSO.

## Add Beyond Identity Admin Console from the gallery

To configure the integration of Beyond Identity Admin Console into Azure AD, you need to add Beyond Identity Admin Console from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](../roles/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications** > **New application**.
1. In the **Add from the gallery** section, type **Beyond Identity Admin Console** in the search box.
1. Select **Beyond Identity Admin Console** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for Beyond Identity Admin Console

Configure and test Azure AD SSO with Beyond Identity Admin Console using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Beyond Identity Admin Console.

To configure and test Azure AD SSO with Beyond Identity Admin Console, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Beyond Identity Admin Console SSO](#configure-beyond-identity-admin-console-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Beyond Identity Admin Console test user](#create-beyond-identity-admin-console-test-user)** - to have a counterpart of B.Simon in Beyond Identity Admin Console that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](../roles/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications** > **Beyond Identity Admin Console** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

	a. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://admin.byndid.com/auth/saml/<azure-tenant-id>/sso/metadata.xml`

	b. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://admin.byndid.com/auth/?org_id=<bi-tenant-id>`

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier and Sign on URL. Contact [Beyond Identity Admin Console Client support team](mailto:support@beyondidentity.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Beyond Identity Admin Console application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Beyond Identity Admin Console application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name | Namespace  |  Source Attribute|
	| ---------------| --------------- | --------- |
	| immutableId | externalId | user.immutableId |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up Beyond Identity Admin Console** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user called B.Simon.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [User Administrator](../roles/permissions-reference.md#user-administrator).
1. Browse to **Identity** > **Users** > **All users**.
1. Select **New user** > **Create new user**, at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Display name** field, enter `B.Simon`.  
   1. In the **User principal name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Select **Review + create**.
1. Select **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use single sign-on by granting access to Beyond Identity Admin Console.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](../roles/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications** > **Beyond Identity Admin Console**.
1. In the app's overview page, select **Users and groups**.
1. Select **Add user/group**, then select **Users and groups** in the **Add Assignment** dialog.
   1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
   1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
   1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Beyond Identity Admin Console SSO

To configure single sign-on on **Beyond Identity Admin Console** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [Beyond Identity Admin Console support team](mailto:support@beyondidentity.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Beyond Identity Admin Console test user

In this section, you create a user called Britta Simon in Beyond Identity Admin Console. Work with [Beyond Identity Admin Console support team](mailto:support@beyondidentity.com) to add the users in the Beyond Identity Admin Console platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Azure AD single sign-on configuration with following options. 

* Click on **Test this application**, this will redirect to Beyond Identity Admin Console Sign-on URL where you can initiate the login flow. 

* Go to Beyond Identity Admin Console Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you click the Beyond Identity Admin Console tile in the My Apps, this will redirect to Beyond Identity Admin Console Sign-on URL. For more information, see [Azure AD My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Next steps

Once you configure Beyond Identity Admin Console you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
