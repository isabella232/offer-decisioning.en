---
keywords: Experience Platform;home;popular topics;offer decisioning;delete a fallback offer
product: experience platform
title: Delete a fallback offer
description: A fallback offer is sent to customers if they are not eligible for other offers
feature: API
role: Data Architect
level: Experienced
exl-id: e200ec85-91ee-402b-b5cb-e96087b0e7b6
---
# Delete a fallback offer

It may occasionally be necessary to remove (DELETE) a fallback offer. Only fallback offers that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the $id of the fallback offer you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the fallback offers are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | The instance id of the fallback offer. | `b3966680-13ec-11eb-9c20-8323709cfc65` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/b3966680-13ec-11eb-9c20-8323709cfc65' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {{ACCESS_TOKEN}}' \
  -H 'x-api-key: {{API_KEY}}' \
  -H 'x-gw-ims-org-id: {{IMS_ORG}}' \
  -H 'x-sandbox-name: {{SANDBOX_NAME}}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the fallback offer. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the fallback offer has been removed from the container.
