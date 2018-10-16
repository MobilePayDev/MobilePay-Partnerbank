# Endpoints
## Products
### /api/v1/products
---
#### GET
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
        	"Product": "MyShop",
            "CustomersCount": 1234
        }
    ]
}
```
### /api/v1/banks/me/customers
---
#### GET
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| product | query |  | No | string |
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
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| registryNumber | path |  | Yes | string |

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
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| registryNumber | path |  | Yes | string |
| from | query |  | Yes | dateTime |
| to | query |  | Yes | dateTime |
| product | query |  | No | string |

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
            "Count": 123,
            "Volume": 123.45,
            "currency": "DKK"
        }
    ]
}
```
### /api/v1/banks/me/transactions
---
#### GET
##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| from | query |  | Yes | dateTime |
| to | query |  | Yes | dateTime |
| product | query |  | No | string |

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
            "Count": 123,
            "Volume": 123.45,
            "currency": "DKK"
        }
    ]
}
```
