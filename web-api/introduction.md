# Quick Start Guide

AutoShares cloud-based API infrastructure was built for fintech developers seeking to launch the next generation of financial services, trading platforms, and apps.

We have made AutoShares APIs as easy as possible to work with. There are some essential concepts to understand having to do with a trading flow, but the calls themselves are very straightforward.

**Lets Get Started:**

[**Sign Up**](https://apidevportal.autoshares.dev/how-to) **or** [**Sign In**](https://apidevportal.autoshares.dev/how-to) \*_to the AutoShares API Documentation Portal_

Review the API documentation. 

**To begin developing, you must register for a developer connection key.**

[**Register for Developer Connection Key**](https://onboarding.autoshares.com/app/241146432165147)

After you submit the developer registration form, AutoShares will set up your developer environment and provide connection keys within 1-2 business days. 

We will generate two sets of API keys for you—a publishable client-side key and a secret server-side key—for testing connections and live connections.

### Authentication

Every call to AutoShares API must include an API secret key. After you create an AutoShares developer account, we generate API keys for you. To start working with the API with your keys, you need to activate your account.

We use Auth0's 2.0 protocol for authentication and authorization. Publicly we support the Authorization Code flow (server-side application). OAuth 2.0 is a simple protocol and a developer can integrate with AutoShares’ Auth0 2.0 endpoints easily, especially using client libraries.

Follow the [**Authentication Instructions**] after your receive your connection keys** 

Read more here: [**Authenticate with AutoShares SSO/Auth0**](https://documentation.autoshares.dev/api-documentation/authentication/authenticate-with-autoshares-sso-auth0)

#### The Flow

In its most basic form, you will register your application with AutoShares, redirect a browser to a URL, parse a token from the responding redirect, and send the token to whichever AutoSharesAPI you wish to access.

#### Authorization Codes

Authorization codes are short-lived (they expire in 10 minutes). A code is provided after an investor authorizes your application for access to their account. These codes are exchanged for access tokens which can be used to make API requests.

#### Access Tokens

Access tokens (or Bearer tokens) are provided after a successful authorization code exchange. These tokens expire every 24 hours – no questions asked. Once a token expires you’ll need to exchange another authorization code to receive another access token.

#### Refresh Tokens

Once refresh tokens are enabled for your application, you will receive the refresh token alongside every access token. You can exchange a refresh token for a new access token. Refresh tokens do not expire.

#### Access Agreements

All users on the system must sign access agreements to stream data. This GET endpoint enables you to fetch the list of all outstanding agreements that must be signed by the user.

#### Onboarding Accounts

Applicants must follow the workflow determined by the AutoShares implementation team. Otherwise, you may initiate account signup using the following instructions with our development application (currently available for development use only).

#### Adding User Accounts

This API endpoint enables you to bind a new or an existing trading account to an existing user.

#### Trading APIs

This is the trader's API that invokes actions typically performed by trader's widgets: placing orders, getting quotes, configuring price alerts, and so forth. This API can be called from anywhere simply using your app's API key and a user's credentials.

## New to coding and development or never worked with API based systems before? Read below for how the process works...

| <p><br>Upon signing up, you get an email like the one below</p>                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Dear \<aspiring developer>,                                                                                                                                                                                                                                                                                                                                  |
| <p>Access to your AutoShares API is now ready for you to review the API documentation. <br><br>API Documentation: <a href="https://documentation.autoshares.dev">https://documentation.autoshares.dev</a></p>                                                                                                                              |
| <p>When you are ready to begin developing, you must register for a development connection key. Please email us at support@autoshares.dev to get setup. Upon approval, your developer environment will be set up and you'll receive credentials within 1-2 business days.|

### Once you register for Developer Access Token and Key



You will receive an email with auth0 login and password reset upon signup.

| These are the credentials you must use to access the API gateway and for further development. |
| ----------------------------------------------------------------------------------------- |
|                                                                                           |

&#x20;

If you are integrating to present a login page to the authentication platform, the following page details the process using auth0(existing authentication platform). Note that your login page needs to be redirected to this login module. This is to enable single signon and you must be familiar with how authentication platforms and single signon works before you go further. We highly recommend reading the resources below before attempting to do that.

&#x20;

1\. [https://documentation.autoshares.dev/api-documentation/authentication](https://documentation.autoshares.dev/api-documentation/authentication)

2\. [https://documentation.autoshares.dev/api-documentation/authentication/authenticate-with-autoshares-sso-auth0](https://documentation.autoshares.dev/api-documentation/authentication/authenticate-with-autoshares-sso-auth0)

3.[https://documentation.autoshares.dev/api-documentation/authentication/triggering-authentication-with-login](https://documentation.autoshares.dev/api-documentation/authentication/triggering-authentication-with-login)

&#x20;



&#x20;
