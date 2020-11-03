---
keywords: Experience Platform;home;popular topics;offer decisioning;decisions;offers;deliver offers
solution: Experience Platform
title: Deliver offers
topic: API guide
description: Offer Decisioning is a collection of services and UI programs that enables marketers to create and deliver end-user personalized offer experiences across channels and applications using business logic and decision rules.
---

# Deliver offers using the Decisions API

Offer Decisioning is a collection of services and UI programs that enables marketers to create and deliver end-user personalized offer experiences, across channels and applications using business logic and decision rules. An offer is a marketing message that may have rules associated with it that specify who is eligible to see the offer.

You can create and deliver offers by making a POST request to the [[!DNL Decisions]](https://www.adobe.io/apis/experienceplatform/home/api-reference.html#!acpdr/swagger-specs/decisioning-ode.yaml) API.

This tutorial requires that you have a unique placement ID and activity ID value available. If you have not acquired these values, see the tutorials for [creating a placement](../offers-api/placements/create.md) and [creating an activity](../activities-api/activities/create.md).

**API format**

```https
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/decisions
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/ode/` |
| `{CONTAINER_ID}` | The container where the activities are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Request**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/ode/e0bd8463-0913-4ca1-bd84-6309134ca1f6/decisions' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
  -d '{
        "xdm:dryRun": false,
        "xdm:propositionRequests": [
            {
                "xdm:placementId": "xcore:offer-placement:122204529514a2c0",
                "xdm:activityId": "xcore:offer-activity:122208b3a8740558"
            }
        ],
        "xdm:profiles": [
            {
                "xdm:validateContextData": false,
                "xdm:identityMap":{
                    "Email":[
                        {
                            "xdm:id": "lilymass@google1.com"
                        }
                    ]
                },
                "xdm:profileModel": "_xdm.context.profile"
            }
        ],
        "xdm:responseFormat": {
            "xdm:includeContent": true,
            "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ]
        }
        }
    }'
```

| Property | Description | Example |
| -------- | ----------- | ------- |
| `xdm:dryRun` | A boolean value that tells the offer decision engine whether the call being made is a trial run or not. If dry run is set to `true`, the decision engine doesn't affect the caps related to the option. | `true`, `false` |
| `xdm:propositionRequests` | An array that contains the placement and activity identifiers. | `xcore:offer-placement:122204529514a2c0`, `xcore:offer-activity:122208b3a8740558` |
| `xdm:profiles` | An array that contains the identity map and context data for each of the profiles. For an API request this will contain one profile. |
| `xdm:profiles.xdm:identityMap` | An array that contains a set of end user identities based on the namespace integration code of the identity. The identity map can carry more than one identity of each namespace. For more information on namespaces, see the [Identity namespace overview](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html). | `Email: [{xdm:id: lilymass@google1.com}]` |
| `xdm:responseFormat` | A set of flags that formats the response content. |
| `xdm:responseFormat.xdm:includeContent` | A boolean value that, if set to `true`, includes content to the response. | `text`, `html block`, `image link` |
| `xdm:responseFormat.xdm:includeMetadata` | An object that is used to specify what metadata is returned. If this property is not included, then `xdm:id` and `repo:etag` are returned by default. | `name` |

**Response**

A successful response returns information on your proposition, including its unique `xdm:propositionID`.

```json
{
    "xdm:propositionID": "2347f8a4-ebf7-45ae-ac75-10d7d91497e1",
    "xdm:propositions": [
        {
            "xdm:activity": {
                "xdm:id": "xcore:offer-activity:122208b3a8740558",
                "repo:etag": "4"
            },
            "xdm:placement": {
                "xdm:id": "xcore:offer-placement:122204529514a2c0",
                "repo:etag": "3"
            },
            "xdm:options": [
                {
                    "xdm:id": "xcore:personalized-offer:12331b9dc92aa2f6",
                    "repo:etag": "7",
                    "xdm:characteristics": {
                        "product": "savings",
                        "region": "NA"
                    },
                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-imagelink",
                    "dc:format": "image/jpeg",
                    "xdm:deliveryURL": "https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec"
                }
            ]
        }
    ],
    "xdm:factors": {
        "xdm:numberOfIneligibleOffers": "2"
    },
    "ode:createDate": 1604011243807
}
```

| Property | Description | Example |
| -------- | ----------- | ------- |
| `xdm:propositionID` | The identity for the proposition entity associated with an XDM DecisionEvent. | `2347f8a4-ebf7-45ae-ac75-10d7d91497e1` |
| `xdm:propositions` | The schema for a single decision activity proposition. Multiple options could be returned for the activity. If no options can be found, then the activity's fallback offer is returned. There will always be either an `options` property or a `fallback` property present. |
| `xdm:propositions.xdm:options` | The schema for a single option. If present, this property cannot be empty. |
| `xdm:propositions.xdm:options.@type` | Defines the type of the component. `@type` acts as tee processing contract for the client. When the experience is assembled, the composer will look for the component(s) that have a specific type. | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:options.dc:format` | The physical or digital manifestation of the resource. Typically, format should include the media-type of the resource. The format may be used to determine the software, hardware or other equipment needed to display or operate the resource. It is recommended to select a value from a controlled vocabulary, for example, the list of [Internet Media Types](http://www.iana.org/ assignments/media-types/) defining computer media formats. | `image/jpeg`, `image/png` |
| `xdm:propositions.xdm:options.xdm:deliveryURL` | Provides the URL for the option. | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `xdm:factors` | Defines a map containing different factors that affected the propositions made, for example, responses from the profile service. |
| `ode:createDate` | The time when the decision response message was created. This is represented as epoch time. | `1604011243807` |