---
description: Retrieve a trading account's collective market value of all security groups
---

# Get Market Value of all Security Groups

### Introduction‌ <a href="#introduction" id="introduction"></a>

This GET endpoint enables you to retrieve the collective market value of different security groups in a specific trading account.‌

There are five required parameters that must be provided in the request:‌

1. **Authorization** (header). This is the authorization token from the very first [token request](broken-reference). The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token).
2. **API version** (path). Unless necessary, leave it at "1.0".
3. **accountID** (path). This is the internal ID of the trading account whose market value of different security groups must be listed.‌

Here's the final template for this API request:

```
GET apiURL/v1.0/accounts/{accountID}/positions/groups
```

## Response <a href="#response" id="response"></a>

In response to this API request, you'll receive a JSON file with the collective market value of different security groups in the specified trading account.

```javascript
[
  {
    "Name": "Options",
    "MarketValue": -996.5
  },
  {
    "Name": "Equity",
    "MarketValue": 129835.86
  },
  {
    "Name": "Cash",
    "MarketValue": 342377.84999484
  }
]
```

where:

| Parameter   | Description                                                                                                                                                                                                 |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | <p>The security group.</p><p>Possible values:</p><ul><li>FixedIncome</li><li>Equity</li><li>Forex</li><li>Futures</li><li>Other</li><li>Options</li><li>Index</li><li>Cryptocurrency</li><li>Cash</li></ul> |
| MarketValue | The collective market value of all securities of this group in this trading account.                                                                                                                        |

#### Relationship Between Security Types and Groups

The following table lists security types that populate each security group:

| Security Group | Corresponding Security Types                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FixedIncome    | <ul><li>BankersAcceptance</li><li>CertificateOfDeposit</li><li>MortgageObligation</li><li>CorporateBond</li><li>CommercialPaper</li><li>CorporatePrivatePlacement</li><li>FederalHousingAuthority</li><li>FederalHomeLoan</li><li>FederalNationalMortgageAssociation</li><li>GovernmentNationalMortgageAssociation</li><li>TreasuriesPlusAgencyDebenture</li><li>MortgageInterestOnly</li><li>MortgagePrincipleOnly</li><li>MortgagePrivatePlacement</li><li>MunicipalBond</li><li>StudentLoanMarketingAssociation</li><li>TimeDeposit</li><li>UsTreasuryBill</li><li>CatsTigersLions</li><li>ConvertibleBond</li><li>MortgageIoette</li></ul> |
| Equity         | <ul><li>CommonStock</li><li>MutualFund</li><li>PreferredStock</li><li>Warrant</li><li>Right</li><li>ETF</li><li>DepositoryReceipt</li><li>CoveredWarrant</li><li>Unit</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Forex          | <ul><li>ForeignExchangeContract</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Futures        | <ul><li>Future</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Options        | <ul><li>Option</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Index          | <ul><li>Index</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Cryptocurrency | <ul><li>Cryptocurrency</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Other          | <ul><li>MiscellaneousPassThru</li><li>NoIsitcSecurityType</li><li>RepurchaseAgreement</li><li>ReverseRepurchaseAgreement</li><li>WildcardEntry</li><li>FakeStockForNonStandartOption</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

### Common Mistakes

Here are some of the common mistakes that developers make when attempting to fetch the collective market value of different security groups in a specific trading account.‌

### &#x20;<a href="#failing-to-specify-the-et-app-key-parameter" id="failing-to-specify-the-et-app-key-parameter"></a>

### Specifying the User ID Instead of the Trading Account ID <a href="#specifying-the-user-id-instead-of-the-trading-account-id" id="specifying-the-user-id-instead-of-the-trading-account-id"></a>

Another common mistake when making this request is specifying the user ID instead of the user's trading account ID. Doing so will result in the 500 status code and the following error message:

```
{    "message": "An error occurred while processing your request",    "error": "Unexpected server error"}
```
