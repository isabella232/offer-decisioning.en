---
product: experience platform
title: Configure offers selection in decisions
description: Learn how to manage offers selection into decisions.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner:
products:
audience:
content-type: reference
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
internal: n
snippet: y
feature: Ranking Formulas
role: Business Practitioner
level: Intermediate
exl-id: 9ced0011-8000-4d87-b591-1587530acf73
---
# Configure offers selection in decisions {#offers-selection-in-activities}

If several offers are eligible for a given placement, you can choose the method that will select the best offer for each profile. When configuring a decision (previously known as offer activity), you can rank offers by:
* Offer priority
* Ranking formula
* AI ranking

![](../assets/offer-rank-by.png)

## Offer priority {#about-offers-priority}

By default, when several offers are eligible for a given placement, the offers with the highest **priority** will be delivered to the customers first.

![](../assets/offer-priority.png)

Offers' priority scores are assigned when creating an offer. Learn how to create a personalized offer in [this section](../offer-library/creating-personalized-offers.md).

## Ranking formula {#assign-ranking-formula}

In addition to offer priority, Offer Decisioning allows you to create **ranking formulas**. These are formulas that determine which offer should be presented first for a given placement, rather than taking into account the offers' priority scores.

For example, you can boost the priority of all offers where the end date is less than 24 hours from now, or boost offers from the "running" category if the profile's point of interest is "running". Learn how to create a ranking formula in [this section](../offer-library/create-ranking-formulas.md).

Once a ranking formula has been created, you can assign it to a placement in a decision (previously known as offer activity). To do this, follow the steps below:

1. Create a decision or edit an existing one. See [Create decisions](../offer-activities/create-offer-activities.md).

1. Add the placements that will contain your offers. See [Create placements](../offer-library/creating-placements.md).

1. For each placement, add a collection. See [Create collections](../offer-library/creating-collections.md).

1. Choose to rank offers by **[!UICONTROL Ranking]** from the drop-down list, then click **[!UICONTROL Add ranking]**.

    ![](../assets/offer-activity-ranking.png)

1. Select the desired ranking formula, then click **[!UICONTROL Select]**.

    ![](../assets/ranking-selection.png)

The ranking formula is now associated with the placement.

If mutiple offers are eligible to be presented in this placement, the decision will use the ranking formula to calculate which offer to deliver first.

## AI ranking {#use-ranking-strategy}

You can also use an trained model system that automatically ranks offers to display for a given profile by selecting a ranking strategy. Learn how to create a ranking strategy in [this section](../offer-library/create-ranking-strategies.md).

Once a ranking strategy has been created, you can assign it to a placement in a decision (previously known as offer activity). To do this this, follow the steps below:

1. Create a decision or edit an existing one. See [Create decisions](../offer-activities/create-offer-activities.md).

1. Add the placements that will contain your offers. See [Create placements](../offer-library/creating-placements.md).

1. For each placement, add a collection. See [Create collections](../offer-library/creating-collections.md).

1. Choose to rank offers by **[!UICONTROL AI ranking]** from the drop-down list.

    ![](../assets/ranking-selection-ai-ranking.png)

1. Click **[!UICONTROL Add ranking]**.

    ![](../assets/ranking-selection-ai-ranking-add.png)

1. Select the ranking strategy that you created. All the details of the ranking strategy are displayed.

    ![](../assets/ranking-selection-ai-ranking-selected.png)

1. Click **[!UICONTROL Select]**.

The ranking strategy is now associated with the placement.

If multiple offers are eligible, the trained model system will determine which offer should be presented first for a given placement.

<!--Result? Describe the impact for the user, i.e. what's the effect of selecting this ranking strategy for this collection/placement.-->

<!--Click **[!UICONTROL Next]** to confirm and save your decision.-->