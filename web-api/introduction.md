# Quick Start Guide
### Overview

AutoShares is a cross-platform online trading solution for Stocks, Options, and ETFs with all-encompassing trading functionality. Even though AutoShares provides both the web and the mobile interfaces for executing trades and analyzing markets, some users opt to implement their own custom interfaces that suit their requirements. For this purpose, AutoShares offers a trading platform as well as extended REST API that can be invoked to perform various trading operations like creating users, getting quotes, and placing orders. 

In this scenario AutoShares serves as the backend platform for your own custom-made web terminal or mobile app. Your task is to develop the mobile and web UI that invokes our API to perform all of the trading operations. On our side, we will execute your customers' orders on the required exchange, settle all transactions with the clearing firm, and take care of all of behind-the-scenes technicalities.

Another frequent use-case of our API is to augment the existing functionality of AutoShares trading platform by designing custom widgets. In this scenario you create your own custom JavaScript-based widgets that can load various information about the user's positions, place new orders, and perform just about any other action. For example, you can create a widget that displays the user's most frequently traded securities; or a widget that displays the list of users' positions with the highest profit or highest loss.

### Trading APIs

This is the trader's API that invokes actions typically performed by trader's widgets: placing orders, getting quotes, configuring price alerts, and so forth. This API can be called from anywhere simply using your app's API key and a user's credentials. 

---

# Working with the APIs

### Introduction

The APIs are designed to perform operations like placing orders and trading, streaming buying power and account values, positions, charts, price alerts, and transactions. 

The documentation for the APIs are structured by categories, each representing a different set of functionality. The first section — **Authentication** — covers the process of generating authentication tokens that must be provided in the header of all other requests. All subsequent sections cover different aspects of AutoSharesthe APIs, ranging from order placement to working with self-directed trading accounts.

Each API request is described on two pages; the first page introduces you to the API request and explains how to properly use the request parameters and the typical mistakes to avoid; the second page is strictly technical, outlining all of the header and body parameters along with their types, the range of request status codes, as well as all possible responses:


![](../../.gitbook/assets/screenshot-2019-04-29-at-15.29.22.png)


### Authentication

Every call to AutoShares API must include an API secret key. After you create an AutoShares account, we generate API keys for you. To start working with the API with your keys, you need to activate your account.

### Add User Accounts

This API endpoint enables you to bind a new or an existing trading account to an existing user.


### Sign Required Agreements

All users on the system must sign agreements. This GET endpoint enables you to fetch the list of all outstanding agreements that must be signed by the user.

### Connect, Test, Launch



