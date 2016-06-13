.. _get-certificates-by-status:

Get certificates by certificate status 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/certificates

To get certificate information by certificate ``status``, provide ``status`` as a query parameter in the endpoint URL of the operation. Valid values for ``status`` are ``deployed``, ``failed``, ``create_in_progress``, or ``cancelled``. No JSON request body is required. 



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
|status                    |String *(Required)*      |Specifies the status for |
|                          |                         |which you want to list   |
|                          |                         |certificates. Valid      |
|                          |                         |values for ``status``    |
|                          |                         |are ``deployed``,        |
|                          |                         |``failed``, or           |
|                          |                         |``create_in_progress``,  |
|                          |                         |``cancelled``.           |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example: Get certificates by certificate status HTTP request**


.. code::

   GET /v1.0/110011/admin/certificates?status=deployed HTTP/1.1
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
|                          |                         |name for the certificate.|
+--------------------------+-------------------------+-------------------------+







**Example: Get certificates by certificate status JSON response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   {
       "domain_name": "www.example.com"
   }




