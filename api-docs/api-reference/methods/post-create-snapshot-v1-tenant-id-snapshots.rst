.. _post-create-snapshot:

Create a snapshot
~~~~~~~~~~~~~~~~~

.. code::

    POST /v1/{tenant_id}/snapshots

This operation creates a snapshot.

A snapshot is a point-in-time copy of the volume. You must flush all writes to
the volume before you create a snapshot. To do so, either unmount any file
systems on the volume or detach the volume.

Snapshots are incremental, so each time that you create a snapshot, the
incremental changes for the new snapshot are appended to the previous snapshot,
which is still available. Note that you can create a volume from the snapshot if desired.

The ``os-extended-snapshot-attributes:progress`` field in the response body
shows the snapshot progress.

When the ``POST`` operation returns the 201 response code, the snapshot is
complete.

For more information about snapshots, see
:how-to:`Create and Use Cloud Block Storage Snapshots<create-and-use-cloud-block-storage-snapshots>`.

Request parameters
------------------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+

The request has the following body parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|**snapshot**              |String *(Required)*      |A partial representation|
|                          |                         |of a snapshot used in   |
|                          |                         |the creation process.   |
+--------------------------+-------------------------+------------------------+
|snapshot.\ **volume_id**  |Uuid *(Required)*        |The ID of the volume to |
|                          |                         |snapshot.               |
+--------------------------+-------------------------+------------------------+
|snapshot.\ **force**      |Boolean                  |[True/False] Indicate   |
|                          |                         |whether to snapshot,    |
|                          |                         |even if the volume is   |
|                          |                         |attached. The default is|
|                          |                         |False.                  |
+--------------------------+-------------------------+------------------------+
|snapshot.\                |String                   |Name of the snapshot.   |
|**display_name**          |                         |The default is None.    |
+--------------------------+-------------------------+------------------------+
|snapshot.\                |String                   |Description of snapshot.|
|**display_description**   |                         |The default is None.    |
+--------------------------+-------------------------+------------------------+

Request example
---------------

The following XML example creates a snapshot.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
             name="snap-001"
             display_name="snap-001"
             display_description="Daily backup"
             volume_id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
             force="true" />

The following JSON example creates a snapshot.

.. code::

   {
       "snapshot": {
           "display_name": "snap-001",
           "display_description": "Daily backup",
           "volume_id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
           "force": true
        }
   }

Response examples
-----------------

The following example shows the XML response for creating a snapshot.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
             created_at="2014-01-28T16:56:56.000000"
             display_name="snap-001"
             display_description="Daily backup"
             id="3fbbcccf-d058-4502-8844-6feeffdf4cb5"
             metadata="null"
             os-extended-snapshot-attributes:progress="25.39%"
             os-extended-snapshot-attributes:project_id="696059"
             size="100"
             status="creating"
             volume_id="521752a6-acf6-4b2d-bc7a-119f9148cd8c" />

The following example shows the JSON response for creating a snapshot.

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

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|201                       |Created                  |The request has been    |
|                          |                         |fulfilled and a resource|
|                          |                         |was created.            |
|-----------------------------------------------------------------------------|
|429                       |SnapshotQuotaExceeded    |Snapshot quota limit has|
|                          |                         |been exceeded per       |
|                          |                         |volume.                 |
+--------------------------+-------------------------+------------------------+
