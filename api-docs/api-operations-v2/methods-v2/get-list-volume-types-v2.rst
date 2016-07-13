
.. _get-list-volume-types-v2:

List volume types
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/types

This operation lists volume types.



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




This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|sort_key                  |String *(Optional)*      |Sorts by an attribute. A |
|                          |                         |valid value is ``name``, |
|                          |                         |``status``, ``container-f|
|                          |                         |ormat``, ``disk-format``,|
|                          |                         |``size``, ``id``,        |
|                          |                         |``created-at``, or       |
|                          |                         |``updated-at``.          |
|                          |                         |Default is               |
|                          |                         |``created-at``.          |
|                          |                         |The API uses the         |
|                          |                         |natural sorting direction|
|                          |                         |of the ``sort-key``      |
|                          |                         |attribute value.         |
+--------------------------+-------------------------+-------------------------+
|sort_dir                  |String *(Optional)*      |Sorts by one or more sets|
|                          |                         |of attribute and sort    |
|                          |                         |direction combinations.  |
|                          |                         |If you omit the sort     |
|                          |                         |direction in a set,      |
|                          |                         |default is ``desc``      |
|                          |                         |(descending).            |
+--------------------------+-------------------------+-------------------------+
|limit                     |Integer *(Optional)*     |Requests a page size of  |
|                          |                         |items. Returns a number  |
|                          |                         |of items up to a limit   |
|                          |                         |value. Use the ``limit`` |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
+--------------------------+-------------------------+-------------------------+
|marker                    |String *(Optional)*      |The ID of the last-seen  |
|                          |                         |item. Use the ``limit``  |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
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
|volume-type.\             |Dict                     |A set of key and value   |
|**extra_specs**           |                         |pairs that contains the  |
|                          |                         |specifications for a     |
|                          |                         |volume type.             |
+--------------------------+-------------------------+-------------------------+
|volume-type.\ **id**      |UUID                     |The UUID of the volume   |
|                          |                         |type.                    |
+--------------------------+-------------------------+-------------------------+
|volume-type.\ **name**    |String                   |The name of the volume   |
|                          |                         |type.                    |
+--------------------------+-------------------------+-------------------------+




**Example List volume types: JSON response**


.. code::

   {
       "volume_types": [
           {
               "extra_specs": {
                   "capabilities": "gpu"
               },
               "id": "6685584b-1eac-4da6-b5c3-555430cf68ff",
               "name": "SSD"
           },
           {
               "extra_specs": {},
               "id": "8eb69a46-df97-4e41-9586-9a40a7533803",
               "name": "SATA"
           }
       ]
   }




