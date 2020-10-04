---
title: Granting access to Offer Decisioning
description: Learn how to manage users' permissions for the Offers Decisioning service via Adobe Admin Console.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
internal: n
snippet: y
---

# Granting access to Offer Decisioning {#granting-acess-to-offer-decisioning}

Users' permissions for Offer Decisioning are managed using the Adobe Admin Console. For more details on the Admin Console itself, refer to the [dedicated documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

To grant access to the Offer Decisioning service, follow these steps:

1. Open the Admin Console, then select the **[!UICONTROL Adobe Experience Platform Decisioning Service]** among the available products. 

    ![](assets/offers_admin_console.png)

1. The product profiles for the service display. You can have as many product profiles as desired, corresponding to the various roles that you want to set up for your organization.

    Select a product profile to access its permissions.

    ![](assets/offers_rights_productprofile.png)

1. In the **[!UICONTROL Permissions]** tab, make sure that at least one **[!UICONTROL Container]** is included for the profile.

1. To access the product profile’s permissions, select the **[!UICONTROL Permissions]** line.

    ![](assets/offers_rights_permissions.png)

1. Permissions that have been granted to the product profile display in the right section. Click the **+** button to add a permission to the list.

    ![](assets/offers_rights_addpermissions.png)

    Available permissions are:

    * **[!UICONTROL Read Offers]**: access existing offers, decision rules and tags.
    * **[!UICONTROL Write Offers]**: create or edit offers, decision rules and tags.
    * **[!UICONTROL Delete Offers]**: delete offers, decision rules and tags.
    * **[!UICONTROL Read Activities]**: access existing offer activities.
    * **[!UICONTROL Write Activities]**: create or edit offer activities.
    * **[!UICONTROL Delete Activities]**: delete offer activities.
    * **[!UICONTROL Read Placements]**: access existing placements.
    * **[!UICONTROL Write Placements]**: create or edit placements.
    * **[!UICONTROL Delete Placements]**: delete placements.

>[!NOTE]
>
>Make sure that all product profiles have at least the **[!UICONTROL Read Offer]**, **[!UICONTROL Read Placements]**, and **[!UICONTROL Read Activities]** permissions.
>
>You can then assign additional rights according to their roles (designing offers, creating placements, etc.).
