
.. _put-update-snapshot-v2:

Update snapshot
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PUT /v2/{tenant_id}/snapshots/{snapshot_id}

This operation updates a specified snapshot.



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



This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**snapshot**              |Dict *(Required)*        |A snapshot object.       |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |String *(Optional)*      |The name of the snapshot.|
|**name**                  |                         |Default is ``None``.     |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |String *(Optional)*      |A description of the     |
|**description**           |                         |snapshot. Default is     |
|                          |                         |``None``.                |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **new_size**   |Integer *(Optional)*     |The size for the volume, |
|                          |                         |in gibibyte (GiB).       |
+--------------------------+-------------------------+-------------------------+




   



**Example Update snapshot: JSON request**


.. code::

   {
       "snapshot":{
           "name":"snap-002”,
           "description":"This is yet, another snapshot."
       }
   }





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






**Example Update snapshot: JSON response**


.. code::

   {
       "snapshot":{
           "created_at":"2013-02-20T08:11:34.000000",
           "description":"This is yet, another snapshot",
           "name”:”snap-002“,
           "id":"4b502fcb-1f26-45f8-9fe5-3b9a0a52eaf2",
           "size":1,
           "status":"available",
           "volume_id":"2402b902-0b7a-458c-9c07-7435a826f794"
       }
   }




