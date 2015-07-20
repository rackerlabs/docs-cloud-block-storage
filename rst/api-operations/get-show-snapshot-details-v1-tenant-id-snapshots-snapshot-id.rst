
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Show Snapshot Details -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Show Snapshot Details
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <get-show-snapshot-details-v1-tenant-id-snapshots-snapshot-id.html#request>`__
`Response <get-show-snapshot-details-v1-tenant-id-snapshots-snapshot-id.html#response>`__

.. code::

    GET /v1/{tenant_id}/snapshots/{snapshot_id}

Shows snapshot details.

.. note::
   The ``os-extended-snapshot-attributes:progress`` field in the response body shows snapshot progress. See the following examples.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |                         |                         |
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





**Example Show Snapshot Details: XML response**


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
    


**Example Show Snapshot Details: JSON response**


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
    

