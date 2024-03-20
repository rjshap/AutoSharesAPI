# For logout scenario

#### Clearing a session with logout

This route handles signing a user out from your application. It will clear the user's session in your app, and briefly redirect to Auth0's logout endpoint to ensure their session is completely clear, before they are returned to your home route

As an example

```
# 👆 We're continuing from the steps above. Append this to your /views.py file.
```

```
 
```

```
def logout(request):
```

```
    request.session.clear()
```

```
 
```

```
    return redirect(
```

```
        f"https://{settings.AUTH0_DOMAIN}/v2/logout?"
```

```
        + urlencode(
```

```
            {
```

```
                "returnTo": request.build_absolute_uri(reverse("index")),
```

```
                "client_id": settings.AUTH0_CLIENT_ID,
```

```
            },
```

```
            quote_via=quote_plus,
```

```
        ),
```

```
    )
```

&#x20;

Include the client\_id parameter in the string, as shown here:\
\
[`https://YOUR_DOMAIN/v2/logout?returnTo=http%3A%2F%2Flocalhost%3A85&client_id=YOUR_CLIENT_ID`](https://your\_domain/v2/logout?returnTo=http%3A%2F%2Flocalhost%3A85\&client\_id=YOUR\_CLIENT\_ID)

&#x20;

&#x20;This would ensure the logouts happen seamlessly. If it is not provided, it results in inconsistent behavior.

&#x20;
