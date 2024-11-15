---
description: >-
  Fetch information about a particular equity by providing a keyword that will
  be queried in all equities' symbol, exchange, and description fields.
---

# Get Equity Info by Mask

## Overview

This GET endpoint enables you to retrieve a list of securities with a certain pattern by specifying a keyword which will be queried in all equities' symbol, exchange, and description fields. All equities that feature the queried word (mask) in their ticker symbol or description will be returned in the JSON file as a response to the request.

There are five required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **mask** (query). This is the target keyword that will be searched for in all equities' symbol, exchange, and description fields.
4. **count** (query). This is the maximum number of equities that must be retrieved.

There's also one noteworthy optional parameter:

* filter (query). This is a query used to retrieve only those equities that satisfy the conditions of the query. The following table outlines the parameter's syntax:

| Syntax                          | Description                                                      | Example                                                 |
| ------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------- |
| Type=String                     | This query enables you to retrieve equities of a particular type | <ul><li>Type='MutualFund'</li></ul>                     |
| Type in (string1, string2, ...) | This query enables you to retrieve equities of multiple types    | <ul><li>Type in ('MutualFund', 'CommonStock')</li></ul> |

Here's the final template for this API request:

```
GET apiURL/v1.0/equities/lookup?mask=Apple&count=5&filter=Type%3D'MutualFund'
```

## Response

In response to this API request, you'll receive a JSON file with all equities who feature the queried word in the symbol, exchange, or description fields.

```javascript
[
    {
        "Id": 742349,
        "Symbol": "APLE",
        "Description": "Apple Hospitality REIT, Inc. Common Shares",
        "Exchange": "XNYS",
        "Currency": "USD",
        "AddedDate": "2016-05-04T13:32:42.358371Z",
        "ModifyDate": "2017-12-14T08:00:21.2018188Z",
        "Type": "CommonStock",
        "Precision": 2,
        "VolumePrecision": 0,
        "TickSize": 0.01,
        "Enabled": true,
        "AllowTrade": true,
        "AllowMargin": true,
        "AllowShort": true
    },
    {
        "Id": 4,
        "Symbol": "AAPL",
        "Description": "Apple Inc.",
        "Exchange": "XNAS",
        "Currency": "USD",
        "AddedDate": "2012-11-29T16:05:43.993Z",
        "ModifyDate": "2018-12-10T08:00:22.2867686Z",
        "Type": "CommonStock",
        "Precision": 2,
        "VolumePrecision": 0,
        "TickSize": 0.01,
        "Enabled": true,
        "AllowTrade": true,
        "AllowMargin": true,
        "AllowShort": true
    }
]
```

where:

| Parameter       | Description                                                                                                                                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Id              | This is the internal ID of the security in AutoShares.                                                                                                                                                                                                                      |
| Symbol          | This is the ticker symbol under which the security is listed on the exchange.                                                                                                                                                                                               |
| Description     | Usually this is the full name of the underlying company.                                                                                                                                                                                                                    |
| Exchange        | This is the exchange on which the security is listed.                                                                                                                                                                                                                       |
| Currency        | This is the currency in which the security is denominated.                                                                                                                                                                                                                  |
| AddedDate       | This is the date on which the security was added to the database.                                                                                                                                                                                                           |
| ModifyDate      | This is the date in which the security's information was last modified.                                                                                                                                                                                                     |
| Type            | This is the type of the security.                                                                                                                                                                                                                                           |
| Precision       | This is the number of decimal places in the security's price.                                                                                                                                                                                                               |
| VolumePrecision | This is the number of decimal places in the security's trading volume (might be useful for cryptocurrencies).                                                                                                                                                               |
| TickSize        | This is the minimum price change of the security. For example, if this property equals 0.01 for AAPL, the minimum price change for AAPL is 0.01 (150.67 —> 150.68, but not 150.675). For securities with the market price of less than $1, the TickSize is equal to 0.0001. |
| Enabled         | This field indicated if the security is enabled and can be traded by users.                                                                                                                                                                                                 |
| AllowTrade      | This field indicates is the security if permitted for trading.                                                                                                                                                                                                              |
| AllowMargin     | This field indicates if the security is allowed to be traded on margin.                                                                                                                                                                                                     |
| AllowShort      | This field indicates if the security can be sold short.                                                                                                                                                                                                                     |

## Common Mistakes

Here are some of the common mistakes that developers make when attempting to retrieve equities with a certain keyword in their symbol, exchange, or description fields.

The following article covers the syntax for this API request in detail.
