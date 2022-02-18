---
product: experience platform
solution: Experience Platform
title: Get started with Offer Decisioning events
description: Learn how to create Offer Decisioning reports in Adobe Experience Platform.
feature: Activities
role: User
level: Intermediate
exl-id: f0dae1c2-0981-4e22-8e4a-118e7a7d5014
---
# Get started with Offer Decisioning events {#monitor-offer-events}

Each time Offer Decisioning makes a decision for a given profile, information related to these events are automatically sent to Adobe Experience Platform.

This allows you to export these data to analyze them into your own reporting system. You can also leverage Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) in combination with other tools for enhanced analysis and reporting purposes.

The datasets containing Offer Decisioning events are accessible from Adobe Experience Platform **[!UICONTROL Datasets]** menu. One dataset is automatically created on provisioning for each of your instances.

![](../assets/events-datasets-list.png)

These datasets are based on the **[!UICONTROL ODE DecisionEvents]** schema, which contains all the XDM fields that are required to send information from Offer Decisioning to Adobe Experience Platform.  

>[!NOTE]
>
>Note that ODE DecisionEvents datasets are **non-profile datasets**, meaning that they cannot be ingested into Experience Platform for use by Real-time Customer Profile.

**Related topics:**

* [Offer Decisioning events key information](../reports/key-information.md)
* [Access events XDM fields](../reports/xdm-fields.md)
