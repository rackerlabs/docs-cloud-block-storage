.. _get-list-volumes:

Retrieve volumes
~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/volumes

This operation retrieves summary information for all Cloud Block Storage
volumes that the tenant who submits the request can access.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+

This operation does not accept a request body.

Response examples
-----------------

The following example shows the XML response for retrieving summary information
about volumes.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <volumes xmlns="http://docs.rackspace.com/volume/api/v1">
       <volume xmlns="http://docs.rackspace.com/volume/api/v1"
               id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
               display_name="vol-001"
               display_description="Another volume."
               status="active"
               size="100"
               volume_type="SATA"
               created_at="2012-02-14T20:53:07Z">
       </volume>
       <volume xmlns="http://docs.rackspace.com/volume/api/v1"
               id="76b8950a-8594-4e5b-8dce-0dfa9c696358"
               display_name="vol-002"
               display_description="Yet another volume."
               status="active"
               size="100"
               volume_type="SATA"
               created_at="2012-03-15T19:10:03Z" />
   </volumes>

The following example shows the JSON response for retrieving summary
information about volumes.

.. code::

   {
       "volumes": [
           {
               "id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
               "display_name": "vol-001",
               "display_description": "Another volume.",
               "size": 100,
               "volume_type": "SATA",
               "snapshot_id": null,
               "attachments": [],
               "created_at": "2012-02-14T20:53:07Z"
           },
           {
               "id": "76b8950a-8594-4e5b-8dce-0dfa9c696358",
               "display_name": "vol-002",
               "display_description": "Yet another volume.",
               "size": 100,
               "volume_type": "SATA",
               "snapshot_id": null,
               "attachments": [],
               "created_at": "2012-03-15T19:10:03Z"
           }
       ]
   }
   
Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
