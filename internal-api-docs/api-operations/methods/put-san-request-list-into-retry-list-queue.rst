
.. _put-san-request-list-into-retry-list-queue:

Put a SAN request list into the retry list queue
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    PUT /admin/provider/akamai/ssl_certificate/retry_list


This operation puts a new SAN request list into the SAN retry list queue.

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








This table shows the body parameters for the request:

+------------------------+------------------------+----------------------------+
|Name                    |Type                    |Description                 |
+========================+========================+============================+
|\ **project_id**        |String (*Required*)     |Specifies the associated    |
|                        |                        |identifier for the user     |
|                        |                        |account, such as, 12345.    |
+------------------------+------------------------+----------------------------+
|\ **domain_name**       |String (*Required*)     |Specifies a string          |
|                        |                        |representing the domain,    |
|                        |                        |such as                     |
|                        |                        |``test_san1.cnamecdn.com``. |
+------------------------+------------------------+----------------------------+
|\ **flavor_id**         |String (*Required*)     |Specifies the CDN-provider  |
|                        |                        |flavor id that is used.     |
+------------------------+------------------------+----------------------------+
|\ **validate_service**  |String (*Required*)     |Indicates whether the       |
|                        |                        |domain is validated as      |
|                        |                        |belonging to an existing    |
|                        |                        |service. Valid values are   |
|                        |                        |``true`` and ``false``.     |
+------------------------+------------------------+----------------------------+





**Example: Put a SAN request list into the retry list queue JSON request**


.. code::

   PUT /v1.0/110011/admin/provider/akamai/ssl_certificate/retry_list HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json


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





Response
""""""""""""""""





This table shows the body parameters for the response:

+------------------------+------------------------+----------------------------+
|Name                    |Type                    |Description                 |
+========================+========================+============================+
|\ **queue**             |String                  |Indicates the retry list    |
|                        |                        |queue.                      |
+------------------------+------------------------+----------------------------+
|queue.\ **project_id**  |String                  |Specifies the associated    |
|                        |                        |identifier for the user     |
|                        |                        |account, such as, 12345.    |
+------------------------+------------------------+----------------------------+
|queue.\ **domain_name** |String                  |Specifies a string          |
|                        |                        |representing the domain,    |
|                        |                        |such as                     |
|                        |                        |``test_san1.cnamecdn.com``. |
+------------------------+------------------------+----------------------------+
|queue.\ **flavor_id**   |String                  |Specifies the CDN-provider  |
|                        |                        |flavor id that is used.     |
+------------------------+------------------------+----------------------------+
|\ **deleted**           |String                  |Specifies any requests that |
|                        |                        |are deleted from the queue. |
+------------------------+------------------------+----------------------------+







**Example: Put a SAN request list into the retry list queue JSON response**


.. code::

   HTP/1.1 202 (Accepted)


.. code::

   {
     "queue": [
       {
         "project_id": "002",
         "domain_name": "test_san1.cnamecdn.com",
         "flavor_id": "cdn"
       },
       {
         "project_id": "000",
         "domain_name": "test_san2.cnamecdn.com",
         "flavor_id": "cdn"
       }
     ],
     "deleted": []
   }
