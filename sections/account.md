Account
========

The account object
-------------------

### Attributes

Name | Type | Description
--:|:-:|:--
**object** | string | Is "account".
**created** | integer |
**name** | string |
**email** | string |
**avatar_image_url** | string |
**referral_code** | string | The referral code the user can use to referrer others.


### Example

```json
{
	"object": "account",
	"created": 1412036805,
	"name": "John Doe",
	"email": "test@example.com",
	"avatar_image_url": "http://example.com/image.jpg",
	"referral_code": "V7OAkRU"
}
```

Retreive the account
------------------
Returns the current authenticated user account.

### Example request

	curl https://spaces.com/api/v1/account \
		-u ACCESS_TOKEN:

### Example response

```json
{
	"object": "account",
	"created": 1412036805,
	"name": "John Doe",
	"email": "test@example.com",
	"avatar_image_url": "http://example.com/image.jpg",
	"referral_code": "V7OAkRU"
}
```