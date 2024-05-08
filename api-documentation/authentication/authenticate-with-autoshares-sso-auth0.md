# Authenticate with AutoShares SSO/Auth0

## Universal Login is setup for all applications integrating with AutoShares. 

This is the easiest way to set up authentication in your application. We recommend using it for the best experience, best security and the fullest array of features. This guide will use it to provide a way for your users to log in to your JavaScript application. 

&#x20;

## When a user logs in, Auth0 returns three items:

* `access_token`: &#x20;
* `id_token`:
* `expires_in`: the number of seconds before the Access Token expires

## You can use these items in your application to set up and manage authentication.

#### Create an auth\_config.json in the root of the project. 

The values from domain and clientId should be populated within this file.

#### Login to configure this snippet with your account

`{`

&#x20; `"domain": "{yourDomain}",`

&#x20; `"clientId": "{yourClientId}"`

`}`

&#x20;

## If using a programming language such as Django,

Authlib to handle your application's authentication with Auth0:

`# 👆 We're continuing from the steps above. Append this to your /views.py file.`

`oauth = OAuth()`

`oauth.register(`

&#x20;   `"auth0",`

&#x20;   `client_id=settings.AUTH0_CLIENT_ID,`

&#x20;   `client_secret=settings.AUTH0_CLIENT_SECRET,`

&#x20;   `client_kwargs={`

&#x20;       `"scope": "openid profile email",`

&#x20;   `},`

`server_metadata_url=f"https://{settings.AUTH0_DOMAIN}/.well-known/openid-configuration",)`
