Webhook
=======

The webhooks will attempt delivery each hour until delivered, or until 24 tries.

The webhook object
------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "webhook"
**created** | integer |
**url** | string |
**event** | object |
**pending** | boolean | Whether the webhook is yet to be delivered or not.

### Example

```json
{
	"object": "webhook",
	"created": 1412106939,
	"url": "http://example.com/webhook_location_example",
	"event": {
		"object": "event",
		"created": 1412106939,
		"type": "customer.created",
		"data": {
			"object": {
				"object": "customer",
				"id": "CUSTOMER_TOKEN",
				"name": "John Doe",
				"email": "test@example.com",
				"created": 1412106939
			}
		}
	},
	"pending": true
}
```

List all webhooks
-----------------
Returns a list of all webhooks.

### Example request

	$ curl https://spaces.com/api/v1/webhooks \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 2,
	"data": [
		{
			"object": "webhook",
			"created": 1412106939,
			"url": "http://example.com/webhook_location_example",
			"event": {
				"object": "event",
				"created": 1412106939,
				"type": "customer.created",
				"data": {
					"object": {
						"object": "customer",
						"id": "CUSTOMER_TOKEN",
						"name": "John Doe",
						"email": "test@example.com",
						"created": 1412106939
					}
				}
			},
			"pending": true
		},
		{...}
	]
}
```