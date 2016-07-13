
.. _post-create-volume-v2:

Create volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v2/{tenant_id}/volumes

This operation creates a volume.

To create a bootable volume, include the UUID of the image from which you want to 
create the volume in the ``imageRef`` attribute in the request body.

**Preconditions**

-   You must have enough volume storage quota remaining to create a volume of size requested.

**Asynchronous postconditions**

-   With correct permissions, you can see the volume status as ``available`` through API calls.

-   With correct access, you can see the created volume in the storage system that Cloud Block Storage manages.

**Troubleshooting**

-   If volume status remains ``creating`` or shows another error status, the request failed. Ensure you meet 
    the preconditions, and then investigate the storage back end.








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
|                          |                         |a                        |
|                          |                         |multi-tenancy cloud.     |
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
|volume.\                  |String *(Optional)*      |The volume description.  |
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The volume name.         |
|**name**                  |                         |                         |
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
|volume.\                  |String *(Optional)*      |The type of volume to    |
|**volume_type**           |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID *(Optional)*        |The UUID of the source   |
|**source_volid**          |                         |volume. The API creates  |
|                          |                         |a new volume with the    |
|                          |                         |same size as the source  |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The availability_zone.   |
|**availability_zone**     |                         |                         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Boolean *(Optional)*     |To enable a volume to    |
|**multiattach**           |                         |attach to more than one  |
|                          |                         |server, set the value to |
|                          |                         |``true``. The default is |
|                          |                         |``false``.               |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID    *(Optional)*     |The UUID of the primary  |
|**source_replica**        |                         |volume to clone.         |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID    *(Optional)*     |The UUID of the          |
|**consistencygroup_id**   |                         |consistency group.       |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Dict   *(Optional)*      |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |UUID *(Optional)*        |The UUID of the image    |
|**imageRef**              |                         |from which you want to   |
|                          |                         |create a volume.         |
|                          |                         |Required to create a     |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+







**Example Create volume: JSON request**


.. code::

   {
        "volume": {
            "size": 10,
            "availability_zone": null,
            "source_volid": null,
            "description": null,
            "multiattach ": false,
            "snapshot_id": null,
            "name": null,
            "imageRef": null,
            "volume_type": null,
            "metadata": {},
            "source_replica": null,
            "consistencygroup_id": null
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


**Example Create volume: JSON response**


.. code::

    {
        "volume": {
            "status": "creating",
            "migration_status": null,
            "user_id": "0eea4eabcf184061a3b6db1e0daaf010",
            "attachments": [],
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
            "bootable": "false",
            "encrypted": false,
            "created_at": "2015-11-29T03:01:44.000000",
            "description": null,
            "updated_at": null,
            "volume_type": "lvmdriver-1",
            "name": "test-volume-attachments",
            "replication_status": "disabled",
            "consistencygroup_id": null,
            "source_volid": null,
            "snapshot_id": null,
            "multiattach": false,
            "metadata": {},
            "id": "6edbc2f4-1507-44f8-ac0d-eed1d2608d38",
            "size": 2
        }
    }


.. _Next Generation Cloud Servers Developer Guide: https://developer.rackspace.com/docs/cloud-servers/v2/developer-guide/#put-attach-volume-to-server-servers-server-id-os-volume-attachments