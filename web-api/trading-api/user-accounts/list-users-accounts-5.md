# Remove Account From User

## Overview

This API endpoint enables you to unbind a particular trading account from an existing user.

## Remove Account From User

<mark style="color:red;">`DELETE`</mark> `baseURL/v{version}/accounts/{accountId}/users/{userId}`

#### Path Parameters

| Name                                         | Type    | Description                                                                                        |
| -------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------- |
| apiVersion<mark style="color:red;">\*</mark> |         | The version of API. By default, set it to `1.0`.                                                   |
| accountId<mark style="color:red;">\*</mark>  | integer | This is the internal id of the trading account which is to be unbound from an existing user.       |
| userId	<mark style="color:red;">\*</mark>    | String  | This is the internal identifier of the user from whom an existing trading account must be unbound. |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request, JSON data is returned, containing updated information about the user and trading accounts." %}
```javascript
[
  {
    "UserModel": {
      "UserId": 0,
      "FirstName": "string",
      "MiddleName": "string",
      "LastName": "string",
      "Login": "string",
      "Email": "string",
      "Role": 0,
      "AddedDate": "2023-07-28T14:00:07.132Z",
      "Salutation": "NoSalutation",
      "Suffix": "NoSuffix"
    },
    "AccountAccessType": "Full"
  }
]
```
{% endtab %}
{% endtabs %}
