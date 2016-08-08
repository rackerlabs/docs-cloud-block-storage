
.. _get-show-snapshot-metadata:

Retrieve metadata for a snapshot
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/snapshots/{snapshot_id}/metadata

This operation retrieves the metadata for the specified snapshot.

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

Response example
----------------

The following example shows the JSON response for retrieving the metadata for
a specified snapshot.

.. code::

   {
       "snapshot": {
           "status": "available",
           "os-extended-snapshot-attributes:progress": "0%",
           "description": null,
           "created_at": "2014-05-06T17:59:52.000000",
           "metadata": {
               "key": "v1"
           },
           "volume_id": "ebd80b99-bc3d-4154-9d28-5583baa80580",
           "os-extended-snapshot-attributes:project_id": "7e0105e19cd2466193729ef78b604f79",
           "size": 10,
           "id": "dfcd17fe-3b64-44ba-b95f-1c9c7109ef95",
           "name": "my-snapshot"
       }
   }

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
