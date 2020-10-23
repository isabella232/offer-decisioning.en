---
keywords: Experience Platform;home;popular topics;offer decisioning;offer collections;collections;create a collection
solution: Experience Platform
title: Create a collection
topic: API guide
description: Collections are subsets of offers based on predefined conditions defined by a marketer, such as category of the offer.
---

# Create a collection

Collections are subsets of offers based on predefined conditions defined by a marketer, such as category of the offer.

You can create a collection by making a POST request to the [!DNL Offer Library] API, while providing your container ID.

**API format**

```http
POST /{CONTAINER_ID}/instances
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| {CONTAINER_ID} | The container where the collections are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Request**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Offer Collection 1",
        "xdm:filterType": "anyTags",
        "xdm:ids": [
            "xcore:tag:124e147572cd7866"
        ]
    }'
```

**Response**

A successful response returns information on the newly created collection, including its unique instance ID and placement `@id`. You can use the instance ID in later steps to update or delete your collection. You can use your unique collection `@id` in a later tutorial to create an activity.

```json
{
    "instanceId": "0bf31c20-13f1-11eb-a752-e58fd7dc4cb3",
    "@id": "xcore:offer-filter:124e3594ce8b4930",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T22:59:17.345797Z",
    "repo:lastModifiedDate": "2020-10-21T22:59:17.345797Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```