.. _get-show-snapshot-details:

Retrieve details for a snapshot
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/snapshots/{snapshot_id}

This operation retrieves details for the specified snapshot.

.. note::
   The ``os-extended-snapshot-attributes:progress`` field in the response body
   shows snapshot progress. See the following examples.

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

Response examples
-----------------

The following example shows the XML response for retrieving details for the
specified snapshot.

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

The following example shows the JSON response for retrieving details for the
specified snapshot.

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
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
