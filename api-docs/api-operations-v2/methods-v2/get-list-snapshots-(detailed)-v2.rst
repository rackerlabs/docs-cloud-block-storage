
.. _get-list-snapshots-detail-v2:

List snapshots (detailed)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/snapshots/detail

This operation lists detailed information for all Cloud Block Storage snapshots that the tenant who submits the request can access.



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






This operation does not accept a request body.




Response
""""""""""""""""




This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**snapshots**             |Dict                     |A snapshots object.      |
+--------------------------+-------------------------+-------------------------+
|snapshots.\ **status**    |String                   |The snapshot status.     |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |String                   |The snapshot description.|
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+ 
|snapshots.\               |DateTime                 |The date and time when   |
|**created_at**            |                         |the snapshot was created.|
|                          |                         |The format is ISO8601.   |
|                          |                         |For example,             |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm. The +/- value, if |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |snapshot, if any.        |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |UUID                     |The UUID of the volume   |
|**volume_id**             |                         |if the snapshot was      |
|                          |                         |created from a volume.   |
+--------------------------+-------------------------+-------------------------+
|snapshots.\ **size**      |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+
|snapshots.\ **id**        |UUID                     |The snapshot UUID.       |
+--------------------------+-------------------------+-------------------------+
|snapshots.\ **name**      |String                   |The snapshot name.       |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |Integer                  |A percentage value for   |
|**os-extended-snapshot-   |                         |the build progress.      |
|attributes:progress**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|snapshots.\               |UUID                     |The UUID of the owning   |
|**os-extended-snapshot-   |                         |project.                 |
|attributes:project_id**   |                         |                         |
+--------------------------+-------------------------+-------------------------+




   





**Example List snapshots (detailed): JSON response**


.. code::

   
   {
       "snapshots": [
           {
               "status": "available",
               "metadata": {
                   "name": "test"
               },
               "os-extended-snapshot-attributes:progress": "100%",
               "name": "test-volume-snapshot",
               "volume_id": "173f7b48-c4c1-4e70-9acc-086b39073506",
               "os-extended-snapshot-attributes:project_id": "bab7d5c60cd041a0a36f7c4b6e1dd978",
               "created_at": "2015-11-29T02:25:51.000000",
               "size": 1,
               "id": "b1323cda-8e4b-41c1-afc5-2fc791809c8c",
               "description": "volume snapshot"
           }
       ]
   }



