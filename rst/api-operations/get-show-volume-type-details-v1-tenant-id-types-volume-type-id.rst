
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Show Volume Type Details -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Show Volume Type Details
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <get-show-volume-type-details-v1-tenant-id-types-volume-type-id.html#request>`__
`Response <get-show-volume-type-details-v1-tenant-id-types-volume-type-id.html#response>`__

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

