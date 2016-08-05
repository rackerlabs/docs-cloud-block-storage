.. _delete-volume-transfer:

Delete a volume transfer
~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    DELETE /v1/{tenant_id}/os-volume-transfer/​{transfer_id}​

This operation deletes a volume transfer specified by ``transfer_id``.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{transfer_id}             |String                   |The unique identifier of|
|                          |                         |a volume transfer.      |
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
