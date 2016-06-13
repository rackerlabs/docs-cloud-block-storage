.. _post-accept-volume-transfer:

Accept a volume transfer
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v1/{tenant_id}/os-volume-transfer/​{transfer_id}​/accept

This operation accepts a volume transfer.




This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+



Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |String                   |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+
|{transfer_id}             |String                   |The unique identifier of |
|                          |                         |a volume transfer.       |
+--------------------------+-------------------------+-------------------------+




This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**accept**                |String *(Required)*      |A partial representation |
|                          |                         |of a volume transfer     |
|                          |                         |acceptance.              |
+--------------------------+-------------------------+-------------------------+
|accept.\ **auth_key**     |String *(Required)*      |The authentication key   |
|                          |                         |for the volume transfer. |
+--------------------------+-------------------------+-------------------------+



**Example: Accept a volume transfer JSON request**


.. code::

   {
       "accept": {
           "auth_key": "9266c59563c84664"
       }
   }   





Response
""""""""""""""""

This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**transfer**              |String                   |A representation         |
|                          |                         |of a volume transfer in  |
|                          |                         |the creation process.    |
+--------------------------+-------------------------+-------------------------+
|transfer.\ **id**         |UUID                     |The UUID of the volume   |
|                          |                         |transfer.                |
+--------------------------+-------------------------+-------------------------+
|transfer.\ **name**       |String                   |The volume transfer name.|
+--------------------------+-------------------------+-------------------------+
|transfer.\ **volume_id**  |UUID                     |The UUID of the volume.  |
+--------------------------+-------------------------+-------------------------+
|transfer.\ **links**      |List                     |The links for the volume |
|                          |                         |transfer.                |
+--------------------------+-------------------------+-------------------------+


**Example: Accept a volume transfer JSON response**


.. code::

   {
       "transfer": {
           "id": "cac5c677-73a9-4288-bb9c-b2ebfb547377",
           "name": "first volume transfer",
           "volume_id": "894623a6-e901-4312-aa06-4275e6321cce",
           "links": [
               {
                   "href": "http://localhost/v2/firstproject/volumes/1",
                   "rel": "self"
               },
               {
                   "href": "http://localhost/firstproject/volumes/1",
                   "rel": "bookmark"
               }
           ]
       }
   }


