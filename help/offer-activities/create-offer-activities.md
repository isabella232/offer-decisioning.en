---
product: experience platform
title: Create decisions
description: Learn how to create decisions
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner:
products:
audience:
content-type: reference
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
internal: n
snippet: y
feature: Activities
role: User
level: Intermediate
exl-id: 80803cac-d33e-4693-bbd5-829e398861b5
---
# Create decisions {#create-offer-activities}

Decisions (previously known as offer activities) are containers for your offers that will leverage the Offer Decision Engine in order to pick the best offer to deliver, depending on the target of the delivery.

![](../assets/do-not-localize/how-to-video.png) [Discover this feature in video](#video)

The list of decisions is accessible in the **[!UICONTROL Offers]** menu / **[!UICONTROL Decisions]** tab. Filters are available to help you retrieve decisions according to their status or start and end dates.

![](../assets/activities-list.png)

Before creating a decision, make sure that the components below have been created in the Offer Library:

* [Placements](../offer-library/creating-placements.md)
* [Collections](../offer-library/creating-collections.md)
* [Personalized offers](../offer-library/creating-personalized-offers.md)
* [Fallback offer](../offer-library/creating-fallback-offers.md)

## Create the decision {#create-activity}

1. Access the decisions list, then click **[!UICONTROL Create activity]**.

1. Specify the decision's name as well as its start and end date and time, then click **[!UICONTROL Next]**.

    ![](../assets/activities-name.png)

## Add decision scopes {#add-decision-scopes}

1. Drag and drop a placement from the list to add it to the decision, then click **[!UICONTROL Add collection]**.

    ![](../assets/activities-placement.png)

    >[!NOTE]
    >
    >The same placement can be selected multiple times in the decision.


1. Select the collection that contains the offers to consider, then click **[!UICONTROL Add]**.

    ![](../assets/activities-collection.png)

1. The selected offers are added to the placement. In this example, we selected two offers that will display into a JSON-type placement aimed at presenting offers into a call center solution.

    ![](../assets/offers-added.png)

1. By default, if multiple offers are eligible for this placement, the offers with the highest priority score will be delivered to the customer.

    If you want to use a specific formula or a ranking strategy to choose which eligible offer to deliver, select it from the **[!UICONTROL Rank offers by]** drop-down list. For more on offer ranking methods, refer to [this section](../offer-activities/configure-offer-selection.md).

1. The **[!UICONTROL Constraint]** field restricts the selection of offers for this placement. This constraint can be applied by using a decision rule or one or several Adobe Experience Platform segments.

    To restrict the selection of the offers to the members of an Adobe Experience Platform segments, select **[!UICONTROL Segments]**, then click **[!UICONTROL Add segments]**.

    ![](../assets/activity_constraint_segment.png)
    
    Add one or several segments from the left pane, combine them using the **[!UICONTROL And]** / **[!UICONTROL Or]** logical operators, then click **[!UICONTROL Select]** to confirm.

    For more on how to work with segments, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

    ![](../assets/activity_constraint_segment2.png)

    If you want to add a selection constraint for this placement using a decision rule, select the **[!UICONTROL Decision rule]** option, then drag the desired rule from the left pane into the **[!UICONTROL Decision rule]** area. For more on how to create a decision rule, refer to [this section](../offer-library/creating-decision-rules.md). 

    ![](../assets/activity_constraint_rule.png)

## Add a fallback offer {#add-fallback}

Select the fallback offer that will be presented as a last resort to the customers that do not match the offers eligibility rules and constraints, then click **[!UICONTROL Next]**.

![](../assets/add-fallback-offer.png)

## Review and save the decision {#review}

If everything is configured properly, a summary of the decision properties displays. 

1. Make sure decision is ready to be used to  present offers to customers.
1. Click **[!UICONTROL Finish]**.
1. Then select **[!UICONTROL Save and activate]**.

    ![](../assets/save-activities.png)
    
    You can also save the decision as draft, in order to edit and activate it later on.

The decision displays in the list with the **[!UICONTROL Live]** or **[!UICONTROL Draft]** status, depending on whether you activated it or not in the previous step. 

It is now ready to be used to deliver offers to customers.

## Decision list {#decision-list}

From the decision list, you can select the decision to display its properties. From there you can also edit it, change its status (**Draft**, **Live**, **Complete**, **Archived**), duplicate the decision, or delete it.

![](../assets/decision_created.png)

Select the **[!UICONTROL Edit]** button to go back to the decision edition mode, where you can modify the decision's [details](#create-activity), [decision scopes](#add-decision-scopes) and [fallback offer](#add-fallback).

Select a live decision and click **[!UICONTROL Deactivate]** to set the decision status back to **[!UICONTROL Draft]**.

To set again the status to **[!UICONTROL Live]**, select the **[!UICONTROL Activate]** button that is now displayed.

![](../assets/decision_activate.png)

The **[!UICONTROL More actions]** button enables the actions described below.

![](../assets/decision_more-actions.png)

* **[!UICONTROL Complete]**: sets the decision's status to **[!UICONTROL Complete]**, meaning the decision cannot be called anymore. This action is only available for activated decisions. The decision is still available from the list, but you cannot set its status back to **[!UICONTROL Draft]** or **[!UICONTROL Approved]**. You can only duplicate, delete or archive it.

* **[!UICONTROL Duplicate]**: creates a decision with the same properties, decision scopes and fallback offer. By default, the new decision has the **[!UICONTROL Draft]** status.

* **[!UICONTROL Delete]**: removes the decision from the list.

    >[!CAUTION]
    >
    >The decision and its content will not be accessible anymore. This action cannot be undone.
    >
    >If the decision is used in another object, it cannot be deleted.

* **[!UICONTROL Archive]**: sets the decision status to **[!UICONTROL Archived]**. The decision is still available from the list, but you cannot set its status back to **[!UICONTROL Draft]** or **[!UICONTROL Approved]**. You can only duplicate or delete it.

You can also delete or change the status of multiple decisions at the same time by selecting the corresponding checkboxes.

![](../assets/decision_multiple-selection.png)

If you want to change the status of several decisions whith different statuses, only the relevant statuses will be changed.

![](../assets/decision_change-status.png)

Once a decision has been created, you can click its name from the list.

![](../assets/decision_click-name.png)

This enables you to access detailed information for that decision. Select the **[!UICONTROL Change log]** tab to [monitor all the changes](../get-started/user-interface.md#changes-log) that have been made to the decision.

![](../assets/decision_information.png)

## Tutorial video {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
