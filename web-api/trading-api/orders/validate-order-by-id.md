---
description: Validate an existing order by providing its ID
---

# Validate Order by ID

## Overview

This GET endpoint enables to you to validate an existing order by providing its ID as well as the ID of the trading account from which the order was placed.

## Returns the validation results for the order.

<mark style="color:blue;">`GET`</mark> `baseURL/v{apiVersion}/accounts/{accountID}/verified/orders/{orderID}`

#### Path Parameters

| Name                                         | Type   | Description                                                    |
| -------------------------------------------- | ------ | -------------------------------------------------------------- |
| apiVersion<mark style="color:red;">\*</mark> | String | The version of the API. Unless necessary, leave it at `1.0`.   |
| accountID<mark style="color:red;">\*</mark>  | String | The ID of the trading account from which the order was placed. |
| orderID<mark style="color:red;">\*</mark>    | String | The ID of the order that is to be validated.                   |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                                        |
| ----------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the very first token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request, the order" %}
```javascript
{
  "Model": {
    "OrderId": 1153288,
    "IsSuccessful": true,
    "Commission": 11,
    "Commissions": {
      "Per Trade Commission": 6,
      "Per Contract Commission": 5
    },
    "Cost": 2,
    "NetCost": 13,
    "TotalCost": 13,
    "Quotes": [
      {
        "Ask": 10,
        "Bid": 10,
        "Last": 10,
        "Volume": 0,
        "OpenInterest": 0,
        "Symbol": "MLXAU",
        "SecurityId": 30708874,
        "Timestamp": "2021-07-09T09:45:02.221093Z"
      }
    ],
    "MarginChange": 2
  },
  "Errors": [],
  "IsSucceed": true
}
```
{% endtab %}
{% endtabs %}
