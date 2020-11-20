---
keywords: Experience Platform;home;popular topics;offer decisioning;offer collections;collections;Delete a collection
solution: Experience Platform
product: experience platform
title: Delete a collection
topic: API guide
description: Collections are subsets of offers based on predefined conditions defined by a marketer, such as category of the offer.
---

# Delete a collection

It may occasionally be necessary to remove (DELETE) a collection. Only collections that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the $id of the collection you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the collections are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | The instance id of the collection you wish to update. | `0bf31c20-13f1-11eb-a752-e58fd7dc4cb3` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0bf31c20-13f1-11eb-a752-e58fd7dc4cb3' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the collection. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the collection has been removed from the container.