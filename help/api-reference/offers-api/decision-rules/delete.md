---
keywords: Experience Platform;home;popular topics;offer decisioning;decision rules;delete decision rules
solution: Experience Platform
product: experience platform
title: Delete decision rules
topic: API guide
description: Decision rules are constraints added to a personalized offer and applied to a profile to determine eligibility.
feature: API
role: Data Architect
level: Experienced
exl-id: 19759ed4-969d-4474-becd-e1d5949156e9
---
# Delete a decision rule

It may occasionally be necessary to remove (DELETE) a decision rule. Only decision rules that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the instance ID of the decision rule you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the decision rules are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` |The instance id of the decision rule you wish to update. | `eaa5af90-13d9-11eb-9472-194dee6dc381` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/eaa5af90-13d9-11eb-9472-194dee6dc381' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the decision rule. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the decision rule has been removed from the container.
