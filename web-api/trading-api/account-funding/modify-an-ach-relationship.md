# Modify an ACH Relationship

This endpoint enables you to modify a bank name of the existing ACH relationship.

## Update An ACH Relationship

<mark style="color:orange;">`POST`</mark> https://apidev.autoshares.dev/cashiering/GetACHProfiles\[\&acct\_no]\[\&acct\_type]\[\&Cashiering\_Profile]

This endpoint enables you to update existing ACH relationship profile.

## Get A Specific ACH Relationship

<mark style="color:blue;">`GET`</mark> https://apidev.autoshares.dev/cashiering/UpdateACHProfile

#### Path Parameters

| Name                     | Type    | Description                                                                                                                                                                                                                      |
| ------------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| acct\_no                 | String  | account number tied to the logged in profile                                                                                                                                                                                     |
| acct\_type               | String  | <p>Single character :  C or M etc., </p><p>Types of accounts</p><ul><li>C: Cash</li><li>M: Margin</li><li>P: Portfolio Margin</li><li>G: General Ledger</li><li>D: DVP/RVP</li><li>F: Corr. Flip</li><li>H: House/Firm</li></ul> |
| Cashiering\_Profile      | String  | account id : Ex: "CHECKING-USD"                                                                                                                                                                                                  |
| correspondentFirmEnabled | boolean | true or false Set the status of the profile as enabled (true) or disabled (false). When profiles are created, they are set as enabled by default.                                                                                |

#### Response

{% tabs %}
{% tab title="200 Successful request, JSON object containing information about the ACH relationship is returned." %}
```javascript

[{
    
    "requestID": "string",
    "responseStatus": "OK",
    "responseMessage": "string"
}]

```
{% endtab %}
{% endtabs %}
