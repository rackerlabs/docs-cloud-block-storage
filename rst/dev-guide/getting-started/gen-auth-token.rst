.. _gsg-gen-auth-token:

Generating an authentication token
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Your first step must always be to generate an authentication token. You
must then include the authentication token in each request in the
``X-Auth-Token`` header.

For more details about authentication, see the *Cloud Block Storage
Developer Guide*.

Remember to replace the placeholders in the following authentication
request example with your information:

-  **yourUserName** —Your common Rackspace Cloud user name, as supplied
   during registration.

-  **yourApiKey** — Your API key.

This guide uses **yourUserName** and **yourApiKey** for authentication.
For information about other supported authentication methods, see the
`Authentication
tokens <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/Token_Calls.html>`__
in the *Cloud Identity Client Developer Guide*.

Use the following global endpoint to access the Cloud Identity service
for authentication:

-  https://identity.api.rackspacecloud.com/v2.0/

In the following example, you authenticate using
``https://identity.api.rackspacecloud.com/v2.0/tokens``, the URL for the
Cloud Identity services. The ``v2.0`` component in the URL indicates
that you are using version 2.0 of the Cloud Identity API.

The cURL request uses the ``-d`` option to send the specified data in a
**POST** request to the HTTP server.

 
**Example: cURL authentication request: JSON**

.. code::  

   curl -d \
    '{
        "auth":
        {
           "RAX-KSKEY:apiKeyCredentials":
           {
              "username": "yourUserName",
              "apiKey": "yourApiKey"}
        }
    }' \
    -H 'Content-Type: application/json' \
    'https://identity.api.rackspacecloud.com/v2.0/tokens' | python  -m  json.tool 

An HTTP status code of 200 (OK) in the response indicates that the
authentication request completed successfully.

In the authentication response, the authentication token ``id`` is
returned with an ``expires`` attribute that specifies when the token
expires. Tokens are valid for a finite duration, typically for 24 hours.
Remember to supply your authentication token wherever you see the
placeholder **yourAuthToken** in the examples in this guide.

The authentication response also contains the service catalog, which
provides endpoints for Rackspace Cloud services. For example,
``https://dfw.blockstorage.api.rackspacecloud.com/v1/``\ ``1234``/) is
one of the ``publicURL`` endpoints for Cloud Block Storage in the
service catalog.

Your actual account number is after the final slash (/) in the
``publicURL`` field, such as ``1234`` in the preceding endpoint. You
must specify your account number in the Cloud Block Storage API request,
wherever you see the placeholder **yourAccountID** specified in the
examples in this guide.

 
**: Authenticate response with partial service catalog
showing cloudBlockStorage: JSON**

.. code::  

   HTTP/1.1 200 OK
   Date: Tue, 06 May 2014 18:33:04 GMT
   Content-Type: application/json

   {
        "access": {
            "token": {
                "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "expires": "2014-05-07T07:37:46.317Z",
                "tenant": {
                    "id": "xxxxxx",
                    "name": "xxxxxx"
                },
                "RAX-AUTH:authenticatedBy": [
                                             "APIKEY"
                                             ]
            },
            "serviceCatalog": [
                {
                    "name": "cloudBlockStorage",
                    "endpoints": [
                    {
                        "region": "SYD",
                        "tenantId": "xxxxxx",
                        "publicURL": "https://syd.blockstorage.api.rackspacecloud.com/v1/xxxxxx"
                    },
                    {
                        "region": "DFW",
                        "tenantId": "xxxxxx",
                        "publicURL": "https://dfw.blockstorage.api.rackspacecloud.com/v1/xxxxxx"
                    },
                    {
                        "region": "ORD",
                        "tenantId": "xxxxxx",
                        "publicURL": "https://ord.blockstorage.api.rackspacecloud.com/v1/830866"
                    },
                    {
                        "region": "IAD",
                        "tenantId": "xxxxxx",
                        "publicURL": "https://iad.blockstorage.api.rackspacecloud.com/v1/830866"
                    },
                    {
                        "region": "HKG",
                        "tenantId": "xxxxxx",
                        "publicURL": "https://hkg.blockstorage.api.rackspacecloud.com/v1/830866"
                    }
                ],
                "type": "volume"
                }
            ]
        }
    }

After authentication, you can use cURL to perform **POST**, **GET**,
**PUT**, and **DELETE** requests for the Cloud Block Storage API.
