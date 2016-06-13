
.. _put-set-limits-on-services-for-a-user-account:

Set limits on services for a user account
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    PUT /admin/limits/{project_id}


To set limits on the number of services for a particular ``project_id``, provide a JSON request body with ``limit`` set to a positive integer. Provide the ``project_id`` associated with the user account in the endpoint URL.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |Created                  |The request has been     |
|                          |                         |fulfilled.               |
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





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **limit**               |String *(Required)*      |Specifies the limit on   |
|                          |                         |the number of services   |
|                          |                         |for the ``project_id``.  |
+--------------------------+-------------------------+-------------------------+





**Example: Set limits on services for a user account JSON request**


.. code::

   PUT /v1.0/110011/admin/limits/{project_id} HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "limit": 5
   }





Response
""""""""""""""""










**Example: Set limits on services for a user account HTTP response**


.. code::

   HTP/1.1 201 (Created)




