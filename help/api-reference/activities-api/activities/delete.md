---
keywords: Experience Platform;home;popular topics;offer decisioning;decisions;delete decisions
product: experience platform
title: Delete decisions
description: A decision contains the logic that informs the selection of an offer.
feature: API
role: Data Architect
level: Experienced
exl-id: 1bf44682-d0b0-460f-8eba-22c50a02c39e
---
# Delete a decision

It may occasionally be necessary to remove (DELETE) a decision (previously known as offer activity). Only decisions that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the $id of the fallback offer you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the decisions are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | The instance id of the activity. | `f88c9be0-1245-11eb-8622-b77b60702882` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/f88c9be0-1245-11eb-8622-b77b60702882' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {{ACCESS_TOKEN}}' \
  -H 'x-api-key: {{API_KEY}}' \
  -H 'x-gw-ims-org-id: {{IMS_ORG}}' \
  -H 'x-sandbox-name: {{SANDBOX_NAME}}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the activity. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the activity has been removed from the container.
