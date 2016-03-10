
.. _get-list-snapshots:

List snapshots
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1/{tenant_id}/snapshots

This operation lists summary information for all Cloud Block Storage snapshots that the tenant who submits the request can access.



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





This operation does not accept a request body.




Response
""""""""""""""""










**Example: List snapshots XML response**


.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <snapshots xmlns="http://docs.rackspace.com/volume/api/v1">
       <snapshot id="3fbbcccf-d058-4502-8844-6feeffdf4cb5"
                 display_name="snap-001"
                 display_description="Daily backup"
                 volume_id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
                 status="available"
                 size="100"
                 created_at="2012-02-29T03:50:07Z" />
       <snapshot id="e479997c-650b-40a4-9dfe-77655818b0d2"
                 display_name="snap-002"
                 dislay_description="Weekly backup"
                 volume_id="76b8950a-8594-4e5b-8dce-0dfa9c696358"
                 status="available"
                 size="100"
                 created_at="2012-03-19T01:52:47Z" />
   </snapshots>
   





**Example: List snapshots JSON response**


.. code::

   {
       "snapshots": [
           {
               "id": "3fbbcccf-d058-4502-8844-6feeffdf4cb5",
               "display_name": "snap-001",
               "display_description": "Daily backup",
               "volume_id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
               "status": "available",
               "size": 100,
               "created_at": "2012-02-29T03:50:07Z"
           },
           {
               "id": "e479997c-650b-40a4-9dfe-77655818b0d2",
               "display_name": "snap-002",
               "display_description": "Weekly backup",
               "volume_id": "76b8950a-8594-4e5b-8dce-0dfa9c696358",
               "status": "available",
               "size": 100,
               "created_at": "2012-03-19T01:52:47Z"
           }
       ]
   }
   




