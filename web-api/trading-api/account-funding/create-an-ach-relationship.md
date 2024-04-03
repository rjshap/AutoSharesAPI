---
description: Establish and bind an ACH relationship to a trading account.
---

# Create A New ACH Relationship

### Overview

After a trader has created a new [trading account](../trading-accounts/open-a-new-trading-account.md), they should proceed to deposit funds into it. AutoShares provides native functionality for managing deposits and withdrawals by means of ACH relationships. Essentially, a trader must establish an ACH relationship with their banking account and, once it's done, use it to deposit and withdraw funds to/from their banking account through AutoShares's web terminal and iOS apps.

After an ACH relationship is established, it'll take some time for the clearing firm to approve it. If the data provided via this API request matches their data (name, etc.), the relationships will be established immediately. However, if there is a mismatch in the name, It will need to be review by the Correspondent via the Portal. From the portal the Correspondent can reject the request or approve it, depending on the mismatch. A bank statement my be required for validation.

Note that some clearing firms put limitations on the number of ACH relationships that can be established for one trading account. For AutoShares, you can establish up to **two** ACH relationships per trading account.

{% hint style="info" %}
Establishment of ACH relationships is available only for real trading accounts. If you attempt to establish an ACH relationship for a paper trading account, the request will fall through.
{% endhint %}

## Create A New ACH Relationship

<mark style="color:green;">`POST`</mark> `baseURL/v{version}/accounts/{accountId}/ach-relationships`

<mark style="color:green;">`POST`</mark>  https://apidev.autoshares.dev/cashiering/AddACHProfileByPlaidToken

#### Path Parameters

| Name                                         | Type   | Description                                                                                          |
| -------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------- |
| acct\_no<mark style="color:red;">\*</mark>   | String | This is the account number tied to the login profile                                                 |
| acct\_type<mark style="color:red;">\*</mark> | String | This is account type that distinguishes whether it is cash, margin etc., (valid values C , M ..etc,) |
| cashiering\_profile                          | String | ex: "CHECKING-USD"                                                                                   |
| accountName                                  | String | ex: "John Doe"                                                                                       |
| plaidToken                                   | String | Assumes you already established relation with plaid and obtained a token                             |
| thirdpartyverification                       | boolen | true or false                                                                                        |
| thirdpartyverificationReviewer               | String | name of reviewer                                                                                     |

#### Headers

| Name         | Type   | Description                |
| ------------ | ------ | -------------------------- |
| Corr, Office | String | These are sent via gateway |

#### Response

{ "requestID": "string", "responseStatus": "OK", "responseMessage": "string" }

### Request Body

The body of this request represents the information about the to-be-established ACH relationship. It must be sent in the JSON format with the parameters described in the following example:

{ "corr": "VLNT", "office": "001", "acct\_no": "ABC123", "acct\_type": "C", "cashiering\_Profile": "CHECKING-USD", "accountName": "John Smith", "plaidToken": "processor-sandbox-f0758e12-9ce7-4bf9-b46f-6a9adfbf4df4", "thirdPartyVerification": true, "thirdPartyVerificationReviewer": "string" }
