.. _get-list-volume-types:

Retrieve volume types
~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/types

This operation retrieves volume types.

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

The following example shows the XML response for retrieving volume types.

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

The following example shows the JSON response for retrieving volume types.

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

.. note::
   Two storage types are currently supported: SATA and SSD. SATA is the standard
   performance storage option and SSD is the high performance option.

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
