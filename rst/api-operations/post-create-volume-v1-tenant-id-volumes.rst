
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Create Volume -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Create Volume
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <post-create-volume-v1-tenant-id-volumes.html#request>`__
`Response <post-create-volume-v1-tenant-id-volumes.html#response>`__

.. code::

    POST /v1/{tenant_id}/volumes

Creates a volume.

Following are several considerations when using this operation: 

* When you use ``source_volid`` for volume cloning, note that this feature currently has the following constraints. You cannot create more than one clone per volume concurrently. Snapshots and volume cloning use the same locking mechanism, so you cannot run a snapshot and a clone of the same volume concurrently.
* Note that you use the ``os-volume_attachments`` API call (/servers/{server_id}/os-volume_attachments) to attach the new volume to your Next Generation Cloud Server (with the specified {server_id}). Refer to the `Next Generation Cloud Servers Developer Guide <http://docs.rackspace.com/servers/api/v2/cs-devguide/content/Volume_Attachment_Actions.html>`__ for details of the call. Once the volume is attached, the new volume appears as another device on the Next Generation Cloud Server. It can then be partitioned, formatted, and mounted for use on the system.
* To create a bootable volume, include the ``imageRef`` parameter in the request. The corresponding response parameter is ``image_id``. For more information about this feature, see the Knowledge Center article `Boot a server from a Cloud Block Storage volume <http://www.rackspace.com/knowledge_center/article/boot-a-server-from-a-cloud-block-storage-volume>`__.




The examples in this section create a 100 gibibytes (GiB) SATA volume called vol-001.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |                         |                         |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |xsd:string               |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|volume                    |string *(Required)*      |A partial representation |
|                          |                         |of a volume used in the  |
|                          |                         |creation process. This   |
|                          |                         |parameter is required    |
|                          |                         |for this operation.      |
+--------------------------+-------------------------+-------------------------+
|size                      |int *(Required)*         |The size of the volume,  |
|                          |                         |in gibibytes (GiB). This |
|                          |                         |is a required parameter. |
|                          |                         |Note: When creating a    |
|                          |                         |volume from a snapshot,  |
|                          |                         |the volume size must be  |
|                          |                         |greater than the         |
|                          |                         |snapshot size.           |
+--------------------------+-------------------------+-------------------------+
|display_description       |string *(Required)*      |A description of the     |
|                          |                         |volume. This parameter   |
|                          |                         |is optional.             |
+--------------------------+-------------------------+-------------------------+
|display_name              |string *(Required)*      |The name of the volume.  |
|                          |                         |This parameter is        |
|                          |                         |optional.                |
+--------------------------+-------------------------+-------------------------+
|snapshot_id               |uuid *(Required)*        |The snapshot from which  |
|                          |                         |to create a volume. This |
|                          |                         |parameter is optional.   |
+--------------------------+-------------------------+-------------------------+
|volume_type               |string *(Required)*      |The type of volume to    |
|                          |                         |create, either SATA or   |
|                          |                         |SSD. This parameter is   |
|                          |                         |optional. If not         |
|                          |                         |defined, the default,    |
|                          |                         |SATA, is used.           |
+--------------------------+-------------------------+-------------------------+
|source_volid              |uuid *(Required)*        |The source identifier of |
|                          |                         |an existing Cloud Block  |
|                          |                         |Storage volume that you  |
|                          |                         |want to clone (copy) to  |
|                          |                         |create a new volume.     |
|                          |                         |This parameter is        |
|                          |                         |optional.                |
+--------------------------+-------------------------+-------------------------+
|availability_zone         |string *(Required)*      |This parameter is no     |
|                          |                         |longer used. Therefore,  |
|                          |                         |you can supply any value |
|                          |                         |for                      |
|                          |                         |``availability_zone``.   |
|                          |                         |If you specify no value, |
|                          |                         |the default is ``nova``. |
+--------------------------+-------------------------+-------------------------+
|metadata                  |string *(Required)*      |This optional parameter  |
|                          |                         |is available if you want |
|                          |                         |to set any metadata      |
|                          |                         |values on the volume.    |
+--------------------------+-------------------------+-------------------------+
|imageRef                  |uuid *(Required)*        |Specifying this          |
|                          |                         |parameter is required to |
|                          |                         |create a bootable        |
|                          |                         |volume. This parameter   |
|                          |                         |is the ID of the image   |
|                          |                         |from which you want to   |
|                          |                         |create the volume.       |
+--------------------------+-------------------------+-------------------------+





**Example Create Volume: XML request**


.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <volume xmlns="http://docs.rackspace.com/volume/api/v1"
            display_name="vol-001"
            display_description="Another volume."
            size="100"
            source_volid="e3611474-589b-46b7-9bdf-5555e2e4999b"        
            volume_type="SATA">
    
    </volume>
    


**Example Create Volume: JSON request**


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
^^^^^^^^^^^^^^^^^^





**Example Create Volume: XML response**


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


**Example Create Volume: JSON response**


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

