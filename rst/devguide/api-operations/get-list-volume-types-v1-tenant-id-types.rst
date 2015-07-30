
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List Volume Types
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1/{tenant_id}/types

Lists volume types.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |                         |                         |
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





This operation does not accept a request body




Response
""""""""""""""""


This operation does not accept a response body




**Example List Volume Types: XML response**


.. code::

    <?xml version='1.0' encoding='UTF-8'?>
    <volume_types xmlns="http://docs.rackspace.com/volume/api/v1">>
        <volume_type id="1" name="SATA">
             <extra_specs/>
         </volume_type>
         <volume_type id="2" name="SSD">
             <extra_specs/>
        </volume_type>
    </volume_types>


**Example List Volume Types: JSON response**


.. code::

    {
        "volume_types": [
            {
                "id": 1,
                "name": "SATA",
                "extra_specs": {}
            },
            {
                "id": 2,
                "name": "SSD",
                "extra_specs": {}
            }
        ]
    }

