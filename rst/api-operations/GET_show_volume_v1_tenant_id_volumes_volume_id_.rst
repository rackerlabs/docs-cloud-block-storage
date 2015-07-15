=============================================================================
Show Volume -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Show Volume
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_show_volume_v1_tenant_id_volumes_volume_id_.rst#request>`__
`Response <GET_show_volume_v1_tenant_id_volumes_volume_id_.rst#response>`__

.. code-block:: javascript

    GET /v1/{tenant_id}/volumes/{volume_id}

Shows volume details.



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
|{volume_id}               |*(Required)*             |The unique identifier of |
|                          |                         |an existing volume.      |
+--------------------------+-------------------------+-------------------------+








Response
^^^^^^^^^^^^^^^^^^





**Example Show Volume: XML request**


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


**Example Show Volume: JSON request**


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

