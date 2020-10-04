---
title: Inserting offer activitiinto email deliveries
description: Learn how to insert an offer activities into email deliveries.
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

# Inserting offer activities into email deliveries {#xxxx}

>[!NOTE]
>
>This feature is available for single-send and recurring email messages only. It is not available with transactional messages.

To insert an offer activity into an email delivery, follow these steps:

1. Open a new delivery in the Email Designer. Global concepts on email creation are detailed in [Campaign Standard documentation](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html).

1. Select the component in the email that will contain the offer activity, or drag a new one from the left pane:

    * To insert an **image** offer, drag an image content component at the location of your choice in the email structure, then select it.

        ![](assets/offers_insertimage.png)

    * To insert a **text** or **HTML** offer, drag and drop a structure component into the location of your choice of the email structure, then click the **[!UICONTROL Select a column]** button to select the component's column.

        ![](assets/offers_inserttexthtml.png)

1. Click the **[!UICONTROL Insert offer activity]** button.

    ![](assets/offers_inserting_email_1.png)

1. The offer activity is added to the component. You can now configure it using the dedicated menu that displays in the left pane. It allows you to configure the offer activity by selecting a placement, an offer collection, and a fallback offer.

    >[!NOTE]
    >
    >If the menu is not visible anymore, for example when clicking outside of the offer component, click the Offer button from the left pane to display it again.

    ![](assets/offers_offer_activity_pane.png)

    1. In the **[!UICONTROL Placements]** section, select the placement that will be used to present offers.

        >[!NOTE]
        >
        >Make sure to select placements that are compatible with the component type selected in the email structure (text / HTML / image).

    1. In the **[!UICONTROL Collections]** section, select the collection that contains the offers that you want to consider. For more on offers collections, see [](../../offer-library/using/creating-collections.md).

    1. In the **[!UICONTROL Fallback Offers]** section, select the fallback offer that will be presented to customers who are not eligible for the considered offers.

        ![](assets/offers_offerconfiguration.png)

1. Select the **[!UICONTROL Summary]** tab to visualize the offers that are considered, and the selected fallback offer.

    >[!NOTE]
    >
    >At this step, all offers matching the selected placement are displayed. The decision rule that has been associated to the offer is not yet taken into account.

    ![](assets/offers_offers_attributes_6.png)

1. Click the **[!UICONTROL Done]** button to confirm the offer activity configuration.

Once created, you can still edit the offer activity settings or visualize the summary directly from the **[!UICONTROL Offer settings]** menu.

You can now save, preview and send your delivery (see [](../../campaign-standard/using/sending-emails-with-offer-activities.md)).
