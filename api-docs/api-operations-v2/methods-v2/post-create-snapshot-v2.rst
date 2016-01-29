

.. _post-create-snapshot-v2:

Create snapshot
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v2/{tenant_id}/snapshots

This operation creates a snapshot.

A snapshot is a point-in-time, complete copy of the volume. You can create a volume from a snapshot.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request and that it  |
|                          |                         |has been accepted for    |
|                          |                         |processing, although it  |
|                          |                         |may not be processed     |
|                          |                         |immediately.             |
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
|snapshot.\ **volume_id**  |UUID *(Optional)*        |If the snapshot was      |
|                          |                         |created from a volume,   |
|                          |                         |the volume ID.           |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **force**      |Boolean *(Optional)*     |Indicates whether to     |
|                          |                         |snapshot, even if the    |
|                          |                         |volume is attached.      |
|                          |                         |Default is ``False``.    |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **new_size**   |Integer *(Optional)*     |The size for the volume, |
|                          |                         |in gibibyte (GiB).       |
+--------------------------+-------------------------+-------------------------+








**Example Create snapshot: JSON request**


.. code::

   {
        "snapshot": {
            "name": "snap-001",
            "description": "Daily backup",
            "volume_id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
            "force": true
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




   





**Example Create snapshot: JSON response**


.. code::

   {
       "snapshot": {
           "status": "creating",
           "description": "Daily backup",
           "created_at": "2013-02-25T03:56:53.081642",
           "metadata": {},
           "volume_id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
           "size": 1,
           "id": "ffa9bc5e-1172-4021-acaf-cdcd78a9584d",
           "name": "snap-001"
       }
   }
   




