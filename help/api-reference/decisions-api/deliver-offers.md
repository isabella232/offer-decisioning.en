---
keywords: Experience Platform;home;popular topics;offer decisioning;decisions;offers;deliver offers
solution: Experience Platform
title: Deliver offers
topic: API guide
description: An offer is a marketing message that may have rules associated with it that specify who is eligible to see the offer.
---

# Deliver offers using the Decisions API

Offer Decisioning is a collection of services and UI programs that enables marketers to create and deliver end-user personalized offer experiences across channels and applications using business logic and decision rules.

## Create a single case class proposal schema


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
        "xdm:propositionRequests": [
            {
            "xdm:placementId": "xcore:offer-placement:ffed0456",
            "xdm:activityId": "xcore:offer-activity:ffed0123"
            },
            {
            "xdm:placementId": "xcore:offer-placement:ffed0012",
            "xdm:activityId": "xcore:offer-activity:fffc0789"
            }
        ],
        "xdm:profiles":[
            {
            "xdm:identityMap":{
                "SWCUSTID":[
                {
                    "xdm:id":"123@abc.com"
                },
                {
                    "xdm:id":"1233ce17-20e0-4a2c-8198-2a77fd60cf4d"
                }
                ]
            },
            "xdm:decisionRequestId":"0AA00002-0000-1337-c0de-c0fefec0fefe",
            "xdm:contextData": [
                {
                    "@type":"https://ns.adobe.com/xdm/context/placecontext;version=0",
                    "xdm:data":{
                        "xdm:localTime":"2001-07-04T12:08:56+01:00",
                        "xdm:geo":{
                            "@id":"https://data.adobe.io/entities/geo/tokyo",
                            "xdm:countryCode":"JP",
                            "xdm:stateProvince":"JP-13",
                            "xdm:city":"Tokyo",
                            "xdm:postalCode":"141-0032",
                            "schema:latitude":35.6185,
                            "schema:longitude":139.73237
                        }
                    }
                }
            ]
            }
        ],
        "xdm:allowDuplicatePropositions": {
            "xdm:acrossActivities": true,
            "xdm:acrossPlacements": true
        },
        "xdm:mergePolicy": {
            "xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"
        },
        "xdm:responseFormat": {
            "xdm:includeContent": true,
            "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ],
            "xdm:placement": [
                "name"
            ]
        }
    }
}'
```

**Response**

```json
{
  "xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8",
  "xdm:propositions":[
    {
      "xdm:activity":{
        "xdm:id":"xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement":{
        "xdm:id":"xcore:placement:ffed0456",
        "repo:etag": 1
      },
      "xdm:options":[
        {
          "xdm:id":"xcore:personalized-option:ccc0111",
          "repo:etag": 3,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<table border="0" width="641" height="168"><tbody><tr><td align="left" valign="top"><a href="https://www.adobe.com/experience-platform.html"><img src="https://cdn.adobe.com/content/1445323-3345322.png"/></a></td></tr></tbody></table>"
        }
      ]
    },
    {
      "xdm:activity":{
        "xdm:id":"xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement":{
        "xdm:id":"xcore:placement:ffed0789",
        "repo:etag": 2
      },
      "xdm:fallback":{
        "xdm:id":"xcore:fallback:ccc0222"
        "repo:etag": 5,
        "@type": "https://ns.adobe.com/experience/decisioning/content-component-imagelink",
        "dc:format": "image/png",
        "xdm:deliveryURL": "https://cdn.adobe.com/content/1445323-1134331.png",
        "xdm:content": "https://www.adobe.com/index2.html"
      }
    }
  ],
  "ode:createDate": 1566497582038
}
```