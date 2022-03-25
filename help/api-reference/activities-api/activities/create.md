---
keywords: Experience Platform;home;popular topics;offer decisioning;decisions;create decisions
product: experience platform
title: Create decisions
description: A decision contains the logic that informs the selection of an offer.
feature: API
role: Data Architect
level: Experienced
exl-id: 9a4f568b-d33c-46a6-a614-80722465e0e8
---
# Create a decision

You can create a decision (previously known as offer activity) by making a POST request to the [!DNL Offer Library] API, while providing your container ID.

## Accept and Content-Type headers

The following table shows the valid values which comprise the *Content-Type* and *Accept* fields in the request header:

| Header name | Value |
| ----------- | ----- |
| Accept | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"` |

**API format**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the decisions are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Request**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"' \
  -H 'Authorization: Bearer {{ACCESS_TOKEN}}' \
  -H 'x-api-key: {{API_KEY}}' \
  -H 'x-gw-ims-org-id: {{IMS_ORG}}' \
  -H 'x-sandbox-name: {{SANDBOX_NAME}}'
  -d '{
        "xdm:name": "Activity 1",
        "xdm:startDate": "2020-10-01T16:00:00Z",
        "xdm:endDate": "2021-12-13T16:00:00Z",
        "xdm:status": "live",
        "xdm:criteria": [
            {
                "xdm:placements": [
                    "xcore:offer-placement:122204529514a2c0"
                ],
                "xdm:optionSelection": {
                    "xdm:filter": "xcore:offer-filter:122a120f234dac7f"
                }
            }
        ],
        "xdm:fallback": "xcore:fallback-offer:1233160780eaa2ef"
    }'
```

**Response**

A successful response returns information on the newly created activity, including its unique instance ID and placement `@id`. You can use the instance ID in later steps to update or delete your activity.

```json
{
    "instanceId": "f88c9be0-1245-11eb-8622-b77b60702882",
    "@id": "xcore:offer-activity:124b79dc3ce2d720",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-19T20:02:09.694067Z",
    "repo:lastModifiedDate": "2020-10-19T20:02:09.694067Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
