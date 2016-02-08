
.. _put-update-volume:

Update volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PUT /v1/{tenant_id}/volumes/{volume_id}

This operation updates the name and description for a volume.



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
|{volume_id}               |String *(Required)*      |The unique identifier of |
|                          |                         |an existing volume.      |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volume**                |String *(Required)*      |Information about the    |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |A description of the     |
|**display_description**   |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|volume.\                  |String *(Optional)*      |The name of the volume.  |
|**display_name**          |                         |                         |
+--------------------------+-------------------------+-------------------------+





**Example Update volume: XML request**


.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <volume xmlns=""
           display_description="New Description"
           display_name="New Name">
   </volume>





**Example Update volume: JSON request**


.. code::

   {
     "volume": {
       "display_name": "new name",
       "display_description": "new description"
     }
   }





Response
""""""""""""""""










**Example Update volume: XML response**


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
   





**Example Update volume: JSON response**


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




