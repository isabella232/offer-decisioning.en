---
product: experience platform
solution: Experience Platform
title: Create personalized offers
description: Learn how to create personalized offers in Adobe Experience Platform.
feature: Activities
role: User
level: Intermediate
exl-id: 2471c688-2309-4394-9d97-10ab3e8816a0
---
# Create personalized offers {#creating-personalized-offers}

Before creating an offer, make sure that you created:

* A **placement** in which the offer will be displayed. See [Create placements](../offer-library/creating-placements.md)
* A **decision rule** that will define the condition under which the offer will be presented. See [Create decision rules](../offer-library/creating-decision-rules.md).
* One or several **tags** that you want to associate to the offer. See [Create tags](../offer-library/creating-tags.md).

![](../assets/do-not-localize/how-to-video.png) [Discover this feature in video](#video)

The list of personalized offers is accessible in the **[!UICONTROL Offers]** menu.

![](../assets/offers_list.png)

## Create the offer {#create-offer}

>[!CONTEXTUALHELP]
>id="od_offer_attributes"
>title="About offer attributes"
>abstract="With offer attributes, you can associate key value pairs with the offer for reporting and analysis purposes."
>additional-url="https://video.tv.adobe.com/v/329375" text="Watch demo video"

To create an **offer**, follow these steps:

1. Click **[!UICONTROL Create offer]**, then select **[!UICONTROL Personalized offer]**.

    ![](../assets/create_offer.png)

1. Specify the offer's name as well as its start and end date and time. You can also associate one or several existing tag(s) to the offer, allowing you to search and organize the Offer Library more easily.

    ![](../assets/offer_details.png)

    >[!NOTE]
    >
    >The **[!UICONTROL Offer attributes]** section allows you to associate key value pairs with the offer for reporting and analysis purposes.

## Configure the offer's representations {#representations}

An offer can be displayed at different places in a message: in a top banner with an image, as text in a paragraph, as an HTML block, etc. The more representations an offer has, the more opportunities exist to use the offer in different placement contexts.

To add one or multiple representations to your offer and configure them, follow the steps below.

1. For the first representation, start by selecting the **[!UICONTROL Channel]** that will be used.

    ![](../assets/channel-placement.png)

    Only the available placements for the selected channel display in the **[!UICONTROL Placement]** drop-down list.

1. Select a placement from the list, or use the button next to the **[!UICONTROL Placement]** drop-down list to browse all the placements.

    ![](../assets/browse-button-placements.png)

    Then you can still filter the placements according to their channel and/or content type. Choose a placement and click **[!UICONTROL Select]**.

    ![](../assets/browse-placements.png)

1. Add content to your representation.

    >[!NOTE]
    >
    >Only content corresponding to the placement's content type is available for use.
    
    * If the selected placement is image-type, you can add content coming from the Adobe Experience Cloud Asset library, a centralized repository of assets provided by [!DNL Adobe Experience Manager Assets Essentials].

        >[!NOTE]
        >
        > To work with [Adobe Experience Manager Assets Essentials](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html?lang=en){target="_blank"}, you need to deploy [!DNL Assets Essentials] for your organization and make sure that users are a part of the **Assets Essentials Consumer Users** or/and **Assets Essentials Users** Product profiles. Learn more on [this page](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target="_blank"}.
    
        Choose the **[!UICONTROL Asset library]** option and select **[!UICONTROL Browse]**.

        ![](../assets/offer-browse-asset-library.png)

        Browse the assets to select the image of your choice and click **[!UICONTROL Select]**.

        ![](../assets/offer-select-asset.png)

        You can specify a **[!UICONTROL Destination link]** if you want to associate your content with a specific path.
    
        <!--either copying the path displayed in the **[!UICONTROL Public location]** field, either entering an URL in the corresponding field.-->

        ![](../assets/offer-destination-link.png)

    * To add content from an external public location, select **[!UICONTROL URL]**, then enter the URL address of the content to add.

        ![](../assets/offer-content-url.png)

    * You can also insert text-type content when selecting a compatible placement. Select the **[!UICONTROL Custom]** option and type the text that will display in the offer.

        ![](../assets/offer-text-content.png)

        >[!NOTE]
        >
        >This option is not available for image-type placements.

1. To add another representation, use the **[!UICONTROL Add representation]** button and add as many representations as needed.

    ![](../assets/offer-add-representation.png)

1. Once you added all your representations, select **[!UICONTROL Next]**.

## Add eligibility rules and constraints {#eligibility}

>[!CONTEXTUALHELP]
>id="od_offer_constraints"
>title="About offer constraints"
>abstract="With constraints, you can specify how the offer is prioritized and presented to the user compared to other offers."
>additional-url="https://video.tv.adobe.com/v/329375" text="Watch demo video"

>[!CONTEXTUALHELP]
>id="od_offer_eligibility"
>title="About offer eligibility"
>abstract="In this section, you can use decision rules to determine which users are eligible to the offer."
>additional-url="https://experienceleague.adobe.com/docs/offer-decisioning/using/managing-offers-in-the-offer-library/creating-decision-rules.html" text="Create decision rules"
>additional-url="https://video.tv.adobe.com/v/329373" text="Watch demo video"

>[!CONTEXTUALHELP]
>id="od_offer_priority"
>title="About offer priority"
>abstract="In this field, you can specify priority settings for the offer. Priority is a number used to rank offers that meet all constraints such as eligibility, dates, and capping."
>additional-url="https://video.tv.adobe.com/v/329375" text="Watch demo video"

>[!CONTEXTUALHELP]
>id="od_offer_globalcap"
>title="About offer capping"
>abstract="In this field, you can specify how many times the offer can be presented across all users."
>additional-url="https://video.tv.adobe.com/v/329375" text="Watch demo video"

Eligibility rules and constrains allow you to define the conditions under which an offer will be displayed.

1. Configure the **[!UICONTROL Offer eligibility]**. By default, the **[!UICONTROL All visitors]** decision rule option is selected, meaning that any profile will be eligible to be presented the offer.
    
1. You can limit the presentation of the offer to the members of one or several **Adobe Experience Platform segments**.

    To do this, activate the **[!UICONTROL Visitors who fall into one or multiple segments]** option, then add one or several segments from the left pane and combine them using the **[!UICONTROL And]** / **[!UICONTROL Or]** logical operators.

    For more on how to work with segments, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).
    
    ![](../assets/offer-eligibility-segment.png)

1. If you want to associate a specific **decision rule** to the offer, select **[!UICONTROL By defined decision rule]**, then drag the desired rule from the left pane into the **[!UICONTROL Decision rule]** area. For more on how to create a decision rule, refer to [this section](../offer-library/creating-decision-rules.md).

    ![](../assets/offer_rule.png)

    >[!CAUTION]
    >
    >Event-based offers are currently not supported in [!DNL Offer Decisioning]. If you create a decision rule based on an [event](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#events){target="_blank"}, you will not be able to leverage it in an offer.

1. Define the **[!UICONTROL Priority]** of the offer compared to other ones if the user qualifies for more than one offer. The higher an offer's priority will be, the higher its priority will be compared to other offers.

1. Specify the offer's **[!UICONTROL Capping]**, meaning the number of times the offer will be presented in total across all users. If the offer has been delivered across all users the number of times you have specified in this field, its delivery will stop.

    >[!NOTE]
    >
    >The number of times an offer is proposed is calculated at email preparation time. For example, if you prepare an email with a number of offers, those numbers count towards your max cap regardless of whether or not the email is sent.
    >
    >If an email delivery is deleted or if the preparation is done again before being sent, the capping value for the offer is automatically updated.

    ![](../assets/offer_capping.png)
        
    In the example above:

    * The offer's priority is set to "50", meaning the offer will be presented before offers with a priority between 1 and 49, and after the ones with a priority of at least 51.
    * The offer will be considered for users that match the "Gold Loyalty Customers" decision rule only.
    * The offer will be presented only once per user.

## Review the offer {#review}

Once eligibility rules and constraints have been defined, a summary of the offer properties displays.

1. Make sure everything is configured properly.

1. When your offer is ready to be presented to users, click **[!UICONTROL Finish]**.

1. Select **[!UICONTROL Save and approve]**.

    ![](../assets/offer_review.png)

    You can also save the offer as a draft, in order to edit and approve it later on. 

The offer displays in the list with the **[!UICONTROL Approved]** or **[!UICONTROL Draft]** status, depending on whether you approved it or not in the previous step.

It is now ready to be delivered to users.

## Offer list {#offer-list}
    
From the offer list, you can select the offer to display its properties. You can also edit it, change its status (**Draft**, **Approved**, **Archived**), duplicate the offer, or delete it.

![](../assets/offer_created.png)

Select the **[!UICONTROL Edit]** button to go back to the offer edition mode, where you can modify the offer's [details](#create-offer), [representations](#representations), as well as edit the [eligibility rules and constraints](#eligibility). 

Select an approved offer and click **[!UICONTROL Undo approve]** to set the offer status back to **[!UICONTROL Draft]**.

To set again the status to **[!UICONTROL Approved]**, select the corresponding button that is now displayed.

![](../assets/offer_approve.png)

The **[!UICONTROL More actions]** button enables the actions described below.

![](../assets/offer_more-actions.png)

* **[!UICONTROL Duplicate]**: creates an offer with the same properties, representations, eligibility rules and constraints. By default, the new offer has the **[!UICONTROL Draft]** status.
* **[!UICONTROL Delete]**: removes the offer from the list.

    >[!CAUTION]
    >
    >The offer and its content will not be accessible anymore. This action cannot be undone.
    >
    >If the offer is used in a collection or a decision, it cannot be deleted. You must remove the offer from any objects first.

* **[!UICONTROL Archive]**: sets the offer status to **[!UICONTROL Archived]**. The offer is still available from the list, but you cannot set its status back to **[!UICONTROL Draft]** or **[!UICONTROL Approved]**. You can only duplicate or delete it.

You can also delete or change the status of multiple offers at the same time by selecting the corresponding checkboxes.

![](../assets/offer_multiple-selection.png)

If you want to change the status of several offers whith different statuses, only the relevant statuses will be changed.

![](../assets/offer_change-status.png)

Once an offer has been created, you can click its name from the list.

![](../assets/offer_click-name.png)

This enables you to access detailed information for that offer. Select the **[!UICONTROL Change log]** tab to [monitor all the changes](../get-started/user-interface.md#monitoring-changes) that have been made to the offer.

![](../assets/offer_information.png)

## Tutorial video {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329375?quality=12)
