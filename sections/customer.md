Customer
========

The customer object is read only.

The customer object
-------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "customer".
**id** | string |
**name** | string |
**email** | string |
**created** | integer |
**space** | object |


### Example

```json
{
	"object": "customer",
	"id": "CUSTOMER_TOKEN",
	"name": "John Doe",
	"email": "test@example.com",
	"created": 1410196557,
	"space": {
		"object": "space",
		"id": 1,
		"created": 1410196557,
		"url": "https://spaces.pe/s/EXAMPLE"
	}
}
```

Retreive a customer
------------------
Returns a specified customer. The customer id is unique among all Spaces for a user.

### Example request

	curl https://spaces.com/api/v1/customers/CUSTOMER_TOKEN \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "customer",
	"id": "CUSTOMER_TOKEN",
	"name": "John Doe",
	"email": "test@example.com",
	"created": 1410196557,
	"space": {
		"object": "space",
		"id": 1,
		"created": 1410196557,
		"url": "https://spaces.pe/s/EXAMPLE"
	}
}
```

List all customers
------------------
Returns a list of all customers.

### Example request

	curl https://spaces.com/api/v1/customers \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 20,
	"has_more": true,
	"data": [
		{
			"object": "customer",
			"id": "CUSTOMER_TOKEN",
			"name": "John Doe",
			"email": "test@example.com",
			"created": 1410196557,
			"space": {
				"object": "space",
				"id": 1,
				"created": 1410196557,
				"url": "https://spaces.pe/s/EXAMPLE"
			}
		},
		{...}
	]
}
```