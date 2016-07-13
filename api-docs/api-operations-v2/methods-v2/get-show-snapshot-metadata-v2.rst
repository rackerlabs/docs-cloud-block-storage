
.. _get-show-snapshot-metadata-v2:

Show snapshot metadata
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/snapshots/{snapshot_id}/metadata

This operation shows the metadata for the specified snapshot.



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
|{tenant_id}               |UUID *(Required)*        |The UUID of the tenant in|
|                          |                         |a multi-tenancy cloud.   |
+--------------------------+-------------------------+-------------------------+
|{snapshot_id}             |UUID *(Required)*        |The UUID of the snapshot.|
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""



This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**snapshot**              |Dict                     |A snapshot object.       |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **status**     |String                   |The snapshot status.     |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |String                   |The snapshot description.|
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+ 
|snapshot.\                |DateTime                 |The date and time when   |
|**created_at**            |                         |the snapshot was created.|
|                          |                         |The format is ISO8601.   |
|                          |                         |For example,             |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm. The +/- value, if |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |snapshot, if any.        |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |UUID                     |The UUID of the volume   |
|**volume_id**             |                         |if the snapshot was      |
|                          |                         |created from a volume.   |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **size**       |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **id**         |UUID                     |The snapshot UUID.       |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **name**       |String                   |The snapshot name.       |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |Integer                  |A percentage value for   |
|**os-extended-snapshot-   |                         |the build progress.      |
|attributes:progress**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |UUID                     |The UUID of the owning   |
|**os-extended-snapshot-   |                         |project.                 |
|attributes:project_id**   |                         |                         |
+--------------------------+-------------------------+-------------------------+






**Example Show snapshot metadata: JSON response**


.. code::

   
   
   {
       "snapshot": {
           "status": "available",
           "os-extended-snapshot-attributes:progress": "0%",
           "description": null,
           "created_at": "2014-05-06T17:59:52.000000",
           "metadata": {
               "key": "v1"
           },
           "volume_id": "ebd80b99-bc3d-4154-9d28-5583baa80580",
           "os-extended-snapshot-attributes:project_id": "7e0105e19cd2466193729ef78b604f79",
           "size": 10,
           "id": "dfcd17fe-3b64-44ba-b95f-1c9c7109ef95",
           "name": "my-snapshot"
       }
   }
   




