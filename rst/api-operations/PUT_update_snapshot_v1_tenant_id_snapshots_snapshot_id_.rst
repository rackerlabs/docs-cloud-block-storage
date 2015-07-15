=============================================================================
Update Snapshot -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Update Snapshot
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <PUT_update_snapshot_v1_tenant_id_snapshots_snapshot_id_.rst#request>`__
`Response <PUT_update_snapshot_v1_tenant_id_snapshots_snapshot_id_.rst#response>`__

.. code-block:: javascript

    PUT /v1/{tenant_id}/snapshots/{snapshot_id}

Updates a specified snapshot.



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
|{snapshot_id}             |*(Required)*             |The unique identifier of |
|                          |                         |an existing snapshot.    |
+--------------------------+-------------------------+-------------------------+



This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|display_description       |string *(Required)*      |Describes the snapshot.  |
+--------------------------+-------------------------+-------------------------+
|display_name              |string *(Required)*      |The name of the snapshot.|
+--------------------------+-------------------------+-------------------------+







**Example Update Snapshot: XML request**


.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
              display_name="snap-001"
              display_description="This is yet, another snapshot."/>
    
    


**Example Update Snapshot: JSON request**


.. code::

    {
        "snapshot":{
            "display_name":"snap-001",
            "display_description":"This is yet, another snapshot."
        }
    }


Response
^^^^^^^^^^^^^^^^^^





**Example Update Snapshot: XML request**


.. code::

    <?xml version='1.0' encoding='UTF-8'?>
    <snapshot
        xmlns:os-extended-snapshot-attributes="http://docs.rackspace.com/volume/api/v1"
        status="available"
        display_description="This is yet, another snapshot"
        created_at="2013-02-20T08:11:34.000000"
        volume_id="2402b902-0b7a-458c-9c07-7435a826f794"
        size="1"
        id="4b502fcb-1f26-45f8-9fe5-3b9a0a52eaf2"
        display_name="vol-001"
        os-extended-snapshot-attributes:project_id="0c2eba2c5af04d3f9e9d0d410b371fde"
        os-extended-snapshot-attributes:progress="100%">
        <metadata/>
    </snapshot>
    
    


**Example Update Snapshot: JSON request**


.. code::

    {
        "snapshot":{
            "created_at":"2013-02-20T08:11:34.000000",
            "display_description":"This is yet, another snapshot",
            "display_name":"vol-001",
            "id":"4b502fcb-1f26-45f8-9fe5-3b9a0a52eaf2",
            "size":1,
            "status":"available",
            "volume_id":"2402b902-0b7a-458c-9c07-7435a826f794"
        }
    }

