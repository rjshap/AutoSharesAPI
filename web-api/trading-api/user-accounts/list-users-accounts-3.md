# Get Historical Account Value

## Overview

The endpoint allows you to retrieve the historical values of a particular trading account over the specified period.

{% hint style="info" %}
The start and end date are represented in the following format "2022-07-28T09:04:43.3512813Z".\
\
It is an ISO 8601 timestamp representing a date and time in Coordinated Universal Time (UTC).
{% endhint %}

## Get Historical Account Value

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/accounts/{accountId}/history`

#### Path Parameters

| Name                                         | Type    | Description                                      |
| -------------------------------------------- | ------- | ------------------------------------------------ |
| apiVersion<mark style="color:red;">\*</mark> |         | The version of API. By default, set it to `1.0`. |
| accountId<mark style="color:red;">\*</mark>  | integer | Internal AutoShares ID of the trading account.   |

#### Query Parameters

| Name                                         | Type      | Description                          |
| -------------------------------------------- | --------- | ------------------------------------ |
| startDate	<mark style="color:red;">\*</mark> | date-time | The start date of the target period. |
| endDate<mark style="color:red;">\*</mark>    | date-time | The end date of the target period.   |
| step<mark style="color:red;">\*</mark>       | integer   | Set 1 as a default step.             |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |
| Et-App-Key<mark style="color:red;">\*</mark>    | String | This is your app’s unique key that can be retrieved from the BO Companies widget in AutoShares.                                                                         |

{% tabs %}
{% tab title="200: OK Successful request." %}
```javascript
[
  {
    "Date": "2023-06-15T00:00:00Z",
    "Value": 100000
  },
  {
    "Date": "2023-06-16T00:00:00Z",
    "Value": 100000
  },
  {
    "Date": "2023-06-20T00:00:00Z",
    "Value": 99989
  },
  {
    "Date": "2023-06-21T00:00:00Z",
    "Value": 99933.6
  },
  {
    "Date": "2023-06-22T00:00:00Z",
    "Value": 100025.5
  },
  {
    "Date": "2023-06-23T00:00:00Z",
    "Value": 99975.4
  },
  {
    "Date": "2023-06-27T00:00:00Z",
    "Value": 99984.7
  },
  {
    "Date": "2023-06-28T00:00:00Z",
    "Value": 100009.4
  },
  {
    "Date": "2023-06-29T00:00:00Z",
    "Value": 100004.8
  },
  {
    "Date": "2023-06-30T00:00:00Z",
    "Value": 100103.5
  },
  {
    "Date": "2023-07-03T00:00:00Z",
    "Value": 100062.9
  },
  {
    "Date": "2023-07-05T00:00:00Z",
    "Value": 100053.2
  },
  {
    "Date": "2023-07-06T00:00:00Z",
    "Value": 100089.2
  },
  {
    "Date": "2023-07-07T00:00:00Z",
    "Value": 100037.4
  },
  {
    "Date": "2023-07-10T00:00:00Z",
    "Value": 99962.8
  },
  {
    "Date": "2023-07-11T00:00:00Z",
    "Value": 99963.9
  },
  {
    "Date": "2023-07-12T00:00:00Z",
    "Value": 100028.1
  },
  {
    "Date": "2023-07-13T00:00:00Z",
    "Value": 100090.4
  },
  {
    "Date": "2023-07-14T00:00:00Z",
    "Value": 100117.7
  },
  {
    "Date": "2023-07-17T00:00:00Z",
    "Value": 100155.6
  },
  {
    "Date": "2023-07-18T00:00:00Z",
    "Value": 100290.6
  },
  {
    "Date": "2023-07-19T00:00:00Z",
    "Value": 100260.2
  },
  {
    "Date": "2023-07-20T00:00:00Z",
    "Value": 100158.4
  },
  {
    "Date": "2023-07-21T00:00:00Z",
    "Value": 100115.5
  },
  {
    "Date": "2023-07-24T00:00:00Z",
    "Value": 100137
  },
  {
    "Date": "2023-07-25T00:00:00Z",
    "Value": 100204.4
  },
  {
    "Date": "2023-07-26T00:00:00Z",
    "Value": 100081.1
  },
  {
    "Date": "2023-07-27T00:00:00Z",
    "Value": 99997.8
  },
  {
    "Date": "2023-07-28T00:00:00Z",
    "Value": 100072.7
  }
]
```
{% endtab %}
{% endtabs %}
