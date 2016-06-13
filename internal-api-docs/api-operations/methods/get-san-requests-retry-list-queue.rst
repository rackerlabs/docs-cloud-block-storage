
.. _get-san-requests-retry-list-queue:


List SAN requests in retry list queue
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/provider/akamai/ssl_certificate/retry_list



This operation lists all the SAN requests in the SAN retry list queue.

.. note::
   This endpoint is accessible only by users with the ``support`` role in their Cloud Identity service catalog.





This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This operation does not accept a request body.




**Example: List SAN requests in retry list queue HTTP request**


.. code::

   GET /v1.0/110011/admin/provider/akamai/ssl_certificate/retry_list HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json






Response
""""""""""""""""





This table shows the body parameters for the response:

+------------------------+------------------------+----------------------------+
|Name                    |Type                    |Description                 |
+========================+========================+============================+
|\ **project_id**        |String                  |Specifies the associated    |
|                        |                        |identifier for the user     |
|                        |                        |account, such as, 12345.    |
+------------------------+------------------------+----------------------------+
|\ **domain_name**       |String                  |Specifies a string          |
|                        |                        |representing the domain,    |
|                        |                        |such as                     |
|                        |                        |``test_san1.cnamecdn.com``. |
+------------------------+------------------------+----------------------------+
|\ **flavor_id**         |String                  |Specifies the CDN-provider  |
|                        |                        |flavor id that is used.     |
+------------------------+------------------------+----------------------------+
|\ **validate_service**  |String                  |Indicates whether the       |
|                        |                        |domain is validated as      |
|                        |                        |belonging to an existing    |
|                        |                        |service. Valid values are   |
|                        |                        |``true`` and ``false``.     |
+------------------------+------------------------+----------------------------+







**Example: List SAN requests in retry list queue JSON response**


.. code::

   HTTP/1.1 200 OK


.. code::

   [
     {
       "project_id": "002",
       "domain_name": "test_san1.cnamecdn.com",
       "flavor_id": "cdn",
       "validate_service": true
     },
     {
       "project_id": "000",
       "domain_name": "test_san2.cnamecdn.com",
       "flavor_id": "cdn",
       "validate_service": true
     }
   ]
