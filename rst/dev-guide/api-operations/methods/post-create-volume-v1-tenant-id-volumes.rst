
.. _post-create-volume:

Create volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v1/{tenant_id}/volumes

This operation creates a volume.

Following are several options for consideration when using this operation: 

- **source_volid for volume cloning**: When you use ``source_volid`` for volume cloning, note that this feature currently has the 
  following constraints. Concurrent clone requests are queued for processing. When one clone 
  request completes, the next clone request in the queue starts.


- **os-volume_attachments**: Note that you use the ``os-volume_attachments`` API call (/servers/{server_id}/os-volume_attachments) 
  to attach the new volume to your Next Generation Cloud Server (with the specified {server_id}). 
  Refer to the `Next Generation Cloud Servers Developer Guide`_ for details of the call. 
  Once the volume is attached, the new volume appears as another device on the Next Generation 
  Cloud Server. Once the volume is attached, the new volume appears as another device on the 
  Next Generation Cloud Server. It can then be partitioned, formatted, and mounted for use on 
  the system.


- **Boot from volume**: To create a bootable volume, include the ``imageRef`` parameter in the request. The 
  corresponding response parameter is ``image_id``. For more information about this feature, 
  see :kc-article:`Boot a server from a Cloud Block Storage volume<boot-a-server-from-a-cloud-block-storage-volume>`.


- **Disaffinity for volume creation**: To create volumes on a different node or rack than existing volumes, use the ``metadata`` 
  parameter in the body of the request, and specify ``different_node`` or ``different_rack`` 
  with a comma-separated list of volume IDs from which you want the volume that you are 
  creating to be distinct. For example, specifying the following parameters in the request 
  body creates a volume on a rack that is different from th e threes specified volume IDs: 

      ``“metadata”: “different_rack=45c2c5c4-2666-43e9-aa6b-e58eb733410b,8d472323-196d-47bf-8f17-a21b978d0f90,f158d108-aa30-4609-9d31-c2b230f8a871”``  

  Note that if the criteria specified using ``metadata`` cannot be met, the volume will be in an error state.








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
|{tenant_id}               |String *(Required)*      |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volume**                |String *(Required)*      |A partial representation |
|                          |                         |of a volume used in the  |
|                          |                         |creation process. This   |
|                          |                         |parameter is required    |
|                          |                         |for this operation.      |
+--------------------------+-------------------------+-------------------------+
|volume.\ **size**         |Int *(Required)*         |The size of the volume,  |
|                          |                         |in gibibytes (GiB). This |
|                          |                         |is a required parameter. |
|                          |                         |Note: When creating a    |
|                          |                         |volume from a snapshot,  |
|                          |                         |the volume size must be  |
|                          |                         |greater than the         |
|                          |                         |snapshot size.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |A description of the     |
|**display_description**   |                         |volume. This parameter   |
|                          |                         |is optional.             |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The name of the volume.  |
|**display_name**          |                         |This parameter is        |
|                          |                         |optional.                |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Uuid *(Optional)*        |The snapshot from which  |
|**snapshot_id**           |                         |to create a volume. This |
|                          |                         |parameter is optional.   |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The type of volume to    |
|**volume_type**           |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Uuid *(Optional)*        |The source identifier of |
|**source_volid**          |                         |an existing Cloud Block  |
|                          |                         |Storage volume that you  |
|                          |                         |want to clone (copy) to  |
|                          |                         |create a new volume.     |
|                          |                         |This parameter is        |
|                          |                         |optional.                |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |This parameter is no     |
|**availability_zone**     |                         |longer used. Therefore,  |
|                          |                         |you can supply any value |
|                          |                         |for                      |
|                          |                         |``availability_zone``.   |
|                          |                         |If you specify no value, |
|                          |                         |the default is ``nova``. |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |This optional parameter  |
|**metadata**              |                         |is available if you want |
|                          |                         |to set any metadata      |
|                          |                         |values on the volume.    |
|                          |                         |                         |
|                          |                         |Use ``different_node`` or|
|                          |                         |``different_rack`` with a|
|                          |                         |comma-separated list of  |
|                          |                         |volume IDs from which you|
|                          |                         |want the volume that you |
|                          |                         |are creating to be       |
|                          |                         |distinct. Using these    |
|                          |                         |keywords will create the |
|                          |                         |volume on a node or rack |
|                          |                         |that is different from   |
|                          |                         |those whose volume IDs   |
|                          |                         |are specified.           |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |Uuid *(Optional)*        |Specifying this          |
|**imageRef**              |                         |parameter is required to |
|                          |                         |create a bootable        |
|                          |                         |volume. This parameter   |
|                          |                         |is the ID of the image   |
|                          |                         |from which you want to   |
|                          |                         |create the volume.       |
+--------------------------+-------------------------+-------------------------+





**Example Create volume: XML request**

The example creates a 100 gibibytes (GiB) SATA volume called vol-001.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <volume xmlns="http://docs.rackspace.com/volume/api/v1"
           display_name="vol-001"
           display_description="Another volume."
           size="100"
           source_volid="e3611474-589b-46b7-9bdf-5555e2e4999b"        
           volume_type="SATA">
   
   </volume>
   



**Example Create volume: JSON request**


.. code::

   {
       "volume": {
           "display_name": "vol-001",
           "display_description": "Another volume.",
           "size": 100,
           "source_volid": "e3611474-589b-46b7-9bdf-5555e2e4999b",
           "volume_type": "SATA"
        }
   }
   





Response
""""""""""""""""


**Example Create volume: XML response**


.. code::

   <?xml version='1.0' encoding='UTF-8'?>
   <volume xmlns="http://docs.rackspace.com/volume/api/v1"
           status="available"
           display_name="vol-001"
           attachments=""
           availability_zone="nova"
           bootable="false"
           created_at="2012-02-14T20:53:07Z"
           display_description="Another volume."
           image_id="null"
           volume_type="SATA"
           snapshot_id="null"
           source_volid="e3611474-589b-46b7-9bdf-5555e2e4999b"
           metadata=""
           id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
           size="100"/>



**Example Create volume: JSON response**


.. code::

   {
     "volume": {
       "status": "available",
       "display_name": "vol-001",
       "attachments": [],
       "availability_zone": "nova",
       "bootable": "false",
       "created_at": "2012-02-14T20:53:07Z",
       "display_description": "Another volume.",
       "image_id": null,
       "volume_type": "SATA",
       "snapshot_id": null,
       "source_volid": "e3611474-589b-46b7-9bdf-5555e2e4999b",
       "metadata": {},
       "id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
       "size": 100
     }
   }



.. _Next Generation Cloud Servers Developer Guide: https://developer.rackspace.com/docs/cloud-servers/v2/developer-guide/#put-attach-volume-to-server-servers-server-id-os-volume-attachments