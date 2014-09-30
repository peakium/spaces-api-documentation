Subscription
============

A subscription object is always tied to a [Customer](/sections/customer.md). The subscription token is only unique within the customer scope. For this reason, when you are handling individual subscriptions, you are always required to use the [Customer](/sections/customer.md) resource.

The subscription object
-----------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "subscription"
**token** | string | The token is under the scope of a customer.
**serial_number** | integer | The sequential number for the subscription within the scope of the Space.
**created** | integer |
**items** | object | A list of invoice items for the subscription.
**items**->**data** | array | The list of invoice items.
**items**->**count** | integer | Number of invoice items.
**total** | integer | The fractional amount paid.
**currency** | integer | The currency paid in.
**customer** | object |

### Example

```json
{
	"object": "subscription",
	"token": "SUBSCRIPTION_TOKEN",
	"serial_number": 1,
	"created": 1410196578,
	"status": "active",
	"items": {
		"data": [
			{
				"object": "subscription_item",
				"item_id": "100100",
				"description": "Product 7",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1200,
				"total_amount": 1200
			},
			{
				"object": "subscription_item",
				"item_id": 101,
				"description": "Domestic shipping",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1000,
				"total_amount": 1000
			}
		],
		"count": 2
	},
	"total": 2200,
	"currency": "USD",
	"customer": {
		"object": "customer",
		"token": "CUSTOMER_TOKEN",
		"name": "John Doe",
		"email": "test@example.com",
		"created": 1410196578
	}
}
```

Retrieve a subscription
--------------------------------
To retrieve a specific subscription resource, you need to use the [Customer](/sections/customer.md) resource for the subscription in the URI.

### Example request

	$ curl https://spaces.com/api/v1/customers/CUSTOMER_TOKEN/subscriptions/SUBSCRIPTION_TOKEN \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "subscription",
	"token": "SUBSCRIPTION_TOKEN",
	"serial_number": 1,
	"created": 1410196578,
	"status": "active",
	"items": {
		"data": [
			{
				"object": "subscription_item",
				"item_id": "100100",
				"description": "Product 7",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1200,
				"total_amount": 1200
			},
			{
				"object": "subscription_item",
				"item_id": 101,
				"description": "Domestic shipping",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1000,
				"total_amount": 1000
			}
		],
		"count": 2
	},
	"total": 2200,
	"currency": "USD",
	"customer": {
		"object": "customer",
		"token": "CUSTOMER_TOKEN",
		"name": "John Doe",
		"email": "test@example.com",
		"created": 1410196578
	}
}
```

List all subscriptions
----------------------
Returns a list of all subscriptions.

### Example request

	$ curl https://spaces.com/api/v1/subscriptions \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 2,
	"data": [
		{
			"object": "subscription",
			"token": "SUBSCRIPTION_TOKEN",
			"serial_number": 1,
			"created": 1410196578,
			"status": "active",
			"items": {
				"data": [
					{
						"object": "subscription_item",
						"item_id": "100100",
						"description": "Product 7",
						"quantity": 1,
						"discount": 0,
						"unit_amount": 1200,
						"total_amount": 1200
					},
					{
						"object": "subscription_item",
						"item_id": 101,
						"description": "Domestic shipping",
						"quantity": 1,
						"discount": 0,
						"unit_amount": 1000,
						"total_amount": 1000
					}
				],
				"count": 2
			},
			"total": 2200,
			"currency": "USD",
			"customer": {
				"object": "customer",
				"token": "CUSTOMER_TOKEN",
				"name": "John Doe",
				"email": "test@example.com",
				"created": 1410196578
			}
		},
		{...}
	]
}
```