
.. _get-show-snapshot-details-v2:

Show snapshot details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/snapshots/{snapshot_id}

This operation shows snapshot details.

.. note::
   The ``os-extended-snapshot-attributes:progress`` field in the response body shows snapshot progress. See the example response.
   
   



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










**Example Show snapshot details: JSON response**


.. code::

   {
       "snapshot": {
           "status": "available",
           "os-extended-snapshot-attributes:progress": "100%",
           "description": "Daily backup",
           "created_at": "2013-02-25T04:13:17.000000",
           "metadata": {},
           "volume_id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
           "os-extended-snapshot-attributes:project_id": "0c2eba2c5af04d3f9e9d0d410b371fde",
           "size": 1,
           "id": "2bb856e1-b3d8-4432-a858-09e4ce939389",
           "name": "snap-001"
       }
   }
   




