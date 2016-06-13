
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-post-service-action-admin-services-action:

Post service action
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /admin/services/action

This operation changes the operator status of, or enables, disables, or deletes services for a ``project_id`` or a domain.

To change the operator status of or delete services for a ``project_id`` or a domain, provide a JSON request body with ``action`` set to ``enable``, ``disable``, or ``delete``, along with the ``project_id`` of the user or the ``domain``. 



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

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **project_id**          |String *(Required)*      |Specifies the associated |
|                          |                         |identifier for the user  |
|                          |                         |account, such as, 12345. |
+--------------------------+-------------------------+-------------------------+
|\ **action**              |String *(Required)*      |Specifies the action to  |
|                          |                         |perform, such as         |
|                          |                         |``enable``, ``disable``, |
|                          |                         |or ``delete``.           |
+--------------------------+-------------------------+-------------------------+





**Example: Enable service action JSON request**


.. code::

   POST /v1.0/110011/admin/services/action HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "project_id": "12345",
       "action": "enable"
   }





**Example: Disable service action JSON request**


.. code::

   POST /v1.0/110011/admin/services/action HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "domain": "www.blog.example.com",
       "action": "disable"
   }





Response
""""""""""""""""










**Example: Post service action HTTP response**


.. code::

   HTP/1.1 202 (Accepted)




