Invoice
=======

The invoice object belongs to a customer.

The invoice object
------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "invoice".
**id** | string |
**created** | integer |
**order_number** | integer | The sequential order number. It's scoped to the Space.
**billing_address** | object | A JSON object containing an address field.
**shipping_address** | object | A JSON object containing an address field.
**paid** | boolean |
**shipped** | boolean |
**shipping_details** | string | A message sent to the customer when the order was marked as shipped.
**total** | integer | The fractional amount paid.
**currency** | integer | The currency paid in.
**items** | object | The invoice items.
**items**->**data** | array | The list of invoice items.
**items**->**count** | integer | Number of invoice items.
**customer** | object |

### Example

```json
{
	"object": "invoice",
	"id": "INVOICE_TOKEN",
	"order_number": 1,
	"billing_address": {
		"line_1": "SpaceX",
		"line_2": "1 Rocket Rd",
		"line_3": "",
		"zip_code": "90250",
		"locality": "Hawthorne",
		"region": "CA",
		"country":"US"
	},
	"shipping_address": null,
	"created": 1410196576,
	"paid": false,
	"shipped": false,
	"shipping_details": null,
	"total": 1200,
	"currency": "USD",
	"items": {
		"data": [
			{
				"object": "invoice_item",
				"item_id": "100100",
				"description": "Product 1",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1200,
				"total_amount": 1200,
				"currency": "USD",
				"date_range_start": null,
				"date_range_end": null
			},
			{
				"object": "invoice_item",
				"item_id": 101,
				"description": "Domestic shipping",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1000,
				"total_amount": 1000,
				"currency": "USD",
				"date_range_start": null,
				"date_range_end": null
			}
		],
		"count": 2
	},
	"customer": {
		"object": "customer",
		"id": "CUSTOMER_TOKEN",
		"name": "John Doe",
		"email": "test@example.com",
		"created": 1410196576,
		"space": {
			"object": "space",
			"id": 1,
			"created": 1410196557,
			"url": "https://spaces.pe/s/EXAMPLE"
		}
	}
}
```

Retrieve an invoice
-------------------
Returns a specified invoice. The invoice id is unique among all Spaces for a user.

### Example request

	$ curl https://spaces.com/api/v1/invoices/INVOICE_TOKEN \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "invoice",
	"id": "INVOICE_TOKEN",
	"order_number": 1,
	"billing_address": {
		"line_1": "SpaceX",
		"line_2": "1 Rocket Rd",
		"line_3": "",
		"zip_code": "90250",
		"locality": "Hawthorne",
		"region": "CA",
		"country":"US"
	},
	"shipping_address": null,
	"created": 1410196576,
	"paid": false,
	"shipped": false,
	"shipping_details": null,
	"total": 1200,
	"currency": "USD",
	"items": {
		"data": [
			{
				"object": "invoice_item",
				"item_id": "100100",
				"description": "Product 1",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1200,
				"total_amount": 1200,
				"currency": "USD",
				"date_range_start": null,
				"date_range_end": null
			},
			{
				"object": "invoice_item",
				"item_id": 101,
				"description": "Domestic shipping",
				"quantity": 1,
				"discount": 0,
				"unit_amount": 1000,
				"total_amount": 1000,
				"currency": "USD",
				"date_range_start": null,
				"date_range_end": null
			}
		],
		"count": 2
	},
	"customer": {
		"object": "customer",
		"id": "CUSTOMER_TOKEN",
		"name": "John Doe",
		"email": "test@example.com",
		"created": 1410196576,
		"space": {
			"object": "space",
			"id": 1,
			"created": 1410196557,
			"url": "https://spaces.pe/s/EXAMPLE"
		}
	}
}
```

List all invoices
-----------------
Returns a list of all invoices.

### Example request

	$ curl https://spaces.com/api/v1/invoices \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 2,
	"data": [
		{
			"object": "invoice",
			"id": "INVOICE_TOKEN",
			"order_number": 1,
			"billing_address": {
				"line_1": "SpaceX",
				"line_2": "1 Rocket Rd",
				"line_3": "",
				"zip_code": "90250",
				"locality": "Hawthorne",
				"region": "CA",
				"country":"US"
			},
			"shipping_address": null,
			"created": 1410196576,
			"paid": false,
			"shipped": false,
			"shipping_details": null,
			"total": 1200,
			"currency": "USD",
			"items": {
				"data": [
					{
						"object": "invoice_item",
						"item_id": "100100",
						"description": "Product 1",
						"quantity": 1,
						"discount": 0,
						"unit_amount": 1200,
						"total_amount": 1200,
						"currency": "USD",
						"date_range_start": null,
						"date_range_end": null
					},
					{
						"object": "invoice_item",
						"item_id": 101,
						"description": "Domestic shipping",
						"quantity": 1,
						"discount": 0,
						"unit_amount": 1000,
						"total_amount": 1000,
						"currency": "USD",
						"date_range_start": null,
						"date_range_end": null
					}
				],
				"count": 2
			}
		},
		"customer": {
			"object": "customer",
			"id": "CUSTOMER_TOKEN",
			"name": "John Doe",
			"email": "test@example.com",
			"created": 1410196576,
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