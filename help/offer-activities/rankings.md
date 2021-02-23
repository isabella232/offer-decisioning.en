---
product: experience platform
title: Configure offers selection in activities
description: Learn how to manage offers selection into activities.
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

# Configure offers selection in activities {#offers-selection-in-activities}

By default, when several offers are eligible for a given placement, the offers with the highest **priority** will be delivered to the customers first. Offers' priority scores are assigned when creating an offer (see [Create a personalized offer](../offer-library/creating-personalized-offers.md)).

![](../assets/offer-priority.png)

Additionally, Offer Decisioning allows you to create **manual rankings**. These are formulas that determine which offer should be presented first for a given placement, rather than taking into account the offers' priority scores. For example, you can set up a manual ranking that will xxxx

![](../assets/manual-rankings-list.png)

## Create a manual ranking {#create-manuel-ranking}

To create a manual ranking, follow the steps below:

* Access the **[!UICONTROL Activities]** menu, then the **[!UICONTROL Manual rankings]** tab.

* All created manual rankings display here. Click **[!UICONTROL Create formula]** to create a new manual ranking.

    ![](../assets/ranking-create-formula.png)

* Specify the manual ranking name, description, and formula. 

    ![](../assets/ranking-syntax.png)

* Click **[!UICONTROL Save]**. Your manuel ranking is created, it can now be used in an offer activity to rank eligible offers for a placement.

    ![](../assets/ranking-formula-created.png)


## Assign a manual ranking to an offer activity {#assign-manuel-ranking}

To assign a manual ranking to a placement, follow the steps below:

* Create an offer activity or edit an existing one, then create the placements that will contain your offers (see [Create offer activities(../offer-activities/create-offer-activities.md)).

* For each placement, select **[!UICONTROL Custom ranking]** from the drop-down list, then click **[!UICONTROL Add ranking]**.

    ![](../assets/offer-activity-ranking.png)

* Select the desired manual ranking, then click **[!UICONTROL Select]**.

    ![](../assets/ranking-selection.png)

The manual ranking is now associated to the placement. If mutiple offers are eligible to be presented in this placement, the offer activity will use the manual ranking's formula to calculate which offer to deliver first.