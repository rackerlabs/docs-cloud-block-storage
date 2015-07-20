
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Delete Snapshot -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Delete Snapshot
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <delete-delete-snapshot-v1-tenant-id-snapshots-snapshot-id.html#request>`__
`Response <delete-delete-snapshot-v1-tenant-id-snapshots-snapshot-id.html#response>`__

.. code::

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




