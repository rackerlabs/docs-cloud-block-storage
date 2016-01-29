
.. _get-show-volume-v2:

Show volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/volumes/{volume_id}

This operation shows details for a volume.

**Preconditions:**

-  This volume must exist.



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
|{volume_id}               |UUID *(Required)*        |The UUID of              |
|                          |                         |an existing volume.      |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volume**                |Dict                     |A volume object.         |
+--------------------------+-------------------------+-------------------------+
|volume.\ **status**       |String                   |The volume status.       |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String                   |The volume migration     |
|**migration_status**      |                         |status.                  |                   
+--------------------------+-------------------------+-------------------------+
|volume.\ **user_id**      |UUID                     |The UUID of the user.    |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |List                     |Instance attachment      |
|**attachments**           |                         |information.             |
|                          |                         |If this volume is        |
|                          |                         |attached to a server     |
|                          |                         |instance, the            |
|                          |                         |attachments list includes|
|                          |                         |the UUID of the attached |
|                          |                         |server, an attachment    |
|                          |                         |UUID, the name of the    |
|                          |                         |attached host, if any,   |
|                          |                         |the volume UUID, the     |
|                          |                         |device, and the device   |
|                          |                         |UUID. Otherwise, this    |
|                          |                         |list is empty.           |                   
+--------------------------+-------------------------+-------------------------+
|volume.\ **links**        |Dict                     |The volume links.        |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String                   |The availability_zone.   |
|**availability_zone**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Boolean                  |Indicates if the volume  |
|**bootable**              |                         |is bootable. You can boot|
|                          |                         |an instance from a       |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Boolean                  |Indicates if the volume  |
|**encrypted**             |                         |is encrypted.            |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |DateTime                 |The date and time when   |
|**created_at**            |                         |volume was created. The  |
|                          |                         |format is ISO8601:       |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm.The +/- value, if  |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String                   |The volume description.  |
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+ 
|volume.\                  |DateTime                 |The date and time when   |
|**updated_at**            |                         |volume was updated. The  |
|                          |                         |format is ISO8601:       |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm.The +/- value, if  |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC. If the value is not |
|                          |                         |set, the value is        |
|                          |                         |``null``.                |
+--------------------------+-------------------------+-------------------------+ 
|volume.\                  |String                   |The type of volume to    |
|**volume_type**           |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String                   |The volume name.         |
|**name**                  |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String                   |The volume replication   |
|**replication_status**    |                         |status.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID                     |The UUID of the          |
|**consistencygroup_id**   |                         |consistency group.       |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID                     |The UUID of the source   |
|**source_volid**          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID                     |The UUID of the source   |
|**snapshot_id**           |                         |volume snapshot. The API |
|                          |                         |creates a new volume     |
|                          |                         |snapshot with the same   |
|                          |                         |size as the source volume|
|                          |                         |snapshot.                |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Boolean                  |If ``true``, this volume |
|**multiattach**           |                         |can attach to more than  |
|                          |                         |server instance.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID                     |The UUID of the volume.  |
|**id**                    |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\ **size**         |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+











**Example Show volume: JSON response**


.. code::

   {
       "volume": {
           "status": "available",
           "attachments": [],
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
           "availability_zone": "nova",
           "bootable": "false",
           "os-vol-host-attr:host": "ip-10-168-107-25",
           "source_volid": null,
           "snapshot_id": null,
           "id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
           "description": "Super volume.",
           "name": "vol-002",
           "created_at": "2013-02-25T02:40:21.000000",
           "volume_type": "None",
           "os-vol-tenant-attr:tenant_id": "0c2eba2c5af04d3f9e9d0d410b371fde",
           "size": 1,
           "os-volume-replication:driver_data": null,
           "os-volume-replication:extended_status": null,
           "metadata": {
               "contents": "not junk"
           }
       }
   }




