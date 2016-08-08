.. _get-show-volume:

Retrieve details for a volume
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/volumes/{volume_id}

This operation retrieves details for a specified volume.


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

Response examples
-----------------

The following example shows the XML response for retrieving the details for a
specified volume.

.. code::

   <?xml version='1.0' encoding='UTF-8'?>
   <volume xmlns="http://docs.rackspace.com/volume/api/v1"
           status="available"
           display_name="vol-001"
           attachments=""
           availability_zone="nova"
           bootable="false"
           created_at="2012-02-14T20:53:07Z"
           display_description="Another volume."
           image_id="null"
           volume_type="SATA"
           snapshot_id="null"
           source_volid="e3611474-589b-46b7-9bdf-5555e2e4999b"
           metadata=""
           id="521752a6-acf6-4b2d-bc7a-119f9148cd8c"
           size="100"/>


The following example shows the JSON response for retrieving the details for a
specified volume.

.. code::

   {
     "volume": {
       "status": "available",
       "display_name": "vol-001",
       "attachments": [],
       "availability_zone": "nova",
       "bootable": "false",
       "created_at": "2012-02-14T20:53:07Z",
       "display_description": "Another volume.",
       "image_id": null,
       "volume_type": "SATA",
       "snapshot_id": null,
       "source_volid": "e3611474-589b-46b7-9bdf-5555e2e4999b",
       "metadata": {},
       "id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
       "size": 100
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
