# Quick Start Guide

AutoShares cloud-based API infrastructure helps fintech developers launch the next generation of financial services, trading platforms, and apps.

We have made the APIs as easy as possible to work with. There are some essential concepts to understand having to do with a trading flow, but the calls themselves are very straightforward.

## Introduction to the APIs

AutoShares is an all-in-one front-to-back-office solution consisting of several components: web trader, mobile trading applications for iOS and Android, OMS with a middle and back office, and a suite of APIs for Stock, ETF, and Options Trading.   

AutoShares can be used as a whole turn-key trading suite, or certain components can be utilized separately including: single or multiple API endpoints, web trader, mobile applications, or brokerage back office with OMS.

Even though AutoShares provides both the web and the mobile interfaces for executing trades and analyzing markets, some users opt to implement their own custom interfaces that suit their requirements. For this purpose, AutoShares offers a trading platform as well as extended API that can be invoked to perform various trading operations like creating users, getting quotes, and placing orders.

The trading APIs are designed to perform operations typically performed by trader's widgets: orders, trading, account values, buying powers, positions, transactions, watchlists and price alerts, and so forth. These APIs can be called from anywhere simply using your app's API key and a user's credentials. 

**Features include:**

* AI and Vibe Coding
* Trade equities, options \(including multi-legs\), and ETFs.
* Web-based custom widgets and tabs designer - "trading browser within a web browser" 
* Market Analytics with streaming market data \(LI and LII\)
* Charts, including technical indicators and drawing tools
* Option Chains and Options Trading of Single Legged and Multi Legged Complex Options
* Monitor orders, positions and account balances 
* Customizable Price Alerts Engine
* Trade from any where functionality
* Paper trading/simulated trading mode 
* Customizable layouts
* Automation 
* Single or Multiple Endpoints
* Custom Integration and Development

For an overview of AutoShares Comprehensive Brokerage and Technology Solutions: [**Go here**](https://autoshares.com/api)

# Getting Started with the API
## Signup for AutoShares Developer Portal

[**Sign-up**](https://apidevportal.autoshares.dev/how-to) **or** [**Sign-in**](https://apidevportal.autoshares.dev/how-to) to the AutoShares Developer Portal and review the API documentation. 

When you are ready to start developing, follow the steps below. 

## Request AutoShares Connection Keys

To begin working with the API, you'll first need to register for **AutoShares Connection Keys.**

[**Register for Connection Keys**](https://onboarding.autoshares.com/app/241146432165147)

After you submit the developer registration form, AutoShares will set up your developer environment and provide connection keys.
We will generate two sets of API keys for you—a publishable client-side key and a secret server-side key—for testing connections and live connections. 

After you receive your connection keys, you can move forward with **authentication**.

## Authentication

We use OAuth 2.0 protocol for authentication and authorization. Publicly we support the Authorization Code flow (server-side application). OAuth 2.0 is a simple protocol and a developer can integrate with AutoShares’ Auth0 2.0 endpoints easily, especially using client libraries.

Every call to AutoShares API must include an API secret key. To start working with the API and your keys, you need to activate your account.

**Authentication** will only work *after* you receive your connection keys. 

**Read more here**: [**Authenticate with AutoShares SSO/Auth0**](https://documentation.autoshares.dev/api-documentation/authentication/authenticate-with-autoshares-sso-auth0)

## Sign Required Access Agreements

All users on the system must sign required access agreements to stream data. This GET endpoint enables you to fetch the list of all outstanding agreements that must be signed by the user.

## The Flow

In its most basic form, you will register your application with AutoShares, redirect a browser to a URL, parse a token from the responding redirect, and send the token to whichever AutoSharesAPI you wish to access.

## Authorization Codes

Authorization codes are short-lived (they expire in 10 minutes). A code is provided after an investor authorizes your application for access to their account. These codes are exchanged for access tokens which can be used to make API requests.

## Access Tokens

Access tokens (or Bearer tokens) are provided after a successful authorization code exchange. These tokens expire every 24 hours – no questions asked. Once a token expires you’ll need to exchange another authorization code to receive another access token.

## Refresh Tokens

Once refresh tokens are enabled for your application, you will receive the refresh token alongside every access token. You can exchange a refresh token for a new access token. Refresh tokens do not expire.

## New Account Onboarding

Applicants must follow the workflow determined by the AutoShares implementation team. Otherwise, you may initiate account signup using the following instructions with our online application (currently available for developer use only).

## User Accounts

This API endpoint enables you to bind a new or an existing trading account to an existing user.

## New to AutoShares API? Read how the registration process works.

| <p><br>Upon signing up, you get an email like the one below</p>                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Dear \<aspiring developer>,                                                                                                                                                                                                                                                                                                                                  |
| <p>Access to your AutoShares API is now ready for you to review the API documentation. <br><br>API Documentation: <a href="https://documentation.autoshares.dev">https://documentation.autoshares.dev</a></p>                                                                                                                              |
| <p>When you are ready to begin developing, you must register for a development connection key. Upon approval, your developer environment will be set up and you'll receive credentials within 1-2 business days.|

### Once you register for Developer Access Token and Key



You will receive an email with auth0 login and password reset upon signup.

| These are the credentials you must use to access the API gateway for further development. |
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
