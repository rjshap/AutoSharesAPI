# Get an ACH Relationship

This endpoint enables you to retrieve information about a specific ACH relationship.

## Get A Specific ACH Relationship

<mark style="color:blue;">`GET`</mark> https://apidev.autoshares.dev/cashiering/GetACHProfiles\[\&acct\_no]\[\&acct\_type]\[\&Cashiering\_Profile]

#### Path Parameters

| Name                | Type   | Description                                  |
| ------------------- | ------ | -------------------------------------------- |
| acct\_no            | String | account number tied to the logged in profile |
| acct\_type          | String | Single character :  C or M etc.,             |
| Cashiering\_Profile | String | account id : Ex: "CHECKING-USD"              |

#### Response

{% tabs %}
{% tab title="200 Successful request, JSON object containing information about the ACH relationship is returned." %}
```javascript

[{
    "requestID": "string",
    "corr": "VLNT",
    "office": "001",
    "acct_no": "ABC123",
    "acct_type": "C",
    "cashiering_Profile": "CHECKING-USD",
    "accountName": "John Smith",
    "accountNumber": "12345678",
    "aba": "021000021",
    "achqToken": "string",
    "createdBy": "string",
    "createdDate": "string",
    "approvedBy": "string",
    "approvedDate": "string",
    "approved": true,
    "comments": "string",
    "clearingFirmEnabled": true,
    "correspondentFirmEnabled": true,
    "thirdPartyVerification": true,
    "thirdPartyVerificationReviewer": "string"
}]

```
{% endtab %}
{% endtabs %}
