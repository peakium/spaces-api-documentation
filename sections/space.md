Space
=====

The Space object is read only.

The Space object
----------------

### Attributes

Name | Type | Description
--:|:-:|:--
**id** | integer | ID is sequentially running starting from 1.
**object** | string | Is "space".
**created** | integer |
**url** | string | If null, the space is not publicly available.


### Example

```json
{
	"object": "space",
	"id": 1,
	"created": 1410196557,
	"url": "https://spaces.pe/s/EXAMPLE"
}
```

Retrieve a Space
----------------
Returns a specified Space.

### Example request

	$ curl https://spaces.com/api/v1/spaces/1 \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "space",
	"id": 1,
	"created": 1410196557,
	"url": "https://spaces.pe/s/EXAMPLE"
}
```

List all Spaces
---------------
Returns a list of all Spaces.

### Example request

	curl https://spaces.com/api/v1/spaces \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "list",
	"count": 20,
	"has_more": true,
	"data": [
		{
			"object": "space",
			"id": 1,
			"created": 1410196557,
			"url": "https://spaces.pe/s/EXAMPLE"
		},
		{...}
	]
}
```