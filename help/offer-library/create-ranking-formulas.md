---
product: experience platform
solution: Experience Platform
title: Create ranking formulas
description: Learn how to create ranking formulas in Adobe Experience Platform.
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
---
# Create ranking formulas {#create-ranking-formulas}

## About ranking formulas {#about-ranking-formulas}

**Ranking formulas** allow you to define rules that will determine which offer should be presented first for a given placement, rather than taking into account the offers' priority scores.

Ranking formulas are expressed in **PQL syntax** and can leverage profile attributes, context data and offer attributes. For more on how to use the PQL syntax, refer to the [dedicated documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html).

Once a ranking formula has been created, you can assign it to a placement in a decision (previously known as offer activity). For more on this, see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md).

## Create a ranking formula {#create-ranking-formula}

To create a ranking formula, follow the steps below:

1. Access the **[!UICONTROL Components]** menu, then select the **[!UICONTROL Rankings]** tab.

1. Click **[!UICONTROL Create formula]** to create a new ranking formula.

    ![](../assets/ranking-create-formula.png)

1. Specify the ranking formula name, description, and formula.

    In this example, we want to boost the priority of all offers with the "hot" attribute if the actual weather is hot. To do this, the **contextData.weather=hot** was passed in the decisioning call.

    ![](../assets/ranking-syntax.png)

1. Click **[!UICONTROL Save]**. Your ranking formula is created, you can select it from the list to get details and edit or delete it.

    It is now ready to be used in a decision to rank eligible offers for a placement (see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md)).

    ![](../assets/ranking-formula-created.png)
