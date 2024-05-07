---
description: Retrieve options sorted by a particular field and split into multiple pages
---

# Get Filtered Options

## Overview

This GET endpoint enables you to retrieve options sorted by a specified field.

There are seven required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **pageNumber** (query). This is the page number (there are thousands of options split into pages).
4. **pageSize** (query). This is the number of options that should be retrieved from this page.
5. **sortField** (query). This is the field by which all retrieved options should be sorted. For example, if you specify **ExpirationDate**, first you'll receive options with the furthest expiration date while options with the closest expiration date will be listed in the end.
6. **Desc** (query). This is a boolean field that indicates if the returned options should be sorted in the descending order.

There's also one optional parameter worth examining:

* filter (query). This is an SQL query used to retrieve only those options that satisfy the conditions of the query. The following table outlines the parameter's syntax.

| Syntax                                                                                      | Description                                                                                                                                                             | Example                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <ul><li>AddedDate (>, >=, &#x3C;, &#x3C;=) Date</li><li>AddedDate between Range</li></ul>   | This query enables you to retrieve options that were added in the time period specified in the Range parameter or exactly at the time specified in the Date parameter.  | <ul><li>AddedDate between #2019-03-13T18:31:42# and #2019-03-17T18:31:42#</li><li>AddedDate >= #2019-03-13T18:31:42#</li><li>AddedDate &#x3C; #2019-03-12T19:31:42#</li></ul>    |
| <ul><li>ModifyDate (>, >=, &#x3C;, &#x3C;=) Date</li><li>ModifyDate between Range</li></ul> | This query enables you to retrieve options that will expire in the time period specified in the Range parameter or exactly at the time specified in the Date parameter. | <ul><li>ModifyDate between #2019-03-13T18:31:42# and #2019-03-17T18:31:42#</li><li>ModifyDate >= #2019-03-13T18:31:42#</li><li>ModifyDate &#x3C; #2019-03-12T19:31:42#</li></ul> |
| <ul><li>Symbol = String</li></ul>                                                           | This query enables you to retrieve options whose Symbol parameter is equal to the string provided in the query.                                                         | <ul><li>Symbol = 'AAPL'</li></ul>                                                                                                                                                |
| <ul><li>Exchange = String</li></ul>                                                         | This query enables you to retrieve options whose Exchange parameter is equal to the string provided in the query.                                                       | <ul><li>Exchange = 'XNAS'</li></ul>                                                                                                                                              |
| <ul><li>Currency = USD</li></ul>                                                            | This query enables you to retrieve options that are denominated in the currency provided in the query.                                                                  | <ul><li>Currency = 'USD'</li></ul>                                                                                                                                               |
| <ul><li>Enabled = Bool</li></ul>                                                            | This query enables you to retrieve options that are enabled (can be traded).                                                                                            | <ul><li>Enabled = false</li><li>Enabled = true</li></ul>                                                                                                                         |
| <ul><li>AllowTrade = Bool</li></ul>                                                         | This query enables you to retrieve options that are allowed to be traded.                                                                                               | <ul><li>AllowTrade = true</li><li>AllowTrade = false</li></ul>                                                                                                                   |
| <ul><li>AllowMargin = Bool</li></ul>                                                        | This query enables you to retrieve options that can be traded on margin.                                                                                                | <ul><li>AllowMargin = true</li><li>AllowMargin = false</li></ul>                                                                                                                 |
| <ul><li>AllowShort = Bool</li></ul>                                                         | This query enables you to retrieve options that can be sold short.                                                                                                      | <ul><li>AllowShort = true</li><li>AllowShort = false</li></ul>                                                                                                                   |
| <ul><li>Symbol in (value1, value2, etc.)</li></ul>                                          | This query enables you to retrieve options whose ticker symbol is contained in the query set.                                                                           | <ul><li>Symbol in ('ZTS 190426P00108000')</li></ul>                                                                                                                              |
| <ul><li>UnderlyingAssetSymbol</li></ul>                                                     | This query enables you to retrieve options whose underlying ticker symbol is equal to the one provided in the query.                                                    | <ul><li>UnderlyingAssetSymbol = 'AAPL'</li></ul>                                                                                                                                 |
| <ul><li>SeriesId</li></ul>                                                                  | This query enables you to retrieve options who belong to the option series whose ID was provided in the query.                                                          | <ul><li>SeriesId = 46780</li></ul>                                                                                                                                               |

{% hint style="info" %}
Note that you can combine different queries to create more complex requests:

* `AllowMargin = true and AllowShort = false`
{% endhint %}

Here's the final template for this API request:

```
GET apiURL/v1.0/options?pageNumber=0&pageSize=2&sortField=Type&desc=true
```

## Response

In response to this API request, you'll receive the following JSON that lists the options sorted by the specified parameter.

```javascript
{
    "Result": [
        {
            "Id": 4306850,
            "Symbol": "2SPX  261218P02000000",
            "Description": "PUT CBOE S&P 500 OPEN/EURO INDEX $2000 EXP 12/18/26",
            "Currency": "USD",
            "AddedDate": "2017-01-31T04:00:17.1153652Z",
            "ModifyDate": "2017-03-09T08:11:23.1917303Z",
            "Type": "Option",
            "Precision": 2,
            "VolumePrecision": 0,
            "TickSize": 0.01,
            "Enabled": false,
            "AllowTrade": false,
            "AllowMargin": false,
            "AllowShort": false,
            "OptionType": "Put",
            "ExpirationType": "Flex",
            "ExpirationDate": "2026-12-18T00:00:00Z",
            "StrikePrice": 2000,
            "SeriesId": 125825,
            "UnderlyingAssetSymbol": "2SPX",
            "ContractSize": 100
        },
        {
            "Id": 13210824,
            "Symbol": "VSSQ1 260217P00009000",
            "Description": "PUT Virtual Stock (static quotes) $9.00000000 EXP 02/17/26",
            "Exchange": "VIRTEX",
            "Currency": "USD",
            "AddedDate": "2018-09-11T07:20:10.318803Z",
            "ModifyDate": "2018-12-19T17:10:36.943Z",
            "Type": "Option",
            "Precision": 2,
            "VolumePrecision": 0,
            "TickSize": 0.01,
            "Enabled": true,
            "AllowTrade": true,
            "AllowMargin": true,
            "AllowShort": true,
            "OptionType": "Put",
            "ExpirationType": "Regular",
            "ExpirationDate": "2026-02-17T00:00:00Z",
            "StrikePrice": 9,
            "SeriesId": 125685,
            "UnderlyingAssetSymbol": "VSSQ1",
            "ContractSize": 100
        }
    ],
    "NextPageLink": "https://pub-api-etnatrader-test.etnasoft.us/api/v1.0/options/?pageNumber=1&pageSize=2&sortField=ExpirationDate&desc=true",
    "PreviousPageLink": "",
    "TotalCount": 3480010
}
```

where:

| Parameter             | Description                                                                                                                                                                                                                                                                 |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Id                    | This is the internal ID of the security in AutoShares.                                                                                                                                                                                                                      |
| Symbol                | This is the ticker symbol under which the security is listed on the exchange.                                                                                                                                                                                               |
| Description           | Usually this is the full name of the underlying company.                                                                                                                                                                                                                    |
| Exchange              | This is the exchange on which the security is listed.                                                                                                                                                                                                                       |
| Currency              | This is the currency in which the security is denominated.                                                                                                                                                                                                                  |
| AddedDate             | This is the date on which the security was added to the database.                                                                                                                                                                                                           |
| ModifyDate            | This is the date in which the security's information was last modified.                                                                                                                                                                                                     |
| Type                  | This is the type of the security — option in the case of this API request.                                                                                                                                                                                                  |
| Precision             | This is the number of decimal places in the security's price.                                                                                                                                                                                                               |
| VolumePrecision       | This is the number of decimal places in the security's trading volume (might be useful for cryptocurrencies).                                                                                                                                                               |
| TickSize              | This is the minimum price change of the security. For example, if this property equals 0.01 for AAPL, the minimum price change for AAPL is 0.01 (150.67 —> 150.68, but not 150.675). For securities with the market price of less than $1, the TickSize is equal to 0.0001. |
| Enabled               | This field indicated if the security is enabled and can be traded by users.                                                                                                                                                                                                 |
| AllowTrade            | This field indicates is the security if permitted for trading.                                                                                                                                                                                                              |
| AllowMargin           | This field indicates if the security is allowed to be traded on margin.                                                                                                                                                                                                     |
| AllowShort            | This field indicates if the security can be sold short.                                                                                                                                                                                                                     |
| OptionType            | This is the type of option. Possible values: call, put.                                                                                                                                                                                                                     |
| ExpirationType        | This is the expiration type of the option. Possible values: Regular, Quarterly, Weekly, Flex, Undefined, Mini, NonStandard.                                                                                                                                                 |
| ExpirationDate        | This is the expiration date of the option.                                                                                                                                                                                                                                  |
| StrikePrice           | This is the price at which the holder of the option can buy or sell the underlying asset.                                                                                                                                                                                   |
| SeriesId              | This is the internal ID of the option series in AutoShares                                                                                                                                                                                                                  |
| UnderlyingAssetSymbol | This is the ticker symbol of the underlying asset.                                                                                                                                                                                                                          |
| NextPageLink          | The link of the next page of options.                                                                                                                                                                                                                                       |
| PreviousPageLink      | The link of the previous page of options.                                                                                                                                                                                                                                   |
| TotalCount            | The total number of options available.                                                                                                                                                                                                                                      |

## Common Mistakes

Here are some of the common mistakes that developers make when attempting to retrieve sorted options.

### Failing to Specify the Query Parameters

It's crucial to understand that the _**underlying**_ parameter must be indicated in the request; otherwise you'll receive the 404 status code and the following message:

```javascript
{
    "Message": "No HTTP resource was found that matches the request URI 'https://pub-api-etnatrader-dev.etnasoft.us/api/v1.0/options?pageNumber=0&pageSize=2&sortField=Type'."
}
```

The following article covers the syntax for this API request in detail.
