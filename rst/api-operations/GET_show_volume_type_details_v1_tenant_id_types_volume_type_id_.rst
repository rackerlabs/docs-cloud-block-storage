=============================================================================
Show Volume Type Details -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Show Volume Type Details
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_show_volume_type_details_v1_tenant_id_types_volume_type_id_.rst#request>`__
`Response <GET_show_volume_type_details_v1_tenant_id_types_volume_type_id_.rst#response>`__

.. code-block:: javascript

    GET /v1/{tenant_id}/types/{volume_type_id}

Shows volume type details.



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
|{volume_type_id}          |*(Required)*             |The unique identifier of |
|                          |                         |an existing volume type. |
+--------------------------+-------------------------+-------------------------+








Response
^^^^^^^^^^^^^^^^^^





**Example Show Volume Type Details: XML request**


.. code::

    <?xml version='1.0' encoding='UTF-8'?>
        <volume_type xmlns="http://docs.rackspace.com/volume/api/v1"
            id="1" name="SATA">
            <extra_specs/>
        </volume_type>


**Example Show Volume Type Details: JSON request**


.. code::

    {
        "volume_type": {
            "id": "1",
            "name": "SATA",
            "extra_specs": {}
        }
    }

