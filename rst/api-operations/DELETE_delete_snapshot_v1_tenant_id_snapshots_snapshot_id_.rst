=============================================================================
Delete Snapshot -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Delete Snapshot
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <DELETE_delete_snapshot_v1_tenant_id_snapshots_snapshot_id_.rst#request>`__
`Response <DELETE_delete_snapshot_v1_tenant_id_snapshots_snapshot_id_.rst#response>`__

.. code-block:: javascript

    DELETE /v1/{tenant_id}/snapshots/{snapshot_id}

Deletes a snapshot.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |                         |                         |
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








Response
^^^^^^^^^^^^^^^^^^




