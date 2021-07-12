---
product: experience platform
solution: Experience Platform
title: Create decision rules
description: Learn how to create decision rules in Adobe Experience Platform.
feature: Activities
role: User
level: Intermediate
exl-id: 5d6b5ab4-6909-468d-bf71-bf575931509c
---
# Create decision rules {#creating-decision-rules}

You can create offer decision rules based on data available in Adobe Experience Platform. Decision rules determine to whom an offer can be shown.

For example, you can specify that you only want a 'Women's Winter Clothing Offer' to be shown when (Gender = 'Female') and (Region = 'Northeast').

![](../assets/do-not-localize/how-to-video.png) [Discover this feature in video](#video)

The list of created decision rules is accessible in the **[!UICONTROL Components]** menu.

![](../assets/decision_rules_list.png)

To create a decision rule, follow these steps:

1. Go to the **[!UICONTROL Rules]** tab, then click **[!UICONTROL Create rule]**.

    ![](../assets/offers_decision_rule_creation.png)

1. Name your rule and provide a description, then configure the rule according to your needs.
    
    To do this, the **Segment Builder** from Adobe Experience Platform is available to help you build the rule's conditions. For more on how to use it, refer to the [dedicated  documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en).
    
    In this example, the rule will target customers that have the "Gold" loyalty level.

    ![](../assets/offers_decision_rule_creation_segment.png)

    >[!NOTE]
    >
    >The Segment Builder provided to create decision rules presents some specificities compared to the one used with the **[!UICONTROL Audience Destinations]** service. For example, the **[!UICONTROL Segments]** tab is not available for use. However, the global process described in the Segment Builder documentation is still valid to build offers decisions rules.

1. Click **[!UICONTROL Save]** to confirm.

1. Once the rule is created, it displays in the rules list. You can select it to display its properties and edit or delete it.

    ![](../assets/rule_created.png)

## Tutorial video {#video}


>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)
