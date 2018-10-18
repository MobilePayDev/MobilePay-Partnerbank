The documentation provides an example response for each API method. The example response illustrates all attributes that are returned by that method.


# Endpoints
## Products
### /api/v1/products
---
#### GET
Returns all available MobilePay products.
##### Parameters

*No parameters*

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetProductsResponse](#GetProductsResponse) |

##### Schemas
###### GetProductsResponse
*Example:*
```json
{
    "products": [
        {
            "name": "MyShop"
        }
    ]
}
```
## Banks
### /api/v1/banks/me/product-statistics
---
#### GET
Returns number of customers who use particular products.
##### Parameters

*No parameters*

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetProductStatisticsResponse](#GetProductStatisticsResponse) |
##### Schemas
###### GetProductStatisticsResponse
*Example:*
```json
{
    "products": [
        {
            "product": "MyShop",
            "customersCount": 1234
        }
    ]
}
```
### /api/v1/banks/me/customers
---
#### GET
Returns a list of all customers or customers who use given product.
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| product | query | MobilePay product eg "MyShop" | No | string |
| offset | query |  | No | integer |
| limit | query |  | No | integer |

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetCustomersResponse](#GetCustomersResponse) |

##### Schemas
###### GetCustomersResponse
*Example:*
```json
{
    "items": [
        {
            "registryNumber": "ABC1234"
        }
    ]
}
```
### /api/v1/banks/me/customers/{registryNumber}/products
---
#### GET
Returns a list of products used by given customer.
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| registryNumber | path | CVR in Denmark, VAT in Finland | Yes | string |

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetCustomerProductsResponse](#GetCustomerProductsResponse) |

##### Schemas
###### GetCustomerProductsResponse
*Example:*
```json
{
    "products": [
        {
            "name": "MyShop"
        }
    ]
}
```
### /api/v1/banks/me/customers/{registryNumber}/transactions
---
#### GET
Returns aggregated data about transactions (grouped by product) for given customer.
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| registryNumber | path | CVR in Denmark, VAT in Finland | Yes | string |
| from | query |  | Yes | dateTime |
| to | query |  | Yes | dateTime |
| product | query | MobilePay product eg "MyShop" | No | string |

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetCustomerTransactionsResponse](#GetCustomerTransactionsResponse) |

##### Schemas
###### GetCustomerTransactionsResponse
*Example:*
```json
{
    "transactions": [
        {
            "product": "MyShop",
            "count": 123,
            "volume": 123.45,
            "currency": "DKK"
        }
    ]
}
```
### /api/v1/banks/me/transactions
---
#### GET
Returns aggregated data about all transactions (grouped by product).
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| from | query |  | Yes | dateTime |
| to | query |  | Yes | dateTime |
| product | query | MobilePay product eg "MyShop" | No | string |

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | Success | [GetTransactionsResponse](#GetTransactionsResponse) |

##### Schemas
###### GetTransactionsResponse
*Example:*
```json
{
    "transactions": [
        {
            "product": "MyShop",
            "count": 123,
            "volume": 123.45,
            "currency": "DKK"
        }
    ]
}
```
