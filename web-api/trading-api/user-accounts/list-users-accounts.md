# Get All Accounts Of A User

## Overview

This endpoint enables you to list all trading accounts associated with the provided user id.

## Get All Accounts Of A User

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/users/{userId}/accounts`

#### Path Parameters

| Name                                         | Type   | Description                                      |
| -------------------------------------------- | ------ | ------------------------------------------------ |
| apiVersion<mark style="color:red;">\*</mark> |        | The version of API. By default, set it to `1.0`. |
| userID<mark style="color:red;">\*</mark>     | String | Internal AutoShares ID of the user.              |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request." %}
```javascript
[
  {
    "Id": 83267,
    "ClearingAccount": "83267",
    "AccessType": "Owner",
    "MarginType": "Margin",
    "OwnerType": "IndividualCustomer",
    "Enabled": true,
    "ClearingFirm": "PaperTrading",
    "IsAverageAccount": false,
    "Owners": [
      {
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
      }
    ]
  }
]
```
{% endtab %}
{% endtabs %}
