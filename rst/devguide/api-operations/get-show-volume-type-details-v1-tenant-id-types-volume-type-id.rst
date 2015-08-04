
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Show Volume Type Details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1/{tenant_id}/types/{volume_type_id}

Shows volume type details.



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
|{volume_type_id}          |String *(Required)*      |The unique identifier of |
|                          |                         |an existing volume type. |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""





**Example Show Volume Type Details: XML response**


.. code::

    <?xml version='1.0' encoding='UTF-8'?>
        <volume_type xmlns="http://docs.rackspace.com/volume/api/v1"
            id="1" name="SATA">
            <extra_specs/>
        </volume_type>


**Example Show Volume Type Details: JSON response**


.. code::

    {
        "volume_type": {
            "id": "1",
            "name": "SATA",
            "extra_specs": {}
        }
    }


