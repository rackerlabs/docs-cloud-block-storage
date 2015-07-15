=============================================================================
List Volume Types -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

List Volume Types
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_list_volume_types_v1_tenant_id_types.rst#request>`__
`Response <GET_list_volume_types_v1_tenant_id_types.rst#response>`__

.. code-block:: javascript

    GET /v1/{tenant_id}/types

Lists volume types.



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








Response
^^^^^^^^^^^^^^^^^^





**Example List Volume Types: XML request**


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


**Example List Volume Types: JSON request**


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

