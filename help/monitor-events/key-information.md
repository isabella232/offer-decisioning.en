---
product: experience platform
solution: Experience Platform
title: Monitor Offer Decisioning events in Adobe Experience Platform
description: Learn how to monitor Offer Decisioning events in Adobe Experience Platform.
feature: Activities
role: Business Practitioner
level: Intermediate
exl-id: 2471c688-2309-4394-9d97-10ab3e8816a0
---
# Key information passed to Adobe Experience Platform

Each event that is sent has four key data points (in propositionDetails) that get automatically recorded for every decision that's made to.

SCREENSHOT


These proposition objects are made up of:

* Fallback
If a fallback is returned, name and id

* Placement
Placement name and ID and channel identifier

* Selections: what offer was selected.
-offer name (Decision Option Name)
-unique identifier for that (Decision Option Identifier) -_repo / Decision Option ETag:  unique ID d. So the selection is basically what offer was selected. 
* Activity
Activity name and identifier 


other key information:

* Timestamp

* identitiyMap: user identity
