
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List Snapshots (Detailed)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1/{tenant_id}/snapshots/detail

Lists detailed information for all Cloud Block Storage snapshots that the tenant who submits the request can access.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |                         |                         |
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





This operation does not accept a request body.




Response
""""""""""""""""





**Example List Snapshots (Detailed): XML response**


.. code::

    <?xml version='1.0' encoding='UTF-8'?>
    <snapshots
        xmlns="http://docs.rackspace.com/volume/api/v1">
        <snapshot status="available" description="Daily backup"
            created_at="2013-02-25 07:30:12"
            volume_id="5aa119a8-d25b-45a7-8d1b-88e127885635" size="30"
            id="43f20e0e-2c2c-4770-9d4e-c3d769ae5470" name="snap-001"
            os-extended-snapshot-attributes:project_id="0c2eba2c5af04d3f9e9d0d410b371fde"
            os-extended-snapshot-attributes:progress="100%">
            <metadata/>
        </snapshot>
        <snapshot status="available" description="Weekly backup"
            created_at="2013-02-25 07:20:38"
            volume_id="806092e3-7551-4fff-a005-49016f4943b1" size="1"
            id="e820db06-58b5-439d-bac6-c01faa3f6499" name="snap-002"
            os-extended-snapshot-attributes:project_id="0c2eba2c5af04d3f9e9d0d410b371fde"
            os-extended-snapshot-attributes:progress="100%">
            <metadata/>
        </snapshot>
    </snapshots>
    


**Example List Snapshots (Detailed): JSON response**


.. code::

    
    {
        "snapshots": [
            {
                "status": "available",
                "os-extended-snapshot-attributes:progress": "100%",
                "description": "Daily backup",
                "created_at": "2013-02-25T07:30:12.000000",
                "metadata": {},
                "volume_id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
                "os-extended-snapshot-attributes:project_id": "0c2eba2c5af04d3f9e9d0d410b371fde",
                "size": 30,
                "id": "43f20e0e-2c2c-4770-9d4e-c3d769ae5470",
                "name": "snap-001"
            },
            {
                "status": "available",
                "os-extended-snapshot-attributes:progress": "100%",
                "description": "Weekly backup",
                "created_at": "2013-02-25T07:20:38.000000",
                "metadata": {},
                "volume_id": "806092e3-7551-4fff-a005-49016f4943b1",
                "os-extended-snapshot-attributes:project_id": "0c2eba2c5af04d3f9e9d0d410b371fde",
                "size": 1,
                "id": "e820db06-58b5-439d-bac6-c01faa3f6499",
                "name": "snap-002"
            }
        ]
    }


