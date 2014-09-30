Resource Subscription
========

The resource subscription is based in [REST Hooks](http://resthooks.org/).

The customer object
-------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "resource_subscription".
**event** | string |
**target_url** | string |
**api_version** | string |
**created** | integer |


### Example

```json
{
	"object": "resource_subscription",
	"event": "customer.created",
	"target_url": "http://example.com/resource_subscription_example",
	"api_version": "04-09-2014",
	"created":1412036808
}
```

Create a resource subscription
---------------------------
A resource subscription can be created over the API.

### Arguments

Name | Required/Optional | Description
--:|:-:|:--
**event** | required | The event to trigger for.
**target_url** | required | The target URL to send webhooks to.

### Example request create

	$ curl https://spaces.com/api/v1/resource_subscriptions \
		-u ACCESS_TOKEN: \
		-d event="customer.created" \
		-d target_url="http://example.com/resource_subscription_example"

### Example response

Will respond with `200 OK` status, and the full resource subscription object if valid, or fail with failure HTTP status code.

List all resource subscriptions
------------------
Returns a list of all resource subscriptions.

### Example request

	curl https://spaces.com/api/v1/resource_subscriptions \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 20,
	"has_more": true,
	"data": [
		{
			"object": "resource_subscription",
			"event": "customer.created",
			"target_url": "http://example.com/resource_subscription_example",
			"api_version": "04-09-2014",
			"created":1412036808
		},
		{...}
	]
}
```