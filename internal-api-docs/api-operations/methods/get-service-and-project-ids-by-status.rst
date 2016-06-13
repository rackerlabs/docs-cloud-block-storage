.. _get-service-and-project-ids-by-status:

Get service IDs and project IDs by status 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/services


To get services and project IDs by ``status``, provide ``status`` as a query parameter in the endpoint URL of the operation. Valid values for ``status`` are ``deployed``, ``failed``, or ``update_in_progress``. No JSON request body is required. 



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
|                          |                         |services and project     |
|                          |                         |IDs. Valid values for    |
|                          |                         |``status`` are           |
|                          |                         |``deployed``,            |
|                          |                         |``failed``, or           |
|                          |                         |``update_in_progress``.  |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example: Get service IDs and project IDs by status HTTP request**


.. code::

   GET /v1.0/110011/admin/services?status=deployed HTTP/1.1
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
|\ **project_id**          |String                   |Specifies the project ID |
|                          |                         |for the service.         |
+--------------------------+-------------------------+-------------------------+
|\ **service_id**          |String                   |Specifies the service ID |
|                          |                         |for the service.         |
+--------------------------+-------------------------+-------------------------+







**Example: Get service IDs and project IDs by status JSON response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   {
       "project_id": "12345",
       "service_id": "e8b44506-71b7-4074-9bc8-1b5037ade112"
   }




