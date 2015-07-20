
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
List Volumes -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

List Volumes
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <get-list-volumes-v1-tenant-id-volumes.html#request>`__
`Response <get-list-volumes-v1-tenant-id-volumes.html#response>`__

.. code::

    GET /v1/{tenant_id}/volumes

Lists summary information for all Block Storage volumes that the tenant who submits the request can access.



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








Response
^^^^^^^^^^^^^^^^^^





**Example List Volumes: XML response**


.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <volumes xmlns="http://docs.rackspace.com/volume/api/v1">
        <volume xmlns="http://docs.rackspace.com/volume/api/v1"
                id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
                display_name="vol-001"
                display_description="Another volume."
                status="active"
                size="100"
                volume_type="SATA"
                createdAt="2012-02-14T20:53:07Z">
        </volume>
        <volume xmlns="http://docs.rackspace.com/volume/api/v1"
                id="76b8950a-8594-4e5b-8dce-0dfa9c696358"
                display_name="vol-002"
                display_description="Yet another volume."
                status="active"
                size="100"
                volume_type="SATA"
                createdAt="2012-03-15T19:10:03Z" />
    </volumes>
    


**Example List Volumes: JSON response**


.. code::

    {
        "volumes": [
            {
                "id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
                "display_name": "vol-001",
                "display_description": "Another volume.",
                "size": 100,
                "volume_type": "SATA",
                "snapshot_id": null,
                "attachments": [],
                "createdAt": "2012-02-14T20:53:07Z"
            },
            {
                "id": "76b8950a-8594-4e5b-8dce-0dfa9c696358",
                "display_name": "vol-002",
                "display_description": "Yet another volume.",
                "size": 100,
                "volume_type": "SATA",
                "snapshot_id": null,
                "attachments": [],
                "createdAt": "2012-03-15T19:10:03Z"
            }
        ]
    }
    

