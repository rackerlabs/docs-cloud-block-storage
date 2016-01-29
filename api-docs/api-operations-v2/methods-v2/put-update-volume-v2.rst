
.. _put-update-volume-v2:

Update volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PUT /v2/{tenant_id}/volumes/{volume_id}

This operation updates a volume.



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
|{volume_id}               |UUID *(Required)*        |The UUID of the volume.  |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volume**                |Dict *(Required)*        |A volume object.         |
+--------------------------+-------------------------+-------------------------+
|volume.\ **size**         |Integer *(Required)*     |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The availability_zone.   |
|**availability_zone**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID *(Optional)*        |The UUID of the source   |
|**source_volid**          |                         |volume. The API creates  |
|                          |                         |a new volume with the    |
|                          |                         |same size as the source  |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The volume description.  |
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Boolean *(Optional)*     |To enable a volume to    |
|**multiattach**           |                         |attach to more than one  |
|                          |                         |server, set the value to |
|                          |                         |``true``. The default is |
|                          |                         |``false``.               |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID *(Optional)*        |To create a volume from  |
|**snapshot_id**           |                         |existing snapshot,       |
|                          |                         |specify the UUID of the  |
|                          |                         |volume snapshot. The     |
|                          |                         |volume is created in the |
|                          |                         |same availability zone   |
|                          |                         |and with the same size   |
|                          |                         |as the snapshot.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The volume name.         |
|**name**                  |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID *(Optional)*        |The UUID of the image    |
|**imageRef**              |                         |from which you want to   |
|                          |                         |create a volume.         |
|                          |                         |Required to create a     |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The type of volume to    |
|**volume_type**           |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Dict   *(Optional)*      |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID    *(Optional)*     |The UUID of the primary  |
|**source_replica**        |                         |volume to clone.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID    *(Optional)*     |The UUID of the          |
|**consistencygroup_id**   |                         |consistency group.       |
+--------------------------+-------------------------+-------------------------+





**Example Update volume: JSON request**


.. code::

   {
       "volume": {
           "name": "vol-003",
           "description": "This is yet, another volume."
       }
   }






Response
""""""""""""""""


This table shows the body parameters for the response:

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
|volume.\                  |DateTime                 |The date and time when   |
|**created_at**            |                         |volume was created. The  |
|                          |                         |format is ISO8601:       |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm.The +/- value, if  |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |volume.                  |
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
|volume.\                  |UUID                     |The UUID of the volume.  |
|**id**                    |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\ **size**         |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+





**Example Update volume: JSON response**


.. code::

   {
       "volume": {
           "status": "available",
           "migration_status": null,
           "user_id": "0eea4eabcf184061a3b6db1e0daaf010",
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
           "encrypted": false,
           "created_at": "2015-11-29T03:01:44.000000",
           "description": "This is yet, another volume.",
           "updated_at": null,
           "volume_type": "lvmdriver-1",
           "name": "vol-003",
           "replication_status": "disabled",
           "consistencygroup_id": null,
           "source_volid": null,
           "snapshot_id": null,
           "multiattach": false,
           "metadata": {
               "contents": "not junk"
           },
           "id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
           "size": 1
       }
   }



