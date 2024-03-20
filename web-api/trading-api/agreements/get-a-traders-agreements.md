---
description: Retrieve the list of agreements that the trader must sign
---

# Access Agreements

### Introduction

All users on the system must sign agreements. This GET endpoint enables you to fetch the list of all outstanding agreements that must be signed by the trader.

There are four required parameters that must be provided in the request:

1. **Authorization** (header). This is the authorization token from the very first [token request](../authentication/requesting-tokens/). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **userID** (path). The internal ID of the trader whose agreements are to be retrieved. If the request is sent on behalf of the trader whose authorization token is provided in the second header, simply set this parameter to `@me`.

Here's the final template for this API request:

```
GET apiURL/v1.0/users/@me/agreements
```

### Response

In response to this API request, you'll receive a JSON file containing the list of the agreements that must be signed.

```javascript
[
  {
    "Type": "Platform",
    "CanSkip": true
  }
]
```

where:

| Parameter | Description                                 |
| --------- | ------------------------------------------- |
| Type      | The type of the agreement.                  |
| CanSkip   | Indicates if this agreement can be skipped. |

### Common Mistakes

Here are some of the common mistakes that developers make when attempting to retrieve the list of outstanding agreements.

####
