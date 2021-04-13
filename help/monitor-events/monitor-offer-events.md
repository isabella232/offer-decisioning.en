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
# Monitor Offer Decisioning events in Adobe Experience Platform {#monitor-offer-events}

Customer Journey Management can automatically send offer decisioning performance data to Adobe Experience Platform so it can be combined with other data for analysis purposes.

Offer decisioning events are stored as datasets for the purpose of reporting or other things you would want to do with data stored in the data lake. By default, when the engine makes a decision or makes a decision for a given profile, events are automatically recorded. And it goes into this data set in AEP. Information in the dataset is automatically recorded for every single decision that gets made.

non profile dataset, like for journey events datasets. (Profile option unselected). Means it cannot be ingested into the profile. 

SCREENSHOT

The datasets are based the schema ODE DecisionEvents. dataset automatically created on provisioning for all instances.

SCREENSHOT

What we can do with these data: User can export it and do analysis in your own reporting systems and visualize it using their own tools. Can also leverage the query service, combine this with other tools and then use it in customer journey analytics. key is that the data gets automatically recorded into our data set in AEP so that the customer can export and do what they want to do with it. 
