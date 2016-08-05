.. _get-show-volume-type-details:

Retrieve volume type details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/types/{volume_type_id}

This operation retrieves details for a specified volume type.


Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{volume_type_id}          |String                   |The unique identifier of|
|                          |                         |an existing volume type.|
+--------------------------+-------------------------+------------------------+

This operation does not accept a request body.

Response examples
-----------------

The following example shows the XML response for retrieving details for a
specified volume type.

.. code::

   <?xml version='1.0' encoding='UTF-8'?>
       <volume_type xmlns="http://docs.rackspace.com/volume/api/v1"
           id="1" name="SATA">
           <extra_specs/>
       </volume_type>

The following example shows the JSON response for retrieving details for a
specified volume type.

.. code::

   {
       "volume_type": {
           "id": "1",
           "name": "SATA",
           "extra_specs": {}
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
