# Get Company Logo By Symbol

## Get Company Logo By Symbol

<mark style="color:blue;">`GET`</mark> `baseURL/v{version}/equities/{symbol}/logo`

This endpoint enables you to retrieve company logo image by ticker symbol under which it’s listed on the exchange.

#### Path Parameters

| Name                                         | Type   | Description                                                          |
| -------------------------------------------- | ------ | -------------------------------------------------------------------- |
| apiVersion<mark style="color:red;">\*</mark> | String | The version of API. By default, set it to `1.0`.                     |
| symbol<mark style="color:red;">\*</mark>     | String | Ticker symbol for the company for which you are retrieving an image. |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK 	 Successful request, PNG image of company logo." %}

{% endtab %}
{% endtabs %}
