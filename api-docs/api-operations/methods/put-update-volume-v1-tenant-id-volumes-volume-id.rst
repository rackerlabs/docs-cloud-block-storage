.. _put-update-volume:

Update a volume
~~~~~~~~~~~~~~~

.. code::

    PUT /v1/{tenant_id}/volumes/{volume_id}

This operation updates the name and description for a volume.

Request parameters
------------------

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

The request has the following body parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|**volume**                |String *(Required)*      |Information about the   |
|                          |                         |volume.                 |
+--------------------------+-------------------------+------------------------+
|volume.\                  |String                   |A description of the    |
|**display_description**   |                         |volume.                 |
+--------------------------+-------------------------+------------------------+
|volume.\                  |String                   |The name of the volume. |
|**display_name**          |                         |                        |
+--------------------------+-------------------------+------------------------+

Request example
---------------

The following XML example updates two properties for the volume:
``display_description`` and ``display_name``.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <volume xmlns=""
           display_description="New Description"
           display_name="New Name">
   </volume>

The following JSON example updates two properties for the volume:
``display_description`` and ``display_name``.

.. code::

   {
     "volume": {
       "display_name": "new name",
       "display_description": "new description"
     }
   }

Response examples
-----------------

The following example shows the XML response for updating the volume.

.. code::

   <?xml version='1.0' encoding='UTF-8'?>
   <volume xmlns:atom="http://www.w3.org/2005/Atom"
           xmlns="http://docs.openstack.org/volume/api/v1"
           status="available"
           display_name="New Name"
           availability_zone="nova"
           created_at="2013-07-25 21:53:58"
           display_description="New Description"
           volume_type="SATA"
           snapshot_id="null"
           source_volid="null"
           id="82c9971b-3953-4ca7-b3d4-e671c71d6335"
           size="2">
   <attachments/>
   <metadata/>
   </volume>

The following example shows the JSON response for updating the volume.

.. code::

   {
     "volume":
     {
       "status": "in-use",
       "display_name": "new name",
       "attachments": [],
       "availability_zone": "nova",
       "bootable": "false",
       "created_at": "2012-10-23T17:12:40.000000",
       "display_description": "new description",
       "volume_type": "SATA",
       "snapshot_id": null,
       "source_volid": null,
       "metadata": {},
       "id": "5e9c00de-60b3-48de-ae58-0a07ec842d51",
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
