
.. _delete-snapshot-v2:

Delete snapshot
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    DELETE /v2/{tenant_id}/snapshots/{snapshot_id}

This operation deletes a snapshot.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     | 
|                          |                         |fulfilled and a resource |
|                          |                         |was created.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |UUID *(Required)*        |The UUID of the tenant in|
|                          |                         |a multi-tenancy cloud.   |
+--------------------------+-------------------------+-------------------------+
|{snapshot_id}             |UUID *(Required)*        |The UUID of the snapshot.|
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""






This operation does not return a response body.




