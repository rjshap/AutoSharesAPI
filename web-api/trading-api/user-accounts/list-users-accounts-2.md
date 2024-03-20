# Get Account Info

## Overview

The endpoint allows you to retrieve detailed information about an account. The response will include various account-related data, such as he unique identifier of the account, the timestamp indicating when the account was created, the account provider and etc.

## Get Account Info

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/accounts/{accountId}/details`

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
{
  "Id": "cd61a3a4-5380-42ba-330b-08db6b48ce67",
  "CreatedAt": "2023-06-15T09:04:43.3512813Z",
  "AccountProvider": "PaperTrading",
  "FormType": "Direct",
  "User": "54967",
  "ClearingAccountNumber": "83267",
  "IsOpened": true,
  "FormDataReference": "{\"marginType\":\"DayTrader\",\"cash\":\"100000\"}",
  "CustomerType": "Individual"
}
```
{% endtab %}
{% endtabs %}
