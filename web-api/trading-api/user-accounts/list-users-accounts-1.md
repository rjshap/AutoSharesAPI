# Get All Users Of An Account

## Overview

This API endpoint enables you to retrieve the list of users who have access to a specific trading account.

## Get Account Users

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/accounts/{accountId}/users`

#### Path Parameters

| Name                                         | Type    | Description                                      |
| -------------------------------------------- | ------- | ------------------------------------------------ |
| apiVersion<mark style="color:red;">\*</mark> |         | The version of API. By default, set it to `1.0`. |
| accountId<mark style="color:red;">\*</mark>  | integer | Internal AutoShares ID of the trading account.   |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request." %}
```javascript
[
  {
    "UserModel": {
      "UserId": 54967,
      "FirstName": "Daniel",
      "MiddleName": "",
      "LastName": "Safonov",
      "Login": "danielSafonyan",
      "Email": "daniil.safonov@etnatrader.com",
      "Role": 0,
      "AddedDate": "2023-06-15T08:17:35.2984132Z",
      "Salutation": "NoSalutation",
      "Suffix": "NoSuffix"
    },
    "AccountAccessType": "Owner"
  }
]
```
{% endtab %}
{% endtabs %}
