---
keywords: Offer Decisioning;release notes;popular topics
product: experience platform
title: Release notes
description: Learn about the new features and improvements for Offer Decisioning.
---

# Release notes {#release-notes}

This page lists all the new features and improvements for [!DNL Offer Decisioning].

You can also consult the latest documentation updates [here](documentation-updates.md).

## February 2021 Release {#february-release}

<table>
<thead>
<tr>
<th><strong>Determining offers' selection using manual rankings</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create <strong>manual rankings</strong> and assign them to offer activities. These are formulas that determine which offer should be presented first for a given placement in an offer activity, rather than taking into account the offers' priority scores.</p>
<p>For more information, refer to the <a href="offer-activities/rankings.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Export your offer catalog to Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Offer Decisioning now allows you to automatically export your offer catalog to Adobe Experience Platform as datasets. Each time an update is made to the offer catalog, a new export job is automatically executed to update the datasets.
</p>
<p>For more information, refer to the <a href="export-catalog/get-started-export.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mobile SDK support for Offers</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>xxxx</p>
</td>
</tr>
</tbody>
</table>

## January 2021 Release {#january-release}

Detailed information about an offer or an offer activity is now accessible by clicking its name in the list. [Read more](get-started/user-interface.md#information-pane-actions)

You can now vizualise all the changes that have been made to an offer or an offer activity using the **[!UICONTROL Change log]** tab. [Read more](get-started/user-interface.md#changes-log)

The offers and offer activities lists now allow you to perform bulk actions on multiple elements. [Read more](get-started/user-interface.md#information-pane-actions)

You can now browse and filter available placements when configuring personalized and fallback offers representations. [Read more](offer-library/creating-personalized-offers.md)

You can now use the **[!UICONTROL Language]** drop-down list to select the language for an offer or offer activity's representation. [Read more](offer-library/creating-personalized-offers.md)

You can now duplicate offers and offer activities to create copies with the "Draft" status. [Read more](get-started/user-interface.md#information-pane-actions)

Fixed an issue which prevented filters from working when selecting the channel and content type for a representation.

The message in the representation configuration screen has been made clearer to specify that content can only be drag and dropped from the left pane. [Read more](offer-library/creating-personalized-offers.md)

Fixed an issue which prevented from approving offers saved as drafts.

A new parameter in the APIs now allows you to return the top N offers for a given decision scope. [Read more](api-reference/getting-started.md)

A new parameter in the APIs now allows you to return the etag in the decision response, allowing you to keep track of version changes. [Read more](api-reference/getting-started.md)

A new parameter in the APIs now allows you to return the ranking score for an offer. [Read more](api-reference/getting-started.md)
