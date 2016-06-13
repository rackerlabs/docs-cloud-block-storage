.. _post-set-status-service:

Set the status of a service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /admin/services/status


To change the status of a service for a given ``service_id`` and ``project_id``, provide a JSON request body with ``project_id`` set to the project ID of the service, ``serice_id`` set to the corresponding ``service_id``, and ``status`` set to ``deployed`` or ``failed``. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |Created                  |Following a POST         |
|                          |                         |command, this status     |
|                          |                         |indicates success. The   |
|                          |                         |request has been         |
|                          |                         |fulfilled.               |
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
|\ **service_id**          |String *(Required)*      |Specifies the ID for the |
|                          |                         |service.                 |
+--------------------------+-------------------------+-------------------------+
|\ **status**              |String *(Required)*      |Specifies the status for |
|                          |                         |the service. Valid       |
|                          |                         |values are ``deployed``  |
|                          |                         |or ``failed``.           |
+--------------------------+-------------------------+-------------------------+





**Example: Post service deployed status JSON request**


.. code::

   POST /v1.0/110011/admin/services/status HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
     "project_id": "110011",
     "service_id": "e8b44506-71b7-4074-9bc8-1b5037ade112",
     "status": "deployed"
   }





**Example: Post service failed status JSON request**


.. code::

   POST /v1.0/110011/admin/services/status HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
     "project_id": "110011",
     "service_id": "e8b44506-71b7-4074-9bc8-1b5037ade112",
     "status": “failed”
   }





Response
""""""""""""""""




**Example: Set the status of a service HTTP response**


.. code::

   HTP/1.1 201 (Created)




