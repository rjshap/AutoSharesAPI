---
description: Rename an existing watchlist
---

# Rename Watchlist

## Overview

This PUT endpoint enables you to rename a specific watchlist of the user whose id is provided in the request's path.

There are six required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **userID** (path). This is the ID of the user whose particular watchlist needs to be have one security removed.
4. **watchlistID** (path). This is the internal identifier of the watchlist from which a security must be removed. You can retrieve the list of a user's watchlists with [this method](../remove-security-from-watchlist-by-id/).
5. **name** (query). This is a string that contains the new name for an existing watchlist.

Here's the final template for this API request:

```
PUT apiURL/v1.0/users/@me/watchlists/17973/name?name=New Name
```

## Response

In response to this API request, you'll receive a JSON file with a dictionary that contains two fields: the modified watchlist's ID and its new name.

```javascript
{
    "m_Item1": 17973, //ID of the modified wathclist
    "m_Item2": "New Name" //the new name
}
```

## Common Mistakes

Here are some of the common mistakes that developers make when attempting to rename a specific watchlist.

### Failing to Specify the Query Parameters

It's crucial to understand that the _**name**_ parameter must be provided in the request; otherwise you'll receive the 404 status code and the following message:

```javascript
{
    "Message": "No HTTP resource was found that matches the request URI 'https://pub-api-trader-demo-prod.etnasoft.us/api/v1.0/users/@me/watchlists/17973/name'."
}
```

The following article covers the syntax for this API request in detail.
