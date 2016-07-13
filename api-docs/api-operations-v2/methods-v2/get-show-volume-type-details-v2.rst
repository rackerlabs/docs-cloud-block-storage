
.. _get-show-volume-type-details-v2:

Show volume type details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/types/{volume_type_id}

This operation shows volume type details.



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
|{tenant_id}               |UUID *(Required)*        |The UUID of the tenant in|
|                          |                         |a multi-tenancy cloud.   |
+--------------------------+-------------------------+-------------------------+
|{volume_type_id}          |UUID *(Required)*        |The UUID for an existing |
|                          |                         |volume type.             |
+--------------------------+-------------------------+-------------------------+



This operation does not accept a request body.




Response
""""""""""""""""




This table shows the body parameters for the response:



+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**volume-type**           |List                     |A list of ``volume_type``|
|                          |                         |objects.                 |
+--------------------------+-------------------------+-------------------------+
|volume-type.\ **id**      |UUID                     |The UUID of the volume   |  
|                          |                         |type.                    |
+--------------------------+-------------------------+-------------------------+
|volume-type.\ **name**    |String                   |The name of the volume   |
|                          |                         |type.                    |
+--------------------------+-------------------------+-------------------------+
|volume-type.\             |String                   |The volume type          |
|**description**           |                         |description.             |
+--------------------------+-------------------------+-------------------------+
|volume-type.\             |Boolean                  |Indicates if the volume  |
|**is_public**             |                         |type is public           |
|                          |                         |(``true``).              |
+--------------------------+-------------------------+-------------------------+
|volume-type.\             |Dict                     |A set of key and value   |
|**extra_specs**           |                         |pairs that contains the  |
|                          |                         |specifications for a     |
|                          |                         |volume type.             |
+--------------------------+-------------------------+-------------------------+







**Example Show volume type details: JSON response**


.. code::

   {
       "volume_type": {
           "id": "6685584b-1eac-4da6-b5c3-555430cf68ff",
           "name": "vol-type-001",
           "description": "volume type 001",
           "is_public": "true",
           "extra_specs": {
               "capabilities": "gpu"
           }
       }
   }




