---
keywords: Experience Platform;home;popular topics;offer decisioning;decisions;offers;deliver offers
solution: Experience Platform
title: Deliver offers
topic: API guide
description: An offer is a marketing message that may have rules associated with it that specify who is eligible to see the offer.
---

# Deliver offers using the Decisions API

Offer Decisioning is a collection of services and UI programs that enables marketers to create and deliver end-user personalized offer experiences across channels and applications using business logic and decision rules.

You can create and deliver offers by making a POST request to the [!DNL Decisions](https://www.adobe.io/apis/experienceplatform/home/api-reference.html#/) API and providing your placement and activity IDs.

**API format**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/decisions
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/ode/` |
| `{CONTAINER_ID}` | The container where the activities are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Request**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/ode/ab574eca-f7a9-38d0-b3d9-297376ca9ee2/decisions' \
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
| `xdm:dryRun` | description | example |
| `xdm:propositionRequests` | description | example |
| `xdm:profiles` | description | example |
| `xdm:responseFormat` | description | example |

**Response**

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