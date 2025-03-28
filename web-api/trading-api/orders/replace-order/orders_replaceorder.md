# Syntax

## Replace order

```
PUT /v{version}/accounts/{accountId}/orders/{orderId}
```

### Description

This API endpoint enables you to modify an existing order.

### Parameters

| Type       | Name                                                       | Description                                                                                                                          | Schema                                                             | Default |
| ---------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ | ------- |
| **Header** | <p><strong>Authorization</strong><br><em>required</em></p> | This is the authorization token that you retrieved from the first endpoint (/token).                                                 | string                                                             |         |
| **Path**   | <p><strong>accountId</strong><br><em>required</em></p>     | This is the unique identifier of the trading account on which a new order is to be modified.                                         | integer (int32)                                                    |         |
| **Path**   | <p><strong>orderId</strong><br><em>required</em></p>       | This is the ID of the order that needs to be modified.                                                                               | integer (int32)                                                    |         |
| **Path**   | <p><strong>version</strong><br><em>required</em></p>       | This is the version of the API. Unless you have multiple versions of AutoShares’s API deployed in your environment, leave it at 1.0. | string                                                             | `"1"`   |
| **Body**   | <p><strong>body</strong><br><em>required</em></p>          | This is JSON data that contains updated information about the modified order.                                                        | [ModifyOrderResource](orders\_replaceorder.md#modifyorderresource) |         |

### Responses

| HTTP Code | Description                                                                                                  | Schema                                                 |
| --------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------ |
| **200**   | JSON data with the updated order information is returned, indicating if the order was successfully modified. | [OrderResource](orders\_replaceorder.md#orderresource) |
| **401**   | The access level of the provided authorization token is not sufficient to perform this operation.            | No Content                                             |
| **403**   | The provided Et-App-Key is incorrect.                                                                        | No Content                                             |
| **409**   | Conflict                                                                                                     | No Content                                             |
| **422**   | A validation error occurred while processing the request.                                                    | No Content                                             |
| **500**   | Internal server error                                                                                        | No Content                                             |

### Consumes

* `application/json`
* `text/json`

### Produces

* `application/json`
* `text/json`
