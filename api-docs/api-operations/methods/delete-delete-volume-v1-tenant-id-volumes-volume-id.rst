.. _delete-volume:

Delete a volume
~~~~~~~~~~~~~~~

.. code::

    DELETE /v1/{tenant_id}/volumes/{volume_id}

This operation deletes a volume.

.. note::
   If a snapshot of the volume exists, you cannot delete the volume until you
   delete the snapshot.


Request
-------


The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{volume_id}               |String                   |The unique identifier of|
|                          |                         |an existing volume.     |
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
|                          |                         |accepted for processing.|
+--------------------------+-------------------------+------------------------+
