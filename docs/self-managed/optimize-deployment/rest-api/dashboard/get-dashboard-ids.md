---
id: get-dashboard-ids
title: "Get dashboard IDs"
description: "The REST API to retrieve all dashboard IDs in a given collection."
---

## Purpose

This API allows users to retrieve all dashboard IDs from a given collection.

## Method & HTTP target resource

GET `/api/public/dashboard`

## Request headers

The following request headers have to be provided with every request:

|Header|Constraints|Value|
|--- |--- |--- |
|Authorization|REQUIRED|[Authorization](../../authorization)|

## Query parameters

The following query parameters have to be provided with every request:

|Parameter|Constraints|Value|
|--- |--- |--- |
|collectionId|REQUIRED|The ID of the collection for which to retrieve the dashboard IDs.|

## Request body

No request body is required.

## Result

The response contains a list of IDs of the dashboards existing in the collection with the given collection ID.

## Response codes

Possible HTTP response status codes:

|Code|Description|
|--- |--- |
|200|Request successful.|
|401|Secret incorrect or missing in HTTP Header. See [Authorization](../../authorization) on how to authenticate.|
|500|Some error occurred while processing the request, best check the Optimize log.|

## Example

### Retrieve all dashboard IDs from a collection

Assuming you want to retrieve all dashboard IDs in the collection with the ID `1234` and have configured the accessToken `mySecret`, this is what it would look like:

GET `/api/public/dashboard?collectionId=1234`

#### Request header

`Authorization: Bearer mySecret`

#### Response

Status 200.

#### Response content

```
[
    {
        "id": "9b0eb845-e8ed-4824-bd85-8cd69038f2f5"
    },
    {
        "id": "1a866c7c-563e-4f6b-adf1-c4648531f7d4"
    }
]
```
