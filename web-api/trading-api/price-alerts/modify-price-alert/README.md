---
description: Modify an existing price alert
---

# Modify Price Alert

## Overview

This PUT endpoint enables you to modify a particular price alert of the user whose ID is provided in the request. Price alerts are essentially notifications that are sent to the user when the alert's conditions are satisfied by the market. For example, a user may have a price alert that will notify them when the price of the Apple stock exceeds $200.

There are five required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **userID** (path). This is the ID of the user whose particular price alert must be modified.
4. **model** (body). This is a JSON dictionary that contains information about the modified price alert.

### Alert Modification Syntax

Here's an example of the request body with the information about the modified price alert:

```javascript
{
    "Operator": "GTEQ",
    "State": "New",
    "SecurityId": 4,
    "Field": "Bid",
    "Argument": 200,
    "ExpirationDate": 1550674384
}
```

{% hint style="warning" %}
All six parameters must be indicated in the body JSON; otherwise the price alert will be improperly interpreted by the system.
{% endhint %}

Here's the final template for this API request:

```
PUT apiURL/v1.0/users/{userID}/pricealerts/{alertID}
```

## Response

In response to this API request, you'll receive the 200 status code and a JSON file with a detailed information about the modified price alert:

```javascript
{
  "Id": 0,
  "State": "New",
  "CreatedDate": 0,
  "Operator": "string",
  "SecurityId": 0,
  "Field": "string",
  "Argument": 0,
  "ExpirationDate": 0
}
```

## Common Mistakes

Here are some of the common mistakes that developers make when attempting to modify a particular price alert.

The following article covers the syntax for this API request in detail.
