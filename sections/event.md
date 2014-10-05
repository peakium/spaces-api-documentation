Event
=====
Events are created when something happens to your data. It can be that a new customer has be created, or a subscription has been cancelled. When an event is created, it will try to send webhooks out through the application webhook URL, the user webhook URL's, and/or the REST Hook URL's.

The event object
----------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "event".
**created** | integer |
**type** | string | The event type.
**data** | object | Referencing data. E.g. customer, invoice or subscription.

### Example

```json
{
	"object": "event",
	"created": 1410196574,
	"type": "customer.created",
	"data": {
		"object": { 
			"object": "customer",
			"token": "CUSTOMER_TOKEN",
			"name": "John Doe",
			"email": "test@example.com",
			"created": 1410196574
		}
	}
}
```

Event types
-----------

Event | Description
--:|:--
**customer.created** | A customer has been created
**invoice.created** | An invoice has been created.
**invoice.paid** | An invoice has been paid.
**subscription.created** | A subscription has been created.
**captured_email.created** | An email has been captured through a capture email section.


List all events
---------------
Returns a list of all events.

### Arguments

### Example request

	$ curl https://spaces.com/api/v1/events \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 20,
	"has_more": true,
	"data": [
		{
			"object": "event",
			"created": 1410196574,
			"type": "customer.created",
			"data": {
				"object": { 
					"object": "customer",
					"token": "CUSTOMER_TOKEN",
					"name": "John Doe",
					"email": "test@example.com",
					"created": 1410196574
				}
			}
		},
		{...}
	]
}
```