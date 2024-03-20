# Get Account's Balance Info

## Overview

This endpoint enables you to retrieve balance information of a particular trading account.

## Get Balance Information For An Account

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/accounts/{accountId}/info`

#### Path Parameters

| Name                                         | Type   | Description                                      |
| -------------------------------------------- | ------ | ------------------------------------------------ |
| apiVersion<mark style="color:red;">\*</mark> |        | The version of API. By default, set it to `1.0`. |
| accountId<mark style="color:red;">\*</mark>  | String | Internal ETNA ID of the trading account.         |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request." %}
```javascript
{
  "cash": 100000,
  "netCash": 100000,
  "excess": 100000,
  "changeAbsolute": 0,
  "changePercent": 0,
  "equityTotal": 100000,
  "pendingOrdersCount": 0,
  "netLiquidity": 0,
  "stockLongMarketValue": 0,
  "stockShortMarketValue": 0,
  "optionLongMarketValue": 0,
  "optionShortMarketValue": 0,
  "forexLongMarketValue": 0,
  "forexShortMarketValue": 0,
  "dayTrades": 0,
  "stockBuyingPower": 100000,
  "optionBuyingPower": 100000,
  "forexBuyingPower": 100000,
  "dayTradingBuyingPower": 400000,
  "pendingCash": 0,
  "maintenanceMargin": 0,
  "optionMaintenanceMargin": 0,
  "openPL": 0,
  "openPLDay": 0,
  "openPLPercent": 0,
  "closePL": 0,
  "marketValue": 0,
  "totalPL": 0
}
```
{% endtab %}
{% endtabs %}

### Response Parameters

| Parameter               | Description                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| cash                    | This is the amount of funds available on the trading account.                                                                                                                                                                                                                                                                                                    |
| netCash                 | This the amount of funds available on the account minus the options margin requirement.                                                                                                                                                                                                                                                                          |
| excess                  | <p>This is the amount of funds that can either be withdrawn or used to open new positions. This value is used as the basis for calculating buying power.</p><p><strong>Excess = Equity - TMMR - Pending Cash - Uncleared Cash</strong>, where TMMR - Total Maintenance Margin Requirement (the sum of margin requirements for all positions of this account)</p> |
| changeAbsolute          | This is the difference between the account's value and the account's equity at the closing of the previous trading session. The account's value is the sum of the available Cash and the aggregate market value of all long and short positions.                                                                                                                 |
| changePercent           | Identical to `changeAbsolute` but expressed in percentage terms.                                                                                                                                                                                                                                                                                                 |
| equityTotal             | This is the gross valuation of all equity on the trading account.                                                                                                                                                                                                                                                                                                |
| pendingOrdersCount      | This is the number of pending orders on the account.                                                                                                                                                                                                                                                                                                             |
| netLiquidity            | This is the amount of funds that will be available to the user after all active positions are terminated.                                                                                                                                                                                                                                                        |
| stockLongMarketValue    | This is the gross market value of all long stock positions on the trading account.                                                                                                                                                                                                                                                                               |
| stockShortMarketValue   | This is the gross market value of all short stock positions on the trading account.                                                                                                                                                                                                                                                                              |
| optionLongMarketValue   | This is the gross market value of all long option positions on the trading account.                                                                                                                                                                                                                                                                              |
| optionShortMarketValue  | This is the gross market value of all short option positions on the trading account.                                                                                                                                                                                                                                                                             |
| forexLongMarketValue    | This is the gross market value of all long forex positions on the trading account.                                                                                                                                                                                                                                                                               |
| forexShortMarketValue   | This is the gross market value of all short forex positions on the trading account.                                                                                                                                                                                                                                                                              |
| dayTrades               | This is the number of day trades that have been executed during the last five trading sessions (including the current one).                                                                                                                                                                                                                                      |
| stockBuyingPower        | This is the gross amount of stocks that can be purchased on this trading account, adjusted for the available margin debt.                                                                                                                                                                                                                                        |
| optionBuyingPower       | This is the gross amount of options that can be purchased on this trading account, adjusted for the available margin debt.                                                                                                                                                                                                                                       |
| forexBuyingPower        | This is the gross amount of forex positions that can be opened on this trading account, adjusted for the available margin debt.                                                                                                                                                                                                                                  |
| pendingCash             | This is the amount of funds reserved to complete pending transactions.                                                                                                                                                                                                                                                                                           |
| maintenanceMargin       | This is the minimum amount of equity that must be maintained in a margin account.                                                                                                                                                                                                                                                                                |
| optionMaintenanceMargin | This is the minimum amount of equity that must be maintained for option securities.                                                                                                                                                                                                                                                                              |
| openPL                  | This is the amount of unrealized profit or loss for all positions.                                                                                                                                                                                                                                                                                               |
| closePL                 | This is the amount of realized profit or loss during the current trading session.                                                                                                                                                                                                                                                                                |
| marketValue             | This is the market value of all open long and short positions.                                                                                                                                                                                                                                                                                                   |
