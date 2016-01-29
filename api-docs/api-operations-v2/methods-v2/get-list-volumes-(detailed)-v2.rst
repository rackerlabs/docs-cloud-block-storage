
.. _get-list-volumes-detail-v2:

List volumes (detailed)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/volumes/detail

This operation lists detailed information for all Cloud Block Storage volumes that the tenant who submits the request can access.



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
|**volumes**               |Dict                     |A list of volume objects.|
+--------------------------+-------------------------+-------------------------+
|volumes.\ **status**      |String                   |The volume status.       |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |String                   |The volume migration     |
|**migration_status**      |                         |status.                  |                   
+--------------------------+-------------------------+-------------------------+
|volumes.\ **user_id**     |UUID                     |The UUID of the user.    |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |List                     |Instance attachment      |
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
|volumes.\ **links**       |Dict                     |The volume links.        |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |String                   |The availability_zone.   |
|**availability_zone**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |Boolean                  |Indicates if the volume  |
|**bootable**              |                         |is bootable. You can boot|
|                          |                         |an instance from a       |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |Boolean                  |Indicates if the volume  |
|**encrypted**             |                         |is encrypted.            |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |DateTime                 |The date and time when   |
|**created_at**            |                         |volume was created. The  |
|                          |                         |format is ISO8601:       |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm.The +/- value, if  |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |String                   |The volume description.  |
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+ 
|volumes.\                 |DateTime                 |The date and time when   |
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
|volumes.\                 |String                   |The type of volume to    |
|**volume_type**           |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |String                   |The volume name.         |
|**name**                  |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |String                   |The volume replication   |
|**replication_status**    |                         |status.                  |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |UUID                     |The UUID of the          |
|**consistencygroup_id**   |                         |consistency group.       |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |UUID                     |The UUID of the source   |
|**source_volid**          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |UUID                     |The UUID of the source   |
|**snapshot_id**           |                         |volume snapshot. The API |
|                          |                         |creates a new volume     |
|                          |                         |snapshot with the same   |
|                          |                         |size as the source volume|
|                          |                         |snapshot.                |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |Boolean                  |If ``true``, this volume |
|**multiattach**           |                         |can attach to more than  |
|                          |                         |server instance.         |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volumes.\                 |UUID                     |The UUID of the volume.  |
|**id**                    |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volumes.\ **size**        |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+
|volumes.\ **links**       |Dict                     |The volume links.        |
+--------------------------+-------------------------+-------------------------+





**Example List volumes (detailed): JSON response**


.. code::

   {
       "volumes": [
           {
              "migration_status": null,
               "attachments": [
                   {
                       "server_id": "f4fda93b-06e0-4743-8117-bc8bcecd651b",
                       "attachment_id": "3b4db356-253d-4fab-bfa0-e3626c0b8405",
                       "host_name": null,
                       "volume_id": "6edbc2f4-1507-44f8-ac0d-eed1d2608d38",
                       "device": "/dev/vdb",
                       "id": "6edbc2f4-1507-44f8-ac0d-eed1d2608d38"
                   }
               ],
               "links": [
                   {
                       "href": "http://23.253.248.171:8776/v2/bab7d5c60cd041a0a36f7c4b6e1dd978/volumes/6edbc2f4-1507-44f8-ac0d-eed1d2608d38",
                       "rel": "self"
                   },
                   {
                       "href": "http://23.253.248.171:8776/bab7d5c60cd041a0a36f7c4b6e1dd978/volumes/6edbc2f4-1507-44f8-ac0d-eed1d2608d38",
                       "rel": "bookmark"
                   }
               ],
               "availability_zone": "nova",
               "os-vol-host-attr:host": "difleming@lvmdriver-1#lvmdriver-1",
               "encrypted": false,
               "os-volume-replication:extended_status": null,
               "replication_status": "disabled",
               "snapshot_id": null,
               "id": "6edbc2f4-1507-44f8-ac0d-eed1d2608d38",
               "size": 2,
               "user_id": "32779452fcd34ae1a53a797ac8a1e064",
               "os-vol-tenant-attr:tenant_id": "bab7d5c60cd041a0a36f7c4b6e1dd978",
               "os-vol-mig-status-attr:migstat": null,
               "metadata": {
                   "readonly": "False",
                   "attached_mode": "rw"
               },
               "status": "in-use",
               "description": null,
               "multiattach": true,
               "os-volume-replication:driver_data": null,
               "source_volid": null,
               "consistencygroup_id": null,
               "os-vol-mig-status-attr:name_id": null,
               "name": "test-volume-attachments",
               "bootable": "false",
               "created_at": "2015-11-29T03:01:44.000000",
               "volume_type": "lvmdriver-1"
           },
           {
               "migration_status": null,
               "attachments": [],
               "links": [
                   {
                       "href": "http://23.253.248.171:8776/v2/bab7d5c60cd041a0a36f7c4b6e1dd978/volumes/173f7b48-c4c1-4e70-9acc-086b39073506",
                       "rel": "self"
                   },
                   {
                       "href": "http://23.253.248.171:8776/bab7d5c60cd041a0a36f7c4b6e1dd978/volumes/173f7b48-c4c1-4e70-9acc-086b39073506",
                       "rel": "bookmark"
                   }
               ],
               "availability_zone": "nova",
               "os-vol-host-attr:host": "difleming@lvmdriver-1#lvmdriver-1",
               "encrypted": false,
               "os-volume-replication:extended_status": null,
               "replication_status": "disabled",
               "snapshot_id": null,
               "id": "173f7b48-c4c1-4e70-9acc-086b39073506",
               "size": 1,
               "user_id": "32779452fcd34ae1a53a797ac8a1e064",
               "os-vol-tenant-attr:tenant_id": "bab7d5c60cd041a0a36f7c4b6e1dd978",
               "os-vol-mig-status-attr:migstat": null,
               "metadata": {},
               "status": "available",
               "volume_image_metadata": {
                   "kernel_id": "8a55f5f1-78f7-4477-8168-977d8519342c",
                   "checksum": "eb9139e4942121f22bbc2afc0400b2a4",
                   "min_ram": "0",
                   "ramdisk_id": "5f6bdf8a-92db-4988-865b-60bdd808d9ef",
                   "disk_format": "ami",
                   "image_name": "cirros-0.3.4-x86_64-uec",
                   "image_id": "b48c53e1-9a96-4a5a-a630-2e74ec54ddcc",
                   "container_format": "ami",
                   "min_disk": "0",
                   "size": "25165824"
               },
               "description": "",
               "multiattach": false,
               "os-volume-replication:driver_data": null,
               "source_volid": null,
               "consistencygroup_id": null,
               "os-vol-mig-status-attr:name_id": null,
               "name": "test-volume",
               "bootable": "true",
               "created_at": "2015-11-29T02:25:18.000000",
               "volume_type": "lvmdriver-1"
           }
       ]
   }



