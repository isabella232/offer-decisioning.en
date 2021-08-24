---
keywords: Experience Platform;home;popular topics;offer decisioning;diagnostics
solution: Experience Platform
product: experience platform
title: Diagnostics API endpoint
topic: Development
description: The `/diagnostics` endpoint reports when artifacts like the decisioning package were last attempted to be updated and lists errors that occurred while doing so.
feature: API
role: Data Architect
level: Experienced
---

# Diagnostics endpoint

You can inspect a container for timestamps on when artifacts like the decisioning package were last updated using the `/diagnostics` endpoint. You can also use the `/diagnostics` endpoint to see a list of any errors that have occurred in your container.

## Getting started

The API endpoint used in this guide is part of the [[!DNL Offer Decisioning] API](./getting-started.md). Before continuing, please review the getting started guide for links to related documentation, a guide to reading the sample API calls in this document, and important information regarding required headers that are needed to successfully make calls to any Experience Platform API.

## Retrieve the diagnostic information of a container

**API format**

You can retrieve the diagnostic information of a container by making a GET request to `/{CONTAINER_ID}/diagnostics`.

```http
GET /{CONTAINER_ID}/diagnostics
```

| Parameter | Description |
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

A container for which a decisioning package has been created without issues returns the following response, including a timestamp and an empty list of errors:

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

A brand new container for which no artifacts have been generated yet returns the following response:

```json
{
  "xdm:operations": {}
}
```

A container with errors during the decisioning package update returns a response with a non-empty list of errors:

```json
{
  "xdm:operations": {
    "xdm:decisioningPackageUpdate": {
      "xdm:date": "2021-06-01T12:00:00.000Z",
      "xdm:errors": [
        {
          "xdm:description": "Error(s) were found in instances related to a live activity",
          "xdm:causes": [
            {
              "xdm:description": "Error(s) were found while compiling scopes in xcore:offer-activity:0000000000000001",
              "xdm:details": {
                "@id": "xcore:offer-activity:0000000000000001",
                "instanceId": "00000000-0000-0000-0000-000000000001",
                "href": "https://platform.adobe.io/data/core/xcore/00000000-0000-0000-0000-000000000000/instances/00000000-0000-0000-0000-000000000001",
                "etag": "1"
              },
              "xdm:causes": [
                {
                  "xdm:description": "The following issue(s) were encountered for xcore:offer-activity:0000000000000001",
                  "xdm:details": {
                    "@id": "xcore:offer-activity:0000000000000001",
                    "instanceId": "00000000-0000-0000-0000-000000000001",
                    "href": "https://platform.adobe.io/data/core/xcore/00000000-0000-0000-0000-000000000000/instances/00000000-0000-0000-0000-000000000001",
                    "etag": "1"
                  },
                  "xdm:causes": [
                    {
                      "xdm:description": "Encountered issues with the dependency: xcore:eligibility-rule:0000000000000002",
                      "xdm:causes": [
                        {
                          "xdm:description": "The following issue(s) were encountered for xcore:eligibility-rule:0000000000000002",
                          "xdm:details": {
                            "@id": "xcore:eligibility-rule:0000000000000002",
                            "instanceId": "00000000-0000-0000-0000-000000000002",
                            "href": "https://platform.adobe.io/data/core/xcore/00000000-0000-0000-0000-000000000000/instances/00000000-0000-0000-0000-000000000002",
                            "etag": "2"
                          },
                          "xdm:causes": [
                            {
                              "xdm:description": "Exception encountered while processing entity: Error while validating PQL query",
                              "xdm:causes": [
                                {
                                  "xdm:description": "Function \"occurs\" with argument types [TIMESTAMP, BOOLEAN, TIME_RELATION, TIME_QUALIFICATION] does not match signature [TIMESTAMP, TIME_INTERVAL, TIME_RELATION, TIME_QUALIFICATION(opt)]"
                                }
                              ]
                            }
                          ]
                        }
                      ]
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

Errors that occur during the decisioning package creation prevent new or updated data from being propagated to the Decisioning Engine Runtime. Once the errors are resolved, all relevant data added or changed are included in the new decisioning package.