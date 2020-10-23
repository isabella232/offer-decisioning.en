---
keywords: Experience Platform;home;popular topics;offer decisioning;decision rules;look up a decision rule
solution: Experience Platform
title: Look up a decision rule
topic: API guide
description: Decision rules are constraints added to a personalized offer and applied to a profile to determine eligibility.
---

# Look up a decision rules

You can look up a specific decision rule by making a GET request to the [!DNL Offer Library] API that includes either the decision rule `@id` or the name of the decision rule in the request path.

**API format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_ELIGIBILITY_RULE}&{QUERY_PARAMS}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `ENDPOINT_PATH` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `CONTAINER_ID` | The container where the placements are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `SCHEMA_ELIGIBILITY_RULE` | Defines the schema associated with decision rules. | `https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3` |
| `id` | A string used to match the `@id` property of the entities. The string is matched exactly. The parameter s `id` and `name` cannot be used together. | `xcore:eligibility-rule:124e0faf5b8ee89b` |
| `name` | A string used to match the xdm:name property of the entities. The string is matched exactly, with capitalization, but wild card characters can be used. The parameters `id` and `name` cannot be used together | `Sales rule` |

**Request**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3&name=Sales%20rule' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Response**

A successful response returns the details of the specific decision rule you looked up, including information about its container ID, instance ID and, unique decision rule `@id`.

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3",
    "requestTime": "2020-10-21T20:14:08.153670Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "eaa5af90-13d9-11eb-9472-194dee6dc381",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2020-10-21T20:13:43.048666Z",
                "repo:lastModifiedDate": "2020-10-21T20:13:43.048666Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_score": 0,
                "_instance": {
                    "xdm:name": "Sales rule",
                    "description": "Decisioning rule for sales",
                    "xdm:definedOn": {
                        "profile": {
                            "xdm:schema": {
                                "$ref": "https://ns.adobe.com/xdm/context/profile_union",
                                "version": "1"
                            },
                            "xdm:referencePaths": [
                                "person.name.firstName"
                            ]
                        }
                    },
                    "condition": {
                        "format": "pql/text",
                        "type": "PQL",
                        "value": "profile.person.name.firstName.equals(\"Joe\", false)"
                    },
                    "@id": "xcore:eligibility-rule:124e0faf5b8ee89b"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3#eaa5af90-13d9-11eb-9472-194dee6dc381",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/eaa5af90-13d9-11eb-9472-194dee6dc381",
                        "@type": "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"
                    }
                }
            }
        ],
        "total": 1,
        "count": 1
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3&name=Sales%20rule",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```