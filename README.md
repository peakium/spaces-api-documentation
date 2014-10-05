Spaces API
===========

The Spaces API is build on REST principles with resource-oriented URL's. The API is using HTTP status codes for errors. All responses will be returned in JSON format.

API Endpoints
-------------
* [Account](/sections/account.md)
* [Captured Email](/sections/captured_email.md)
* [Customer](/sections/customer.md)
* [Event](/sections/event.md)
* [Invoice](/sections/invoice.md)
* [Subscription](/sections/subscription.md)
* [Webhook](/sections/webhook.md)
* [Space](/sections/space.md)
* [Resource Subscription](/sections/resource_subscription.md)

Authentication
--------------
Authentication for the API is granted by using the `access_token` generated through an OAuth 2 application. The API will request authentication via [HTTP Basic Auth](http://en.wikipedia.org/wiki/Basic_access_authentication). For the username, you will use the `access_token`, and for the password you do not need to enter anything.

Please keep your access tokens secure as they allow for many irreversible actions.

Authentication are mandatory for all requests to the API.

Example on authenticating an API request through curl:

	$ curl https://spaces.pe/api/v1/customers \
		-u ACCESS_TOKEN:

SSL
---
All requests are required to be done through HTTPS. Requests over plain HTTP will be rejected.

Errors
------
Spaces uses HTTP status codes to indicate errors (or success). Codes in range 2xx indicates success, codes in 4xx range indicates a client side error (e.g. a missing or invalid parameter), and codes in 5xx range indicates an error in Spaces' system.

### HTTP status code errors

Error | Description
---|---
200 OK | The request was handled and returned correctly
400 Bad Request | Missing a required parameter, or using an invalid parameter
401 Unauthorized | No valid API key used
404 Not Found | A resource was not found
500 Internal Server Error | Something went wrong in Spaces' system

### Error return
The returning JSON on errors will often include the following attributes:

Name | Description
--:|:--
message | A human-readable message giving information about the error.

Versioning
----------
Currently there is no versioning of the API. We're implementing this as soon as there will be breaking changes.

Pagination
----------
Spaces has cursor based pagination for lists of objects.

**Pagination Arguments**

Name | Required | Description
--:|:-:|:--
**limit** | optional | A limit on the number of objects to be returned. Limit can range between 1 and 100 items. Defaults to 20.
**starting_after** | optional | A cursor containing the ID of the object you wish to paginate after. If you have `obj_bar` you wish to paginate after, you can set the subsequent call with `starting_after=obj_bar`.
**starting_before** | optional | A cursor containing the ID of the object you wish to paginate before. If you have `obj_bar` you wish to paginate before, you can set the subsequent call with `starting_after=obj_bar`.

**List Response Format**

Name | type | Description
--:|:-:|:--
**object** | string | Is "list".
**data** | array | An array of objects for the list.
**has_more** | boolean | Wether there is more elements available or not. If false, there is no subsequent pages for the list.


Help us
-------
We always love to hear from you if you have any ideas of how to make the API better. You can contact us directly at <beta@peakium.com> with your suggestions. Also, feel free to fork these docs and send a pull request with improvements!	

Need an account?
----------------
Sign up right now at <https://spaces.pe/>
