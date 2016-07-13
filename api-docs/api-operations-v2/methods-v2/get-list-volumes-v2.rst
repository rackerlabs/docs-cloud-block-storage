
.. _get-list-volumes-v2:

List volumes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/volumes

This operation lists summary information for all Cloud Block Storage volumes that the tenant who submits the request can access.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success                  |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |UUID   *(Required)*      |The UUID of the tenant in|
|                          |                         |a multi-tenancy cloud.   |
+--------------------------+-------------------------+-------------------------+

This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|sort                      |String *(Optional)*      |Comma-separated list of  |
|                          |                         |sort keys and optional   |
|                          |                         |sort directions in the   |
|                          |                         |form of <key>[:<direction|
|                          |                         |>]. A valid direction is |
|                          |                         |``asc`` (ascending) or   |
|                          |                         |``desc`` (descending).   |
+--------------------------+-------------------------+-------------------------+
|limit                     |Integer *(Optional)*     |Requests a page size of  |
|                          |                         |items. Returns a number  |
|                          |                         |of items up to a limit   |
|                          |                         |value. Use the ``limit`` |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
+--------------------------+-------------------------+-------------------------+
|marker                    |String *(Optional)*      |The ID of the last-seen  |
|                          |                         |item. Use the ``limit``  |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
+--------------------------+-------------------------+-------------------------+


This operation does not accept a request body.




Response
""""""""""""""""




This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volumes**               |List                     |A list of volume objects.|
+--------------------------+-------------------------+-------------------------+
|volumes.\ **name**        |String                   |The volume name.         |
+--------------------------+-------------------------+-------------------------+
|volumes.\ **id**          |UUID                     |The UUID of the volume.  |             
+--------------------------+-------------------------+-------------------------+
|volumes.\ **links**       |Dict                     |The volume links.        |
+--------------------------+-------------------------+-------------------------+






**Example List volumes: JSON response**


.. code::

   {
        "volumes": [
            {
               "id": "45baf976-c20a-4894-a7c3-c94b7376bf55",
               "links": [
                   {
                       "href": "http://localhost:8776/v2/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/45baf976-c20a-4894-a7c3-c94b7376bf55",
                       "rel": "self"
                   },
                   {
                       "href": "http://localhost:8776/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/45baf976-c20a-4894-a7c3-c94b7376bf55",
                       "rel": "bookmark"
                   }
               ],
               "name": "vol-004"
           },
           {
               "id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
               "links": [
                   {
                       "href": "http://localhost:8776/v2/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/5aa119a8-d25b-45a7-8d1b-88e127885635",
                       "rel": "self"
                   },
                   {
                    "href": "http://localhost:8776/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/5aa119a8-d25b-45a7-8d1b-88e127885635",
                       "rel": "bookmark"
                   }
               ],
               "name": "vol-003"
          }
    ]   




