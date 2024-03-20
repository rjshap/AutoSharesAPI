# Get Balance Information For A User

## Overview

This endpoint enables you to retrieve aggregated balance information of group of accounts linked to a particular user.

## Get Balance Information For A User

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/users/{userId}/balance-info`

#### Path Parameters

| Name                                         | Type    | Description                                      |
| -------------------------------------------- | ------- | ------------------------------------------------ |
| apiVersion<mark style="color:red;">\*</mark> | String  | The version of API. By default, set it to `1.0`. |
| userID<mark style="color:red;">\*</mark>     | Integer | Internal AutoShares ID of the user.              |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request, JSON data with balance information of the specified trading account is returned." %}
```javascript
```
{% endtab %}
{% endtabs %}
