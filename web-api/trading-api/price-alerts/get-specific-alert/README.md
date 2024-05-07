---
description: Fetch information about a specific price alert
---

# Get Specific Alert

## Overview

This GET endpoint enables you to retrieve information about a particular price alert of the user whose ID is provided in the request. Price alerts are essentially notifications that are sent to the user when the alert's conditions are satisfied by the market. For example, a user may have a price alert that will notify them when the price of the Apple stock exceeds $200.

There are five required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **userID** (path). This is the ID of the user whose particular price alert's information needs to be retrieved.
4. **alertID** (query). This is the ID of the price alert whose information needs to be retrieved.

Here's the final template for this API request:

```
GET apiURL/v1.0/users/{userID}/pricealerts/{alertID}
```

## Response

In response to this API request, you'll receive a JSON file with the detailed information about the price alert.

```javascript
{
  "Id": 1713,
  "State": "New",
  "CreatedDate": 1574788285,
  "Operator": "LTEQ",
  "SecurityId": 4,
  "Symbol": "AAPL",
  "Field": "Last",
  "Argument": 250,
  "ExpirationDate": 1577293871
}
```

where:

| Parameter      | Description                                                                                                          |
| -------------- | -------------------------------------------------------------------------------------------------------------------- |
| Id             | This is the internal identifier of the price alert.                                                                  |
| State          | This is the state of the price alert. Possible values: New, Expired, Completed, Stopped.                             |
| CreatedDate    | This is the date on which the price alert was created (in ticks).                                                    |
| Operator       | This is the condition of the price alert. Possible values: GTEQ (greater or equal to), LTEQ (less than or equal to). |
| SecurityId     | This is the ID of the security for which the price alert is configured.                                              |
| Symbol         | This is the ticker symbol of the security for which the price alert is configured.                                   |
| Field          | This is the referent price for the price alert. Possible values: Ask, Bid, Last.                                     |
| Argument       | This is the price point at which the price alert will be triggered and the user will be notified.                    |
| ExpirationDate | This is the expiration date of the price alert (in ticks).                                                           |

The following article covers the syntax for this API request in detail.
