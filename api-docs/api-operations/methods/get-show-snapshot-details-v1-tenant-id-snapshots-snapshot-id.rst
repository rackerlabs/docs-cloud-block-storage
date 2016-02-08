
.. _get-show-snapshot-details:

Show snapshot details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1/{tenant_id}/snapshots/{snapshot_id}

This operation shows snapshot details.

.. note::
   The ``os-extended-snapshot-attributes:progress`` field in the response body shows snapshot progress. See the following examples.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success                  |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |String *(Required)*      |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+
|{snapshot_id}             |String *(Required)*      |The unique identifier of |
|                          |                         |an existing snapshot.    |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""










**Example Show snapshot details: XML response**


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
   





**Example Show snapshot details: JSON response**


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
   




