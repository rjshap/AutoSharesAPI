---
description: >-
  Perform initial authentication to retrieve the authentication token used in
  all other requests
---

# Authentication

## Authenticate with AutoShares SSO/Auth0

Auth0's 2.0 protocol for authentication and authorization. Publicly we support the Authorization Code flow (server-side application). OAuth 2.0 is a simple protocol and a developer can integrate with AutoShares’ Auth0 2.0 endpoints easily, especially using client libraries.

The Authentication API exposes identity functionality for Auth0 and supported identity protocols (including OpenID Connect, OAuth, and SAML).

Typically, you should consume this API through one of the Auth0 SDKs, such as Auth0.js, or a library like Lock. However, if you are building your authentication UI manually, you will need to call the Authentication API directly.

### Some example tasks include:

```
Get tokens during authentication

Request a user's profile using an Access Token

Exchange Refresh Tokens for new Access Tokens

Request a challenge for multi-factor authentication (MFA) API
```

Learn about and explore the requests and responses for the Auth0 Authentication API endpoints in your browser with the Authentication API. 

## Management API

The Management API allows you to manage your Auth0 account programmatically, so you can automate configuration of your environment. Most of the tasks you can perform in the Auth0 Management Dashboard can also be performed programmatically by using this API.

### Some example tasks include:

```
## Register your applications and APIs with Auth0

Set up connections with which your users can authenticate

## Manage users

Link user accounts
```

When you signed up for integrating with AutoShares  single sign-on solution(Auth0), a new application will be created for you. You will need some details about this application to communicate with Auth0. One of the AutoShares system administrators can provide the following information once your application is setup.

### You need the following information:

* Domain
* Client ID
* Client Secret

&#x20;

&#x20;

## Callback URL

A callback URL is a URL in your application where Auth0 redirects the user after they have authenticated. The callback URL for your app must be added to the **Allowed Callback URLs** field within Auth0 by our admins. If this field is not set, users will be unable to log in to the application and will get an error.

&#x20;

You will need to provide this URL and Logout URL .

**## As an example, allowed Callback URL** could be set to [`http://localhost:3000`](http://localhost:3000) if you are testing a local application.

&#x20;

## Installation and code changes for developers:

### You can install the Auth0 SPA SDK as a dependency of your application, useful if you're using a build system

Install as a dependency....

If you use npm or react,

\# installation with npm

npm install --save @auth0/auth0-spa-js

&#x20;

\# installation with yarn

yarn add @auth0/auth0-spa-js

&#x20;

Once the Auth0 SPA SDK is installed, reference it using an import statement at the entrypoint of your application ():

import { createAuth0Client } from '@auth0/auth0-spa-js';

&#x20;

## If using code language such as Django,

create an `.env` file in your project directory. This file will hold your client keys and other configuration details

example:

`# 📁 .env -----`

`AUTH0_CLIENT_ID=lHW6t5rLmCum597wgtNpf0WpMXyunvAI`

`AUTH0_CLIENT_SECRET=yQpIdF-bFHzugj-KWr4Fh-EMZzKFKS7an3NOpjyQLacwtZLCtfR38AIYn61fQMQ9`

`AUTH0_DOMAIN=autosharesdev.us.auth0.com`



## Update settings.py

You'll want to make some minor changes to your `/settings.py` file to read those `.env` values. At the top of the file, add these imports:

```
# 📁 /settings.py -----
```

```
import os
```

```
from dotenv import load_dotenv, find_dotenv
```

&#x20;

&#x20;

at the end of this file, add the following:

`# 📁 /settings.py -----`

&#x20;

`# Load environment definition file`

`ENV_FILE = find_dotenv()`

`if ENV_FILE:`

&#x20;   `load_dotenv(ENV_FILE)`

&#x20;

&#x20;

`# Load Auth0 application settings into memory`

`AUTH0_DOMAIN = os.environ.get("AUTH0_DOMAIN")`

`AUTH0_CLIENT_ID = os.environ.get("AUTH0_CLIENT_ID")`

`AUTH0_CLIENT_SECRET = os.environ.get("AUTH0_CLIENT_SECRET")`

&#x20;
