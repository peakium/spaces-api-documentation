Captured Email
==============

The captured email object is read only.

The captured email object
-------------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "captured_email".
**email** | string |
**created** | integer |
**space** | object |


### Example

```json
{
	"object": "captured_email",
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

List all captured emails
------------------------
Returns a list of all captured emails.

### Example request

	curl https://spaces.com/api/v1/captured_emails \
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