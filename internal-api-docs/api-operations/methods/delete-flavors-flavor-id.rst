
.. _delete-flavors-flavor-id:

Delete flavor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    DELETE /flavors/{flavor_id}


This operation deletes the flavor specified by flavor_id.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|204                       |No Content               |The server successfully  |
|                          |                         |processed the request,   |
|                          |                         |but is not returning any |
|                          |                         |content.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{flavor_id}               |String *(Required)*      |Specifies the flavor ID. |
|                          |                         |For example: asia        |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example: Delete flavor HTTP request**


.. code::

   DELETE /v1.0/110011/flavors/cdn HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   





Response
""""""""""""""""










**Example: Delete flavor HTTP response**


.. code::

   HTTP/1.1 204 No Content




