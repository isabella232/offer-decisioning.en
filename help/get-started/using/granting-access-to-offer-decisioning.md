---
title: Grant access to Offer Decisioning
description: Learn how to manage users' permissions for the Offers Decisioning service via Adobe Admin Console.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner:
products:
audience: 
content-type: reference
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
internal: n
snippet: y
---

# Grant access to Offer Decisioning {#granting-acess-to-offer-decisioning}

Users' permissions for Offer Decisioning are managed using the Adobe Admin Console. For more details on the Admin Console itself, refer to the [dedicated documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).    

To grant access to the Offer Decisioning service, follow these steps:

1. Open the Admin Console, then select **[!UICONTROL Adobe Experience Platform]**. 

    ![](assets/offers_admin_console.png)

1. The product profiles for the service display. You can have as many product profiles as desired, corresponding to the various roles that you want to set up for your organization.

    To create a new product profile, click the **[!UICONTROL New Profile]** button. 

    ![](assets/offers_rights_productprofile.png)

1. Specify the product profile's name and description then click **[!UICONTROL Next]** To access the product profile’s permissions, select the **[!UICONTROL Permissions]** line.

    ![](assets/create-product-profile.png)

1. Select the services to enable for the product profile.

    By default, all services are selected, which is recommended to ensure that all the Experience Cloud functionalities are available.

    ![](assets/enable-services.png)

1. In the **[!UICONTROL Decisioning]** , click the **+** button to assign permissions to the product profile, then click **[!UICONTROL Save]**.

    ![](assets/configure-profile.png)

    Available permissions are:
    
    **[!UICONTROL Manage Decisioning Activities]**:
    
    * Read, write, delete offers
    * Read, write, delete activities
    * Read, write, delete placements

    **[!UICONTROL Execute Decisioning Activities]**:
    
    * Read offers
    * Read activities
    * Read placements
    
    **[!UICONTROL Manage Decisioning Options]**:

    * Read, write, delete offers
    * Read activities
    * Read, write, delete placements

1. A summary of the product profile's permissions displays. You can now assign users to the product profile so that they access these permissions.

    For more details on how to manage users permissions, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).    

    ![](assets/product-profile-created.png)
