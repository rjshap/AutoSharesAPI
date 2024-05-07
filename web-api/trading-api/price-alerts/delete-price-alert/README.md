---
description: Remove an existing price alert
---

# Delete Price Alert

## Overview

This DELETE endpoint enables you to remove a particular price alert of the user whose ID is provided in the request. Price alerts are essentially notifications that are sent to the user when the alert's conditions are satisfied by the market. For example, a user may have a price alert that will notify them when the price of the Apple stock exceeds $200.

There are five required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **userID** (path). This is the ID of the user whose particular price alert's must be deleted.
4. **alertId** (path). This is the ID of the price alert that must be deleted.

Here's the final template for this API request:

```
DELETE apiURL/v1.0/users/{userID}/pricealerts/{alertID}
```

## Response

In response to this API request, you'll receive an empty message and the 204 status code in case the alert was successfully deleted.

## Common Mistakes

Here are some of the common mistakes that developers make when attempting to remove a particular price alert.

The following article covers the syntax for this API request in detail.
