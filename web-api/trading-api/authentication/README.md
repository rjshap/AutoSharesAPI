---
description: >-
  Perform initial authentication to retrieve the authentication token used in
  all other requests
---

# Authentication


## Overview

Auth0's 2.0 protocol for authentication and authorization. Publicly we
support the Authorization Code flow (server-side application). OAuth 2.0 is
a simple protocol and a developer can integrate with AutoShares’ Auth0 2.0
endpoints easily, especially using client libraries.

The Authentication API exposes identity functionality for Auth0 and supported identity protocols (including OpenID Connect, OAuth, and SAML).

Typically, you should consume this API through one of the Auth0 SDKs, such as Auth0.js, or a library like Lock. However, if you are building your authentication UI manually, you will need to call the Authentication API directly.

Some example tasks include:

    Get tokens during authentication

    Request a user's profile using an Access Token

    Exchange Refresh Tokens for new Access Tokens

    Request a challenge for multi-factor authentication (MFA

    API

Learn about and explore the requests and responses for the Auth0 Authentication API endpoints in your browser with the Authentication API.
Management API

The Management API allows you to manage your Auth0 account programmatically, so you can automate configuration of your environment. Most of the tasks you can perform in the Auth0 Management Dashboard can also be performed programmatically by using this API.

Some example tasks include:

    Register your applications and APIs with Auth0

    Set up connections with which your users can authenticate

    Manage users

    Link user accounts
