---
title: 'Tutorial: Configure Workteam  for automatic user provisioning with Azure Active Directory | Microsoft Docs'
description: Learn how to configure Azure Active Directory to automatically provision and de-provision user accounts to Workteam.
services: active-directory
author: twimmers
writer: twimmers
manager: CelesteDG
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: thwimmer
---

# Tutorial: Configure Workteam  for automatic user provisioning

The objective of this tutorial is to demonstrate the steps to be performed in Workteam  and Azure Active Directory (Azure AD) to configure Azure AD to automatically provision and de-provision users and/or groups to Workteam.

> [!NOTE]
> This tutorial describes a connector built on top of the Azure AD User Provisioning Service. For important details on what this service does, how it works, and frequently asked questions, see [Automate user provisioning and deprovisioning to SaaS applications with Azure Active Directory](../app-provisioning/user-provisioning.md).
>

## Prerequisites

The scenario outlined in this tutorial assumes that you already have the following prerequisites:

* An Azure AD tenant.
* [A Workteam tenant](https://workte.am/pricing.html)
* A user account in Workteam  with Admin permissions.

## Assigning users to Workteam 

Azure Active Directory uses a concept called *assignments* to determine which users should receive access to selected apps. In the context of automatic user provisioning, only the users and/or groups that have been assigned to an application in Azure AD are synchronized.

Before configuring and enabling automatic user provisioning, you should decide which users and/or groups in Azure AD need access to Workteam. Once decided, you can assign these users and/or groups to Workteam  by following the instructions here:
* [Assign a user or group to an enterprise app](../manage-apps/assign-user-or-group-access-portal.md)

## Important tips for assigning users to Workteam 

* It is recommended that a single Azure AD user is assigned to Workteam  to test the automatic user provisioning configuration. Additional users and/or groups may be assigned later.

* When assigning a user to Workteam, you must select any valid application-specific role (if available) in the assignment dialog. Users with the **Default Access** role are excluded from provisioning.

## Setup Workteam  for provisioning

Before configuring Workteam  for automatic user provisioning with Azure AD, you will need to enable SCIM provisioning on Workteam.

1. Log in into [Workteam](https://app.workte.am/account/signin). Click **Organization settings** > **SETTINGS**.

	![Screenshot of the Workteam U I with the Organization settings and SETTINGS options called out.](media/workteam-provisioning-tutorial/settings.png)

2. Scroll to bottom and enable the provisioning capabilities of Workteam.

	![Screenshot of the bottom of the SETTINGS section with the S C I M User Provisioning gear icon called out.](media/workteam-provisioning-tutorial/icon.png)

3. Copy the **Base Url** and **Bearer Token**. These values will be entered in the **Tenant URL**and **Secret Token** field in the Provisioning tab of your Workteam application in the Azure portal.

	![Screenshot of the S C I M Settings dialog box with the BASE U R L and BEARER TOKEN text boxes called out.](media/workteam-provisioning-tutorial/scim.png)


## Add Workteam  from the gallery

To configure Workteam  for automatic user provisioning with Azure AD, you need to add Workteam  from the Azure AD application gallery to your list of managed SaaS applications.

**To add Workteam  from the Azure AD application gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, in the left navigation panel, select **Azure Active Directory**.

	![The Azure Active Directory button](common/select-azuread.png)

2. Go to **Enterprise applications**, and then select **All applications**.

	![The Enterprise applications blade](common/enterprise-applications.png)

3. To add a new application, select the **New application** button at the top of the pane.

	![The New application button](common/add-new-app.png)

4. In the search box, enter **Workteam**, select **Workteam** in the results panel, and then click the **Add** button to add the application.

	![Workteam  in the results list](common/search-new-app.png)

## Configuring automatic user provisioning to Workteam  

This section guides you through the steps to configure the Azure AD provisioning service to create, update, and disable users and/or groups in Workteam  based on user and/or group assignments in Azure AD.

> [!TIP]
> You may also choose to enable SAML-based single sign-on for Workteam, following the instructions provided in the [Workteam Single sign-on tutorial](workteam-tutorial.md). Single sign-on can be configured independently of automatic user provisioning, though these two features compliment each other

### To configure automatic user provisioning for Workteam  in Azure AD:

1. Sign in to the [Azure portal](https://portal.azure.com). Select **Enterprise Applications**, then select **All applications**.

	![Enterprise applications blade](common/enterprise-applications.png)

2. In the applications list, select **Workteam**.

	![The Workteam  link in the Applications list](common/all-applications.png)

3. Select the **Provisioning** tab.

	![Screenshot of the Manage options with the Provisioning option called out.](common/provisioning.png)

4. Set the **Provisioning Mode** to **Automatic**.

	![Screenshot of the Provisioning Mode dropdown list with the Automatic option called out.](common/provisioning-automatic.png)

5. Under the Admin Credentials section, input the **Base URL** and **Bearer Token** values retrieved earlier in **Tenant URL** and **Secret Token** respectively. Click **Test Connection** to ensure Azure AD can connect to Workteam. If the connection fails, ensure your Workteam account has Admin permissions and try again.

	![Tenant URL + Token](common/provisioning-testconnection-tenanturltoken.png)

6. In the **Notification Email** field, enter the email address of a person or group who should receive the provisioning error notifications and check the checkbox - **Send an email notification when a failure occurs**.

	![Notification Email](common/provisioning-notification-email.png)

7. Click **Save**.

8. Under the **Mappings** section, select **Synchronize Azure Active Directory Users to Workteam**.

	![Workteam User Mappings](media/workteam-provisioning-tutorial/usermapping.png)

9. Review the user attributes that are synchronized from Azure AD to Workteam  in the **Attribute Mapping** section. The attributes selected as **Matching** properties are used to match the user accounts in Workteam  for update operations. Select the **Save** button to commit any changes.

	![Workteam  User Attributes](media/workteam-provisioning-tutorial/userattribute.png)

11. To configure scoping filters, refer to the following instructions provided in the [Scoping filter tutorial](../app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).

12. To enable the Azure AD provisioning service for Workteam, change the **Provisioning Status** to **On** in the **Settings** section.

	![Provisioning Status Toggled On](common/provisioning-toggle-on.png)

13. Define the users and/or groups that you would like to provision to Workteam  by choosing the desired values in **Scope** in the **Settings** section.

	![Provisioning Scope](common/provisioning-scope.png)

14. When you are ready to provision, click **Save**.

	![Saving Provisioning Configuration](common/provisioning-configuration-save.png)

This operation starts the initial synchronization of all users and/or groups defined in **Scope** in the **Settings** section. The initial sync takes longer to perform than subsequent syncs. For more information on how long it will take for users and/or groups to provision, see [How long will it take to provision users](../app-provisioning/application-provisioning-when-will-provisioning-finish-specific-user.md#how-long-will-it-take-to-provision-users).

You can use the **Current Status** section to monitor progress and follow links to your provisioning activity report, which describes all actions performed by the Azure AD provisioning service on Workteam. For more information, see [Check the status of user provisioning](../app-provisioning/application-provisioning-when-will-provisioning-finish-specific-user.md). To read the Azure AD provisioning logs, see [Reporting on automatic user account provisioning](../app-provisioning/check-status-user-account-provisioning.md).

## Additional resources

* [Managing user account provisioning for Enterprise Apps](../app-provisioning/configure-automatic-user-provisioning-portal.md)
* [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

## Next steps

* [Learn how to review logs and get reports on provisioning activity](../app-provisioning/check-status-user-account-provisioning.md)
