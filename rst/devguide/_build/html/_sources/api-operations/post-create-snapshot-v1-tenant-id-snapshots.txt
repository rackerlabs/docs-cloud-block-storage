
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Create Snapshot
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v1/{tenant_id}/snapshots

Creates a snapshot.

A snapshot is a point-in-time copy of the volume. You must flush all writes to the volume before you create a snapshot. To do so, either unmount any file systems on the volume or detach the volume.

Snapshots are incremental, so each time that you create a snapshot, the incremental changes for the new snapshot are appended to the previous snapshot, which is still available. Note that you can create a volume from the snapshot if desired.

The ``os-extended-snapshot-attributes:progress`` field in the response body shows the snapshot progress.

When the ``POST`` operation returns the 201 response code, the snapshot is complete.

For more information about snapshots, see the following articles in the Knowledge Center: 

* `Create and Use Cloud Block Storage Snapshots <http://www.rackspace.com/knowledge_center/article/create-and-use-cloud-block-storage-snapshots>`__
* `Allowing Snapshots Without Detaching the Volumes <http://www.rackspace.com/knowledge_center/whitepaper/allowing-snapshots-without-detaching-the-volumes>`__






This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |                         |                         |
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
|snapshot                  |String *(Required)*      |A partial representation |
|                          |                         |of a snapshot used in    |
|                          |                         |the creation process.    |
+--------------------------+-------------------------+-------------------------+
|volume_id                 |Uuid *(Required)*        |The ID of the volume to  |
|                          |                         |snapshot.                |
+--------------------------+-------------------------+-------------------------+
|force                     |Boolean *(Optional)*     |[True/False] Indicate    |
|                          |                         |whether to snapshot,     |
|                          |                         |even if the volume is    |
|                          |                         |attached. The default is |
|                          |                         |False.                   |
+--------------------------+-------------------------+-------------------------+
|display_name              |String *(Optional)*      |Name of the snapshot.    |
|                          |                         |The default is None.     |
+--------------------------+-------------------------+-------------------------+
|display_description       |String *(Optional)*      |Description of snapshot. |
|                          |                         |The default is None.     |
+--------------------------+-------------------------+-------------------------+





**Example Create Snapshot: XML request**


.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
              name="snap-001"
              display_name="snap-001"
              display_description="Daily backup"
              volume_id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
              force="true" />
    


**Example Create Snapshot: JSON request**


.. code::

    {
        "snapshot": {
            "display_name": "snap-001",
            "display_description": "Daily backup",
            "volume_id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
            "force": true
         }
    }
    


Response
""""""""""""""""





**Example Create Snapshot: XML response**


.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
              createdAt="2014-01-28T16:56:56.000000"
              display_name="snap-001"
              display_description="Daily backup"
              id="3fbbcccf-d058-4502-8844-6feeffdf4cb5"                    
              metadata="null"
              os-extended-snapshot-attributes:progress="25.39%"
              os-extended-snapshot-attributes:project_id="696059"           
              size="100"
              status="creating"
              volume_id="521752a6-acf6-4b2d-bc7a-119f9148cd8c" /> 
    


**Example Create Snapshot: JSON response**


.. code::

    {
        "snapshot": {
            "created_at": "2014-01-28T16:56:56.000000",
            "display_description": "Daily backup",
            "display_name": "snap-001",        
            "id": "3fbbcccf-d058-4502-8844-6feeffdf4cb5",
            "metadata": {},
            "os-extended-snapshot-attributes:progress": "25.39%",
            "os-extended-snapshot-attributes:project_id": "123456",        
            "size": 100,
            "status": "creating",
            "volume_id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c"
         }
    }
    


