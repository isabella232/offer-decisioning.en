---
keywords: Experience Platform;home;popular topics;offer decisioning;getting started
solution: Experience Platform
product: experience platform
title: Getting started
topic: API guide
description: Learn how to start using the Offer Library API to perform key operations using the Offer Decisioning Engine.
---

# [!DNL Offer Decisioning] API developer guide

[!DNL Offer Decisioning] is an Application Service integrated with Adobe Experience Platform. It allows you to leverage Adobe Experience Platform to deliver the best offer and experience to your customers across all touch points at the right time.

This developer guide provides steps to help you start using the [!DNL Offer Library] API. The guide then provides sample API calls for performing key operations using the Offer Decisioning Engine.

![](assets/do-not-localize/how-to-video.png) [Discover this feature in video](#video)

## Prerequisites

This guide requires a working understanding of the following components of Adobe Experience Platform:

* [[!DNL Experience Data Model (XDM) System]](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html): The standardized framework by which [!DNL Experience Platform] organizes customer experience data.
    * [Basics of schema composition](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html): Learn about the basic building blocks of XDM schemas.
* [[!DNL Offer Decisioning]](../offer-decisioning-home.md): Explains the concepts and components used for Experience Decisioning in general and Offer decisioning in particular. Illustrates the strategies used for choosing the best option to present during a customer's experience.
* [[!DNL Profile Query Language (PQL)]](https://docs.adobe.com/content/help/en/experience-platform/segmentation/pql/overview.html): PQL is a powerful language to write expressions over XDM instances. PQL is used to define decision rules.

## Reading sample API calls

This guide provides example API calls to demonstrate how to format your requests. These include paths, required headers, and properly formatted request payloads. Sample JSON returned in API responses is also provided. For information on the conventions used in documentation for sample API calls, see the section on [how to read example API calls](https://docs.adobe.com/content/help/en/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request) in the [!DNL Experience Platform] troubleshooting guide.

## Gather values for required headers

In order to make calls to [!DNL Platform] APIs, you must first complete the [authentication tutorial](https://docs.adobe.com/content/help/en/experience-platform/tutorials/authentication.html). Completing the authentication tutorial provides the values for each of the required headers in all [!DNL Experience Platform] API calls, as shown below:

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`

All requests that contain a payload (POST, PUT, PATCH) require an additional header:

* `Content-Type: application/json`

## Manage access to a container

A container is an isolation mechanism to keep different concerns apart. The container ID is the first path element for all repository APIs. All decisioning objects reside within a container.

An administrator can group similar principals, resources, and access permissions into profiles. This reduces the management burden and is supported by [Adobe Admin Console](https://adminconsole.adobe.com/). You must be a product administrator for Adobe Experience Platform in your organization to create profiles and assign users to them. It is sufficient to create product profiles that match certain permissions in a one-time step and then simply add users to those profiles. Profiles act as groups that have been granted permissions and every real user or technical user in that group inherits those permissions.

Given administrator privileges, you can grant or withdraw permissions to users through the [Adobe Admin Console](https://adminconsole.adobe.com/). For more information, see the [Access control overview](https://docs.adobe.com/content/help/en/experience-platform/access-control/home.html).

### List containers accessible to users and integrations

**API format**

```http
GET /{ENDPOINT_PATH}?product={PRODUCT_CONTEXT}&property={PROPERTY}==decisioning
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| {ENDPOINT_PATH} | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| {PRODUCT_CONTEXT} | Filters the list of containers by their association to product contexts. | `acp` |
| {PROPERTY} | Filters the type of container that is returned. | `_instance.containerType==decisioning` |

**Request**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/?product=acp&property=_instance.containerType==decisioning' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Response**

A successful response returns information regarding offer decisioning containers. This includes an `instanceId` attribute, the value of which is your container ID.

```json
{
    "_embedded": {
        "https://ns.adobe.com/experience/xcore/container": [
            {
                "instanceId": "{INSTANCE_ID}",
                "schemas": [
                    "https://ns.adobe.com/experience/xcore/container;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2020-09-16T07:54:28.319959Z",
                "repo:lastModifiedDate": "2020-09-16T07:54:32.098139Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "containerType": "decisioning",
                    "repo:name": "{REPO_NAME}",
                    "dataCenter": "{DATA_CENTER}",
                    "parentName": "{PARENT_NAME}",
                    "parentId": "{PARENT_ID}"
                },
                "_links": {
                    "self": {
                        "href": "/containers/{INSTANCE_ID}"
                    }
                }
            }
        ]
    },
    "_links": {
        "self": {
            "href": "/?product=acp&property=_instance.containerType==decisioning",
            "@type": "https://ns.adobe.com/experience/xcore/hal/home"
        }
    }
}
```

## Next steps

This document covered the prerequisite knowledge required to make calls to the [!DNL Offer Library] API, including acquiring your container ID. You can now proceed to the sample calls provided in this developer guide and follow along with their instructions.

## Tutorial video {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)
