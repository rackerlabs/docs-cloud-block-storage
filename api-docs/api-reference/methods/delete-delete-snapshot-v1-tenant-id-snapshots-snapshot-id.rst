.. _delete-snapshot:

Delete a snapshot
~~~~~~~~~~~~~~~~~

.. code::

    DELETE /v1/{tenant_id}/snapshots/{snapshot_id}

This operation deletes a snapshot.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{snapshot_id}             |String                   |The unique identifier of|
|                          |                         |an existing snapshot.   |
+--------------------------+-------------------------+------------------------+

This operation does not accept a request body.

Response
--------

This operation does not return a response body.

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|202                       |Accepted                 |The request has been    |
|                          |                         |fulfilled and a resource|
|                          |                         |was created.            |
+--------------------------+-------------------------+------------------------+
