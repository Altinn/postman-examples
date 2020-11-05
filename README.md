# postman-examples

## Getting started
Install Postman (https://www.getpostman.com/). Signing up for an account is not necessary, you can go straight to the app.

### Importing the collection
In the top left corner is an *import* button. Either drag the `Altinn.postman_collection.json` file from `postman-examples/Collection` into the window or click *choose files* and select it.

### Importing the environments
In the top right corner there is a button with a cog wheel called *manage environments*. Click it, then click the *import* button, then click *choose files*. Select all the json-files in `postman-examples/environments/` and click *open*.

For more information, go to https://altinn.github.io/docs/api/rest/

### Using enterprise certificate authentication
When using [authentication with enterprise certificates](https://altinn.github.io/docs/api/rest/kom-i-gang/) (link in norwegian only), you must configure a [client certificate in Postman](https://learning.getpostman.com/docs/postman/sending-api-requests/certificates/). For testing in dev environment without TLS-termination, you must supply the certificate in Base64 PEM format (without BEGIN/END headers) in a HTTP header named `X-ENV-SSL_CLIENT_CERTIFICATE` for authorization to take place. 

For all non-dev environments, all requests must include the query parameter `ForceEIAuthentication` in order for TLS client authentication to take place. This is already included in all service owner operations.

### Using Bearer token authentication
When using [authentication with Maskinporten](https://altinn.github.io/docs/api/rest/kom-i-gang/) (link in norwegian only), you must configure the requests in postman for [Bearer token](https://learning.postman.com/docs/sending-requests/authorization/#bearer-token).
This can also be combined with the [MaskinportenTokenGenerator](https://github.com/Altinn/MaskinportenTokenGenerator) utility, which can be used to retrieve and set the bearer token on the request through a [pre-request script](https://github.com/Altinn/MaskinportenTokenGenerator#postman-integration).