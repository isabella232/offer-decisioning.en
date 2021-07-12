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

1. Add one or multiple representations for your offer using the **[!UICONTROL Add representation]** button.

    >[!NOTE]
    >
    >An offer can be displayed at different places in a message: in a top banner with an image, as text in a paragraph, as an html block etc. The more representations an offer has, the more opportunities exist to use the offer in different placement contexts.

1. For each representation, specify the **[!UICONTROL Channel]** and the **[!UICONTROL Placement]** where the offer will be displayed.

    ![](../assets/channel-placement.png)     

    The **[!UICONTROL Browse]** button allows you to filter available placements and filter them according to their channel and/or content type.
    
    ![](../assets/browse-placements.png)  

1. Add content to each representation coming from Adobe Experience Cloud Assets library or from an external public location.

    * To add content from Adobe Experience Cloud Assets library, drag and drop it from the left pane into the representation area, then specify the URL to associate with the content in the **[!UICONTROL Destination link]** field.

        >[!NOTE]
        >
        >Contents can only be dragged and dropped from the Asset Picker in the left panel. Only content corresponding to the placement's content type is available for use.

        ![](../assets/offer_drag_content.png)

    * To add content from an external public location, click the **[!UICONTROL Add content]** button, then specify the name, URL, and Destination link of the content to add.

        Make sure that the content you are adding corresponds to the selected placement's content type.

        ![](../assets/offer_add_content.png)

    * You can also insert text-type content. To do this, click the **[!UICONTROL Add content]** button, then select the **[!UICONTROL Custom text]** option. In the **[!UICONTROL Text]** field, type the text that will display in the offer.

        >[!NOTE]
        >
        >This option is not available for image-type placements.

        ![](../assets/offer_text_content.png)

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
    
    You can limit the presentation of the offer to the members of one or several Adobe Experience Platform segments. To do this, activate the **[!UICONTROL Visitors who fall into one or multiple segments]** option, then add one or several segments from the left pane and combine them using the **[!UICONTROL And]** / **[!UICONTROL Or]** logical operators.

    For more on how to work with segments, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).
    
    ![](../assets/offer-eligibility-segment.png)

    If you want to associate a specific decision rule to the offer, select **[!UICONTROL By defined decision rule]**, then drag the desired rule from the left pane into the **[!UICONTROL Decision rule]** area. For more on how to create a decision rule, refer to [this section](../offer-library/creating-decision-rules.md).

    ![](../assets/offer_rule.png)

1. Define the **[!UICONTROL Priority]** of the offer compared to other ones if the user qualifies for more than one offer. The higher an offer's priority will be, the higher its priority will be compared to other offers

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

Once eligibility rules and constraints have been defined, a summary of the offer properties displays. If everything is configured properly and your offer is ready to be presented to users, click **[!UICONTROL Finish]**, then select **[!UICONTROL Save and approve]**.

You can also save the offer as a draft, in order to edit and approve it later on. 

![](../assets/offer_review.png)

The offer displays in the list with the **[!UICONTROL Live]** or **[!UICONTROL Draft]** status, depending on whether you approved it or not in the previous step.

It is now ready to be delivered to users. You can select it to display its properties and edit or suppress it.

![](../assets/offer_created.png)

Once an offer has been created, you can click its name in the list to access detailed information, as well as monitor all the changes that have been made to it using the **[!UICONTROL Change log]** tab (see [Monitoring changes to offers and decisions](../get-started/user-interface.md#monitoring-changes)).

## Tutorial video {#video}


>[!VIDEO](https://video.tv.adobe.com/v/329375?quality=12)
