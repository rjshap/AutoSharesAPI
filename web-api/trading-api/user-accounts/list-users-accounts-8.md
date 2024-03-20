# Update Alias Account For Current User

## Overview

This endpoint enables users to add or update an alias for a trading account.

An alias serves as a nickname or custom label for the account, providing an alternative name for easier identification and navigation.

For instance, if a client shares an account with their spouse, they can add an alias like "Family Account" to refer to it instead of using the account number.

## Update Alias Account For Current User

<mark style="color:orange;">`PUT`</mark> `baseURL/v{version}/accounts/{accountId}/alias/{alias}`

#### Path Parameters

| Name                                         | Type    | Description                                                                     |
| -------------------------------------------- | ------- | ------------------------------------------------------------------------------- |
| apiVersion<mark style="color:red;">\*</mark> |         | The version of API. By default, set it to `1.0`.                                |
| accountId<mark style="color:red;">\*</mark>  | integer | The internal ID of the trading account to which the alias will be assigned.     |
| alias<mark style="color:red;">\*</mark>      | String  | The custom name (alias) that the user wants to assign to the trading account.\\ |

#### Headers

| Name                                            | Type   | Description                                                                                                                                                             |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | This is the authorization token from the token request. The value of this header must have the following format: `Bearer BQ898r9fefi` (`Bearer` + 1 space + the token). |

{% tabs %}
{% tab title="200: OK Successful request, the alias is assigned to the specified account." %}

{% endtab %}
{% endtabs %}
