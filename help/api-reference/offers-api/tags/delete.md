---
keywords: Experience Platform;home;popular topics;offer decisioning;delete tags
solution: Experience Platform
product: experience platform
title: Delete tags
description: Tags allow you to better organize and sort through your offers.
feature: API
role: Data Architect
level: Experienced
exl-id: cf15e944-e8cf-4c76-b5a5-f963b9e891e6
---
# Delete a tag

It may occasionally be necessary to remove (DELETE) a tag. Only tags that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the $id of the tag you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the tags are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | The instance id of the tag you wish to update. | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {{ACCESS_TOKEN}}' \
  -H 'x-api-key: {{API_KEY}}' \
  -H 'x-gw-ims-org-id: {{IMS_ORG}}' \
  -H 'x-sandbox-name: {{SANDBOX_NAME}}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the tag. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the tag has been removed from the container.
