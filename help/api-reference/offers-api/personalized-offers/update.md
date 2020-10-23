---
keywords: Experience Platform;home;popular topics;offer decisioning;personalized offers;update;update personalized offers
solution: Experience Platform
title: Update personalized offers
topic: API guide
description: A personalized offer is a customizable marketing message based on eligibility rules and constraints.
---

# Update a personalized offer

You can modify or update a personalized offer by making a PATCH request to the [!DNL Offer Library] API

For more information on JSON Patch, including available operations, see the official [JSON Patch documentation](http://jsonpatch.com/).

**API format**

```http
PATCH /{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| {CONTAINER_ID} | The container where the personalized offers are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| {INSTANCE_ID} | The instance id of the personalized offer you wish to update. | `0f4bc230-13df-11eb-bc55-c11be7252432` |

**Request**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0f4bc230-13df-11eb-bc55-c11be7252432' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'\
  -d '[
        {
            "op": "add",
            "path": "/_instance/xdm:representations/-",
            "value": {
                "xdm:placement": "xcore:offer-placement:124e0be5699743d3",
                "xdm:components": [
                    {
                        "@type": "https://ns.adobe.com/experience/offer-management/content-component-text",
                        "dc:format": "text/plain",
                        "dc:language": ["en"],
                        "xdm:content": "Here is your first sale offer!"
                    }
                ]
            }
        }
    ]'
```

| Parameter | Description |
| --------- | ----------- |
| `op` | The operation call used to define the action needed to update the connection. Operations include: `add`, `replace`, and `remove`. |
| `path` | The path of the parameter to be updated. |
| `value` | The new value you want to update your parameter with. |

**Response**

A successful response returns the updated details of the personalized offer, including its unique instance ID and personalized offer `@id`.

```json
{
    "instanceId": "0f4bc230-13df-11eb-bc55-c11be7252432",
    "@id": "xcore:personalized-offer:124e181c8b0d7878",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T20:50:32.018624Z",
    "repo:lastModifiedDate": "2020-10-21T20:50:32.018624Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```