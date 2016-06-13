
.. _get-limits-on-services:

Get limits on services for a user account
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/limits/{project_id}



To get limits on the number of services for a particular ``project_id``, provide the ``project_id`` in the endpoint URL of the operation. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{project_id}              |String (*Required*)      |The unique identifier    |
|                          |                         |for the user.            |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example: Get limits on services for a user account HTTP request**


.. code::

   GET /v1.0/110011/admin/limits/{project_id} HTTP/1.1
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
|\ **limit**               |String                   |Specifies the limit on   |
|                          |                         |the number of services   |
|                          |                         |for the ``project_id``.  |
+--------------------------+-------------------------+-------------------------+







**Example: Get limits on services for a user account JSON response**


.. code::

   HTP/1.1 200 (OK)


.. code::

   {
       "limit": 5
   }




