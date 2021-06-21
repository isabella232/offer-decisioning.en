---
keywords: Experience Platform;home;popular topics;offer decisioning;diagnostics
solution: Experience Platform
product: experience platform
title: Diagnostics API endpoint
topic: Developer guide
description: The `/diagnostics` endpoint returns a timestamp indicating when the offer catalog and/or activities were last updated, as well as a list of errors that occurred when doing so.
feature: API
role: Data Architect
level: Experienced
---

# Diagnostics endpoint

You can inspect a container for timestamps on when the offer catalog and/or activities were last updated using the `/diagnostics` endpoint. You can also use the `/diagnostics` endpoint to see a list of any errors that have occurred in your container.

## Getting started

The API endpoint used in this guide is part of the [[!DNL Offer Decisioning] API](./getting-started.md). Before continuing, please review the getting started guide for links to related documentation, a guide to reading the sample API calls in this document, and important information regarding required headers that are needed to successfully make calls to any Experience Platform API.

## Retrieve the diagnostic information of a container

**API format**

You can retrieve the diagnostic information of a container by making a GET request to `/{CONTAINER_ID}/diagnostics`.

```http
GET /{CONTAINER_ID}/diagnostics
```

| Parameter | Description
| --- | --- |
| `{CONTAINER_ID}` | The ID of the container you want to inspect. |

**Request**

```shell
curl -X GET \
  https://platform.adobe.io/data/core/ode/{CONTAINER_ID}/diagnostics \
  -H 'Accept: application/vnd.adobe.xed-id+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}'
```

**Response**

A container with updates or activities returns the following response, including a timestamp value for a package update:

```json
{
    "xdm:operations": {
        "xdm:decisioningPackageUpdate": {
            "xdm:date": "2021-04-13T22:38:48.897Z",
            "xdm:errors": []
        }
    }
}
```

A brand new container with neither updates nor activities returns the following response:

```json
{
  "xdm:operations": {}
}
```

A container with errors returns the following response:

```json
{
  "xdm:operations": {
    "xdm:offerCatalogUpdate": {
      "xdm:date": "2019-04-24T00:19:50.822Z",
      "xdm:errors": [
        {
          "xdm:description": "Error when creating offer catalog package for imsOrgId={IMS_ORG}, containerId={CONTAINER_ID}, error=Errors while processing offers, errorCount=1"
        },
        {
          "xdm:description": "Error while resolving offerId=xcore:personalized-offer:f8e0a451e93f4de: Error while processing ruleId=xcore:eligibility-rule:f8e0a5d6d2000e8: PQLValidationException: Unsupported function fake"
        }
      ]
    },
    "xdm:activitiesUpdate": {
      "xdm:date": "2019-04-24T00:19:50.782Z",
      "xdm:errors": []
    }
  }
}
```
