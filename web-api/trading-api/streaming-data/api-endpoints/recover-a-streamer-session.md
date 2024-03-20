# Recover a Streamer Session

### Overview

This PUT endpoint enables you to retrieve information that might be required to initiate a streaming session.

There are four required parameters that must be provided in the request:



1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference/). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **sessionType** (query). The type of the session that must be recovered. Possible values:
   * `0`. Recovers the data session
   * `1`. Recovers the quote session

Here's the final template for this API request:

```
PUT publicApiURL/v1.0/streamers/session/recover?sessionType=0
```

### Response

In response to this API request, you will receive a JSON dictionary containing the ID of the recovered session:

```javascript
{
  "Id": "f495411a-a3a1-47aa-a8cd-42e18365f444"
}
```

###

####
