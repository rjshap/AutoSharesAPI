# Deposit / Withdraw Funds via ACH

This endpoint enables you to deposit or withdraw funds to/from an ACH-based banking account.

Create a new request to transfer funds to or from a linked bank account via ACH transfer.



{% hint style="info" %}
Deposits and withdrawals performed through ACH relationships will be reflected in trading account balances before the start of the following trading session (after AutoShares receives SOD files).
{% endhint %}

## Send An ACH Transfer To The Clearing Firm

<mark style="color:green;">`POST`</mark> `https://apidev.autoshares.dev/cashiering/AddACHRequest`

{% tabs %}
{% tab title="Example  Request JSON" %}
```
{
   "corr": "VLNT",
    "office": "001",
    "acct_no": "ABC123",
    "acct_type": "C",
    "cashiering_Profile": "CHECKING-USD",
    "value_dt": "12/1/2021",
    "amount": 1500,
    "comment": "Requested by John Smith at 9:59AM EST 12/1/2021",
    "externalRefID": "ABC123456",
    "withdrawFullBalance": false,
    "fee_amt": 0,
    "irA_Contribution_Type": "_0100",
    "irA_Distribution_Type": "_0000",
    "irA_Tax_Code": "_1",
    "irA_Year": 2022,
    "irA_FederalWithholding": 1000,
    "irA_StateWithholding": 500,
    "irA_State": "NY
 }
```
{% endtab %}
{% endtabs %}

#### Path Parameters

| Name                                                  | Type    | Description                                    |
| ----------------------------------------------------- | ------- | ---------------------------------------------- |
| accountno<mark style="color:red;">\*</mark>           | String  | The version of the API. By default it's `1.0`. |
| cashiering\_profile<mark style="color:red;">\*</mark> | Integer | ID of the trading account.                     |
| amount                                                | integer | amount of withdrawal or deposit                |

#### Response

{% tabs %}
{% tab title="200 Successful request, the ACH transfer was successfully sent to the clearing firm." %}
```
{
  
    "requestID": "string",
    "responseStatus": "OK",
    "responseMessage": "string",
    "cashID": "944074a8-63bc-4d94-a9a7-2f57309fe415",
    "externalRefID": "123456789ABCDEFD"

}
```
{% endtab %}
{% endtabs %}

```javascript
```
