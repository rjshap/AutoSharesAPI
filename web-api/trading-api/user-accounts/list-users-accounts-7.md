# Add Account To User By Username

## Overview

This API endpoint enables you to bind a new or an existing trading account to an existing user.

## Add Account To User By Username

<mark style="color:orange;">`PUT`</mark> `baseURL/v{version}/accounts/{accountId}/username/{username}`

#### Path Parameters

| Name                                         | Type    | Description                                                                                           |
| -------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------- |
| apiVersion<mark style="color:red;">\*</mark> |         | The version of API. By default, set it to `1.0`.                                                      |
| accountId<mark style="color:red;">\*</mark>  | integer | This is the internal identifier of the trading account which is to be bound to an existing user.      |
| username<mark style="color:red;">\*</mark>   | String  | This field represents the username of the user to whom an existing trading account should be bound.\\ |

#### Query Parameters

| Name                                         | Type   | Description                                                                                                                         |
| -------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| accessType<mark style="color:red;">\*</mark> | String | This is the access level the user should have to this trading account. Available values: Full, ReadOnly, ClosePositionsOnly, Owner. |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request, JSON data is returned, containing updated information about the user and trading accounts." %}
```javascript
{
  "UserModel": {
    "UserId": 0,
    "FirstName": "string",
    "MiddleName": "string",
    "LastName": "string",
    "Login": "string",
    "Email": "string",
    "Role": 0,
    "AddedDate": "2023-07-28T14:00:07.136Z",
    "Salutation": "NoSalutation",
    "Suffix": "NoSuffix"
  },
  "AccountAccessType": "Full"
}
```
{% endtab %}
{% endtabs %}
