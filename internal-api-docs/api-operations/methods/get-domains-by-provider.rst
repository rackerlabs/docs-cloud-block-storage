
.. _get-get-domains-by-provider-url-admin-domains:

Get domains by provider URL 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/domains


To retrieve the domains by provider URL, provide ``provider_url`` as a query parameter in the endpoint URL of the operation. 				No JSON request body is required. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|provider_url              |String *(Required)*      |Specifies the provider   |
|                          |                         |URL for which you want   |
|                          |                         |to retrieve domains. The |
|                          |                         |provider URL is the      |
|                          |                         |domain to which the      |
|                          |                         |CNAME is set for the     |
|                          |                         |Rackspace operator_url   |
|                          |                         |per domain.              |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example: Get domains by provider URL HTTP request**


.. code::

   GET /v1.0/110011/admin/domains?provider_url=www.example.provider.com HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **domain_name**         |String                   |Specifies the domain     |
|                          |                         |name or names found for  |
|                          |                         |the specified provider   |
|                          |                         |URL.                     |
+--------------------------+-------------------------+-------------------------+







**Example: Get domains by provider URL JSON response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   [
       {
         "domain_name": "blog.example.com"
       },
       {
         "domain_name": "css.mywebsite.com"
       }
   ]




