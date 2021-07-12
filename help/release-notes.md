---
keywords: Offer Decisioning;release notes;popular topics
product: experience platform
title: Release notes
description: Learn about the new features and improvements for Offer Decisioning.
role: User
level: Intermediate
exl-id: 25079153-87f9-4535-b03f-d8977925a0a6
---
# Release notes {#release-notes}

This page lists all the new features and improvements for [!DNL Offer Decisioning].

You can also consult the latest documentation updates [here](documentation-updates.md).


## June 2021 Release {#june2021-release}

<table>
<thead>
<tr>
<th><strong>AI ranking</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>
AI ranking allows you to create different ranking strategies (based on your business goals) that will be used by a trained model system to rank the eligible offers to display for a given profile.</p>
<p>The use of AI ranking in Offer Decisioning is currently available in early access to select users only.</p>
<p>For more information, refer to the <a href="offer-library/create-ranking-strategies.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Asset publication</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>When configuring an offer's representations, if you add content from the Adobe Experience Cloud Assets library, the asset is now published in the offer creation flow. This prevents broken images when the offer is added to an email.</p>
<p>For more information, refer to the <a href="offer-library/creating-personalized-offers.md#representations">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Decision scope renaming</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>When creating a new decision (previously known as offer activity), the first steps consisting in adding placements to build the offer decision have been renamed as "decision scopes".</p>
<p>For more information, refer to the <a href="offer-activities/create-offer-activities.md#add-decision-scopes">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

## May 2021 Release {#may2021-release}

<table>
<thead>
<tr>
<th><strong>Placement selection in a decision</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The same placement can now be selected multiple times in a decision (previously known as offer activity).</p>
<p>For more information, refer to the <a href="offer-activities/create-offer-activities.md#add-decision-scopes">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

## April 2021 Release {#april2021-release}

<table>
<thead>
<tr>
<th><strong>New navigation in Offer Decisioning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The navigation in Offer Decisioning functionalities has been reorganized into two new menus: <b>Offers</b> and <b>Components</b>. Additionally, "Offer activities" have been renamed to "Decisions". You can now access them in the <b>Offers</b> menu > <b>Decisions</b> tab.</p>
</td>
</tr>
</tbody>
</table>

## March 2021 Release {#march-release}

<table>
<thead>
<tr>
<th><strong>Use a decision rule or a segment as a constraint in a decision</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>When creating a decision, you can now use a decision rule or a segment as a constraint to restrict the selection of the offers contained in a placement.</p>
<p>For more information, refer to the <a href="offer-activities/create-offer-activities.md#add-decisions">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Directly use a segment to determine an offer's eligibility</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now limit the selection of an offer to the members of one or several Adobe Experience Platform segments.</p>
<p>For more information, refer to the <a href="offer-library/creating-personalized-offers.md#eligibility">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Other improvements

Fixed an issue that could display the wrong eligibility rule applied to an offer when browsing an offer's details from the list.

Fixed an issue which prevented from specifying a **[!UICONTROL Public location]** or **[!UICONTROL Destination link]** in an offer representation if the URL exceeded 255 characters.

## February 2021 Release {#february-release}

<table>
<thead>
<tr>
<th><strong>Determining offers' selection using ranking formulas</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create <strong>ranking formulas</strong> and assign them to decisions. These are formulas that determine which offer should be selected first for a given placement in a decision, rather than taking into account the offers' priority scores.</p>
<p>For more information, refer to the <a href="offer-activities/configure-offer-selection.md">detailed documentation</a>.</p>
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

## January 2021 Release {#january-release}

Detailed information about an offer or a decision is now accessible by clicking its name in the list. [Read more](get-started/user-interface.md#information-pane-actions)

You can now vizualise all the changes that have been made to an offer or a decision using the **[!UICONTROL Change log]** tab. [Read more](get-started/user-interface.md#changes-log)

The offers and decisions lists now allow you to perform bulk actions on multiple elements. [Read more](get-started/user-interface.md#information-pane-actions)

You can now browse and filter available placements when configuring personalized and fallback offers representations. [Read more](offer-library/creating-personalized-offers.md)

You can now use the **[!UICONTROL Language]** drop-down list to select the language for an offer or decision's representation. [Read more](offer-library/creating-personalized-offers.md)

You can now duplicate offers and decisions to create copies with the "Draft" status. [Read more](get-started/user-interface.md#information-pane-actions)

Fixed an issue which prevented filters from working when selecting the channel and content type for a representation.

The message in the representation configuration screen has been made clearer to specify that content can only be drag and dropped from the left pane. [Read more](offer-library/creating-personalized-offers.md)

Fixed an issue which prevented from approving offers saved as drafts.

A new parameter in the APIs now allows you to return the top N offers for a given decision scope. [Read more](api-reference/getting-started.md)

A new parameter in the APIs now allows you to return the etag in the decision response, allowing you to keep track of version changes. [Read more](api-reference/getting-started.md)

A new parameter in the APIs now allows you to return the ranking score for an offer. [Read more](api-reference/getting-started.md)
