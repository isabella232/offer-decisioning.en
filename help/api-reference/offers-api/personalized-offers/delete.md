---
keywords: Experience Platform;home;popular topics;offer decisioning;personalized offers;delete;delete personalized offers
product: experience platform
title: Delete personalized offers
description: A personalized offer is a customizable marketing message based on eligibility rules and constraints.
feature: API
role: Data Architect
level: Experienced
exl-id: d00454c8-b597-4069-bf11-ebe26628ed79
---
# Delete a personalized offer

It may occasionally be necessary to remove (DELETE) a personalized offer. Only personalized offers that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the $id of the personalized offer you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the personalized offers are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0f4bc230-13df-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {{ACCESS_TOKEN}}' \
  -H 'x-api-key: {{API_KEY}}' \
  -H 'x-gw-ims-org-id: {{IMS_ORG}}' \
  -H 'x-sandbox-name: {{SANDBOX_NAME}}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the personalized offer. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the personalized offer has been removed from the container.
